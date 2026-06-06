1\. IAM (Identity and Access Management)

IAM is the AWS service used to control who can access what resources and what actions they can perform.



Purpose: Security and permissions.



Example:

With IAM:



Developer → EC2, S3 only

Data Scientist → S3 only

Admin → Full Access



You create a user for a developer.

Allow access to S3.

Deny access to EC2 deletion.



Key concepts:



\->Users-A user represents a person or application.

Each user gets: Username/Password (for AWS Console)/Access Key/Secret Access Key

Example:

User: RamSai

Permissions:

\- Read S3

\- Launch EC2

\-------------------------------------------------------------------------------

Groups-Groups are collections of users.Instead of assigning permissions one-by-one:Give permissions to the group once.

Developers Group

├── RamSai

├── John

└── David

Example:



Developers Group

&#x20;   ↓

EC2 Full Access

S3 Read Access  All members inherit those permissions.

\--------------------------------------------------------------------------------



Policies: Policies define permissions.Policies are JSON documents.

Example:



{

&#x20; "Version": "2012-10-17",

&#x20; "Statement": \[

&#x20;   {

&#x20;     "Effect": "Allow",

&#x20;     "Action": "s3:ListBucket",

&#x20;     "Resource": "\*"

&#x20;   }

&#x20; ]

}

Example policy : 

Allow only S3 Read:



{

&#x20; "Version": "2012-10-17",

&#x20; "Statement": \[

&#x20;   {

&#x20;     "Effect":"Allow",

&#x20;     "Action":\[

&#x20;       "s3:GetObject",

&#x20;       "s3:ListBucket"

&#x20;     ],

&#x20;     "Resource":"\*"

&#x20;   }

&#x20; ]

}

Roles: Roles are extremely important in MLOps.Temporary permissions



Real-world analogy: IAM is the security guard deciding who can enter which rooms.





2.Amazon S3 (Simple Storage Service) – Complete Overview





Amazon S3 as a giant cloud storage service where you can store and retrieve any amount of data from anywhere in the world. AWS manages the infrastructure, scalability, durability, and security for you.





Amazon S3 is an object storage service used to store files such as:

Images\\Videos\\PDFs\\Backups\\Application logs\\ML datasets\\Website files



S3 stores data as objects inside buckets.



Real-life Example



Imagine Google Drive:



Folder → Bucket

File → Object

File Name → Key  \*A bucket is a container that stores objects.\*An object is the actual file stored in S3.\* Key=A unique name for an object.



3\. How S3 Works

Create a Bucket

Upload Objects

Access Objects using URL/API

Download or Delete Objects





4\. Important Features



Scalability/Durability/Availability/Security



5\. S3 Storage Classes

Storage Class	Use Case

S3 Standard	Frequently accessed data

S3 Intelligent-Tiering	Unknown access pattern

S3 Standard-IA	Infrequently accessed data

S3 One Zone-IA	Lower cost storage

S3 Glacier Instant Retrieval	Archive with quick access

S3 Glacier Flexible Retrieval	Long-term archive

S3 Glacier Deep Archive	Lowest cost archive



6\. Common Use Cases



Website Hosting/Backup Storage/Machine Learning/Data Lakes





7\. S3 Security

IAM Policies



Control who can access buckets.



Example:



Allow:

&#x20; - s3:GetObject

&#x20; - s3:PutObject



Bucket Policies



Control access at bucket level.



Encryption

SSE-S3

SSE-KMS

Client-side Encryption



Block Public Access



Prevents accidental public exposure of data. AWS recommends keeping public access blocked unless explicitly required.



8\. Versioning



Versioning keeps multiple copies of the same file.



Example:



report.pdf (v1)

report.pdf (v2)

report.pdf (v3)



Amazon S3 (Simple Storage Service) is a highly scalable, durable, secure object storage service provided by AWS that stores data as objects within buckets and is commonly used for backups, data lakes, static website hosting, machine learning datasets, and application storage.



For MLOps interviews, focus on:



Buckets, Objects, and Keys

Storage Classes

Versioning

Lifecycle Policies

IAM and Bucket Policies

S3 + EC2 integration

S3 + SageMaker integration

S3 for model and dataset storage



Amazon EC2 (Elastic Compute Cloud) – Complete Overview



Amazon EC2 (Elastic Compute Cloud) is a service that lets you create and run virtual servers in the cloud.

Instead of buying a physical computer, AWS provides a virtual machine (VM) that you can start, stop, resize, and manage whenever you need.

EC2 is a cloud-based virtual server that allows you to run applications, websites, databases, and machine learning workloads on AWS.

Real-Life Example



Suppose you developed a website on your laptop.



Without EC2:



Users → Your Laptop → Website



Problems:



Laptop must stay ON 24/7

Limited resources

Not scalable



With EC2:



Users → EC2 Instance → Website



Benefits:



Available 24/7

High performance

Easily scalable

Core Components of EC2

1\. Instance



An EC2 Instance is a virtual machine.



Example:



Windows Server

Ubuntu Linux

Amazon Linux

Red Hat Linux



Think of an Instance as: Physical Computer = EC2 Instance



It contains: Operating System/Software/Configurations





2\. AMI (Amazon Machine Image)



An AMI is a template used to launch an EC2 instance.



It contains:



Operating System

Software

Configurations



Examples:



Ubuntu 24.04

Amazon Linux 2023

Windows Server 2022

AMI → Create Instance





3.Instance Types

Different instance sizes for different workloads.

General Purpose

Example: t2.micro/t3.micro/t3.medium



Used for: Websites /Applications/Development



Compute Optimized

c5.large/c6i.large



Used for:/ML training/Scientific computing





Memory Optimized: r5.large/r6i.large



Used for :Databases/Big data processing



GPU Instances/g4dn.xlarge/p4d.24xlarge



Used for:/Deep Learning

AI/Video processing



EC2 Storage/EBS (Elastic Block Store)Acts like a hard disk attached to EC2.

EC2 Instance

&#x20;    |

&#x20;    v

EBS Volume

Stores: Operating System/Files/Databases



Instance Store/Temporary storage.



Instance Stop/Delete

&#x20;     ↓

Data Lost



Used for:



Cache

Temporary files

\------------------------------------------------------------

Security Groups

A Security Group acts as a firewall.

Allow:

Port 22 → SSH/Port 80 → HTTP/Port 443 → HTTPS

Traffic:/Internet/Security Group/EC2 Instance



Key Pair/Used to securely connect to Linux instances.



When creating EC2:

Create Key Pair

&#x20;     |

Download .pem file

&#x20;     |

SSH Login



Example:



ssh -i key.pem ubuntu@public-ip





EC2 Scaling

Auto Scaling



Automatically adds or removes servers.



Example:



100 Users → 1 EC2



10,000 Users → 5 EC2



AWS adjusts automatically.



Load Balancer



Distributes traffic across multiple EC2 instances.



Users

&#x20;  |

Load Balancer

&#x20;/    |    \\

EC2  EC2  EC2



Benefits:



High availability

Better performance

EC2 in MLOps



A common MLOps architecture:



GitHub

&#x20;  |

&#x20;  v

EC2

&#x20;  |

Docker

&#x20;  |

FastAPI

&#x20;  |

ML Model



Uses:



Train ML models

Deploy FastAPI applications

Run Docker containers

Host APIs

Execute pipelines





EC2 + S3 Workflow

Dataset

&#x20;  |

&#x20;  v

S3 Bucket

&#x20;  |

Download

&#x20;  |

EC2 Training Server

&#x20;  |

Train Model

&#x20;  |

Store Model

&#x20;  |

S3 Bucket



This is one of the most common AWS architectures in ML projects.



Frequently Asked Interview Questions

What is EC2?



Amazon EC2 is a cloud computing service that provides scalable virtual servers for running applications on AWS.



What is an AMI?



An Amazon Machine Image is a template containing an operating system and software configuration used to launch EC2 instances.



What is EBS?



Elastic Block Store is persistent storage attached to EC2 instances.



What is a Security Group?



A virtual firewall that controls inbound and outbound traffic to an EC2 instance.



What is Auto Scaling?



A service that automatically increases or decreases the number of EC2 instances based on demand.





30-Second Interview Answer



Amazon EC2 (Elastic Compute Cloud) is an AWS service that provides scalable virtual servers in the cloud. It allows users to launch instances from AMIs, attach storage using EBS, secure access through Security Groups, and scale applications using Auto Scaling and Load Balancers. EC2 is widely used for hosting applications, websites, APIs, and machine learning workloads.





Docker

Docker is a containerization platform that packages an application along with all its dependencies, libraries, and configurations into a Container so that it runs consistently on any system.

Docker allows you to build, ship, and run applications inside lightweight containers.



A container is a lightweight, isolated environment that contains:



Application code/Python packages/Libraries/Runtime/Dependencies

Example:



Container

&#x20;├── Python

&#x20;├── FastAPI

&#x20;├── NumPy

&#x20;├── Pandas

&#x20;└── ML Model



You can run the same container on:

Windows/Linux/AWS/EC2/Azure/Google Cloud



Docker Architecture

Docker Client->Commands you type:docker run/docker build/docker ps





&#x20;     |

&#x20;     v

Docker Engine->The service that creates and manages containers.

&#x20;     |

&#x20;     +---- Images->An Image is a blueprint/template for creating containers.

&#x20;                                    Cake Recipe = Docker Image

&#x20;                      Cake = Container//Create Image: docker build -t  myapp .                        

&#x20;     |

&#x20;     +---- Containers == A running instance of an image.//docker run myapp

Example:



Image

&#x20; |

&#x20; v

Container Running



You can create multiple containers from one image.



3\. Dockerfile



A text file containing instructions to build an image



FROM python:3.11



WORKDIR /app



COPY . .



RUN pip install -r requirements.txt



CMD \["python", "app.py"]//docker build -t myapp .

**4. Docker Hub**::  Docker's public image repository.



Think of it as:



GitHub for Docker Images



Popular images: Python/Ubuntu/MySQL/Redis/Nginx  //docker pull python:3.11



Dockerfile

&#x20;     |

&#x20;     v

Docker Image

&#x20;     |

&#x20;     v

Docker Container

&#x20;     |

&#x20;     v

Running Application



Common Docker Commands

Check Docker Version  - docker --version

List Running Containers - docker ps

List Images  - docker images

Run Container -docker run nginx

Stop Container  -docker stop container\_id

Remove Container -docker rm container\_id

Remove Image -docker rmi image\_name

\----------------------------------------------------------------------------------

**Docker Networking**

Containers can communicate with each other.

FastAPI Container

&#x20;       |

Database Container//docker network create ml-network



**Docker Volumes:** 

Volumes store data permanently.



Docker in MLOps



Since you're preparing for MLOps roles, Docker is one of the most important skills.



Example workflow:



Train Model

&#x20;     |

&#x20;     v

model.pkl

&#x20;     |

&#x20;     v

FastAPI API

&#x20;     |

&#x20;     v

Docker Container

&#x20;     |

&#x20;     v

AWS EC2



Docker + AWS Workflow

Developer Laptop

&#x20;       |

docker build

&#x20;       |

&#x20;       v

Docker Image

&#x20;       |

docker push

&#x20;       |

&#x20;       v

:contentReference\[oaicite:1]{index=1}

&#x20;       |

docker pull

&#x20;       |

&#x20;       v

EC2 / ECS///This is a very common MLOps deployment pipeline.





Docker vs Virtual Machine

Docker Container	Virtual Machine

Lightweight	Heavy

Starts in seconds	Takes minutes

Shares OS kernel	Has full OS

Uses less memory	Uses more memory

Better for microservices	Better for full OS isolation



Docker Interview Answer (30 Seconds)



Docker is a containerization platform that packages applications and their dependencies into lightweight containers. It ensures that applications run consistently across development, testing, and production environments. Key Docker components include Docker Images, Containers, Dockerfiles, Volumes, and Networks. In MLOps, Docker is commonly used to package ML models and APIs for deployment on services like EC2, ECS, and Kubernetes.





