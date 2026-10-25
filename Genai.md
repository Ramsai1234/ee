```

Basic concepts every GenAI Engineer should know
1. What is Generative AI?

Generative AI is a type of artificial intelligence that creates new content, such as text,
 images, audio, video, and code, based on patterns learned from training data.

Example: ChatGPT generates answers from a user's questions.

2. What is the difference between AI, Machine Learning, Deep Learning, and Generative AI?
- AI: The broad field of making machines perform intelligent tasks.
- ML: Algorithms learn patterns from data.
- Deep Learning: ML using multilayer neural networks.
- Generative AI: Models generate new content based on learned patterns.
3. What is an LLM?

An LLM, or Large Language Model, is a neural network trained on large amounts of text and other data to understand and generate language.

Examples include GPT models, Llama, and Gemini.

4. What are the applications of Generative AI?
- Chatbots and virtual assistants
- Document summarization
- Question answering
- Code generation
- RAG applications
- Text and image generation
- Customer support automation
5. What is the difference between traditional AI and Generative AI?

Traditional AI often classifies, predicts, or detects patterns. Generative AI produces new content.

Example: A traditional ML model predicts whether an email is spam. A GenAI model drafts an email.

6. What is a foundation model?

A foundation model is a large model trained on broad datasets that can be adapted to multiple tasks,
such as summarization, question answering, and classification.

7. What is a Large Multimodal Model?

A multimodal model can process or generate more than one type of data, such as text, images, audio, or video.

8. What is a token in Generative AI?

A token is a unit of text processed by a language model. It may represent a word, part of a word, punctuation, or another text unit.

For example, the word "playing" might be represented by one token or multiple tokens depending on the tokenizer.

9. What is tokenization?

Tokenization converts text into tokens that a model can process.

Typical flow:

Text → Tokenizer → Token IDs → Model

10. What is an embedding?

An embedding is a numerical vector representing information such as a word, sentence, image, or document.

Embeddings allow systems to compare semantic similarity between pieces of information.

11. What is a hallucination in GenAI?

A hallucination occurs when a model generates information that is false, unsupported, or fabricated but presents it as if it were correct.

12. How can you reduce hallucinations?
- Use RAG with reliable documents.
- Provide clear instructions and context.
- Require source-grounded answers.
- Allow the model to say it does not know.
- Evaluate answers against trusted references.
These techniques reduce risk but do not guarantee hallucination-free answers.

13. What is a context window?

A context window is the maximum amount of input and generated content a model can handle within a single interaction,
 measured in tokens. The exact limit depends on the model.

14. What is inference in Generative AI?

Inference is the process of using a trained model to generate predictions or outputs for new input.

Example: Sending a prompt to an LLM and receiving an answer.

15. What is the difference between training and inference?
- Training: The model learns patterns by updating its parameters.
- Inference: The trained model generates outputs without normally updating its parameters.
16. What is temperature in an LLM?

Temperature controls the randomness of token selection during generation.
- Lower temperature: generally more predictable output.
- Higher temperature: generally more varied output.
It does not guarantee factual accuracy.

17. What are top-k and top-p sampling?
- Top-k: Selects the next token from a set of the \(k\) most likely tokens.
- Top-p: Selects from the smallest set of tokens whose cumulative probability reaches a chosen threshold.
Both influence output diversity.

18. What is a system prompt?

A system prompt provides high-level instructions defining the model's role, behavior, boundaries, and response requirements.

Example: "You are a customer-support assistant. Answer using the provided company documentation."

19. What is prompt engineering?

Prompt engineering is the process of designing and refining instructions and context to help an LLM produce useful outputs.

20. What is the difference between an open-source model and a proprietary model?

An open-weight model makes its trained weights available under its particular license, allowing permitted local hosting or customization.
A proprietary model is controlled by its provider and may be accessible through an API.

Note: Open weights do not necessarily mean the training data, training code, or all components are open source.

Part 2: LLMs and Transformers (21–40)
Understand how LLMs work
21. What is a Transformer?

A Transformer is a neural network architecture that uses attention mechanisms to process relationships between tokens.
It is the foundation of many modern LLMs.

22. What is self-attention?

Self-attention allows each token to weigh information from other tokens in the input to build a context-aware representation.

23. What are Query, Key, and Value in attention?
- Query (Q): Represents what a token is looking for.
- Key (K): Represents information used to match against a query.
- Value (V): Represents the information aggregated using attention weights.
24. What is multi-head attention?

Multi-head attention runs several attention operations in parallel so the model can learn different relationships between tokens.

25. What is positional encoding?

Positional encoding or positional information helps a Transformer account for token order,
 because attention alone does not inherently encode the sequence's order.

26. What is an encoder in a Transformer?

An encoder transforms input tokens into contextual representations.
 Encoder-based models are often used for tasks such as classification and semantic representation.

27. What is a decoder in a Transformer?

A decoder generates tokens autoregressively, using previously available tokens to predict the next token.

28. What is an encoder-decoder model?

It contains an encoder that processes the input and a decoder that generates output.
This architecture is useful for tasks such as translation and text transformation.

29. What is autoregressive generation?

Autoregressive generation predicts one token at a time, using the preceding context to generate the next token.

30. What is perplexity?

Perplexity measures how well a language model predicts a sequence of tokens.
Lower perplexity generally indicates better predictive performance on the same evaluation data, but it does not necessarily mean better real-world answers.

31. What is pretraining?

Pretraining is the initial large-scale training stage in which a model learns general patterns from a broad dataset.

32. What is instruction tuning?

Instruction tuning trains a model on instruction-and-response examples to improve its ability to follow user instructions.

33. What is RLHF?

Reinforcement Learning from Human Feedback uses human preference feedback to help align model responses with desired behavior.
 Implementations can use different optimization methods.

34. What is a pretrained model?

A pretrained model has already learned from an initial training process and can be used directly or adapted to a particular task.

35. What is the difference between GPT-style and BERT-style models?

GPT-style models are typically decoder-only and designed for autoregressive generation.
BERT-style models are typically encoder-based and use bidirectional context, making them useful for understanding tasks.

36. What is the KV cache?

A key-value cache stores previously computed attention keys and values during generation, avoiding repeated calculations and improving decoding efficiency.

37. What is the difference between a model's parameters and hyperparameters?

Parameters are learned values inside the model. Hyperparameters are settings chosen for training or inference, such as learning rate, batch size, and temperature.

38. What is fine-tuning?

Fine-tuning continues training a pretrained model on a more specific dataset to adapt its behavior or capabilities to a target task.

39. What is quantization?

Quantization represents model weights or activations with lower numerical precision, often reducing memory usage and sometimes improving inference speed, with potential quality trade-offs.

40. What is the difference between an LLM and an embedding model?

An LLM commonly generates or processes text. An embedding model converts inputs into vectors that represent semantic or other learned features.
 Some systems use both together.

Part 3: Prompt Engineering (41–55)
41. What is zero-shot prompting?

Asking a model to perform a task without providing examples.

42. What is few-shot prompting?

Providing a small number of examples in the prompt to demonstrate the desired task or output format.

43. What is one-shot prompting?

Providing one example of the expected input and output before asking the model to perform the task.

44. What is chain-of-thought prompting?

It is a prompting approach intended to encourage multistep reasoning. In production, you can instead request concise explanations,
 intermediate results, or verifiable steps appropriate to the task.

45. What is role prompting?

Assigning the model a role, such as "Act as a Python tutor," to guide the style and scope of the response.

46. What is prompt templating?

Creating a reusable prompt with placeholders for dynamic information.

Example:
template = "Explain {topic} with an example."



47. What is structured output?

Output that follows a defined schema, such as JSON with specific fields and data types.

48. What is the difference between a prompt and a prompt template?

A prompt is the actual instruction sent to the model. A prompt template is a reusable structure that generates prompts using variable values.

49. What is prompt chaining?

Breaking a complex task into multiple model calls, where the output of one step becomes input to another.

50. What is prompt injection?

An attack in which malicious instructions in user input or retrieved content attempt to override the intended behavior of the application.

51. How do you defend against prompt injection?

Treat user input and retrieved documents as untrusted, separate instructions from data, enforce permissions outside the LLM,
 validate tool calls, and test adversarial inputs.

52. What is the difference between system, user, and assistant messages?
- System or developer instructions establish application behavior.
- User messages contain requests or data.
- Assistant messages contain the model's responses.
The exact message roles available depend on the model interface.

53. What is constrained decoding?

Constrained decoding restricts generation to outputs that satisfy defined rules, such as a grammar or JSON schema,
 when supported by the model or serving system.

54. How do you improve a poorly performing prompt?

Clarify the task, supply relevant context, specify constraints and output format, add examples when useful,
 and evaluate the results against representative test cases.

55. How do you select a prompt for production?

Choose the prompt that performs reliably on a representative evaluation set, satisfies safety and formatting requirements,
and meets latency and cost targets.

Part 4: LangChain and LCEL (56–75)
56. What is LangChain?

LangChain is a framework for building LLM applications by connecting models, prompts, retrievers, tools, and other components.

57. What are the main components of LangChain?

Common components include chat models, prompt templates, output parsers, retrievers, document loaders, text splitters, tools, and runnable sequences.

58. What is a chat model in LangChain?

A chat model is an interface for sending messages to a conversational model and receiving responses.

59. What is a PromptTemplate?

It creates a prompt by filling placeholders with supplied values.
from langchain_core.prompts import PromptTemplateprompt = PromptTemplate.from_template(    "Explain {topic} simply.")result = prompt.format(topic="RAG")print(result)



60. What is a ChatPromptTemplate?

It creates a structured sequence of chat messages, often including system and human messages.

61. What is an output parser?

An output parser transforms model output into a more useful representation, such as a string, structured object, or validated data structure.

62. What is LCEL?

LangChain Expression Language is a way to compose runnable components into sequences and other workflows.

63. What does the pipe operator (|) do in LCEL?

It connects runnable components so the output from one component is passed to the next.
chain = prompt | model | output_parser



64. What is a RunnableSequence?

It represents a sequence of runnable components executed in order.

65. What is RunnablePassthrough?

It passes input through unchanged, which is useful when preserving input fields in a chain.

66. What is RunnableParallel?

It executes multiple runnable branches on the same input and combines their results into a mapping.

67. What is a document loader?

A document loader imports data from sources such as PDFs, text files, websites, or databases into document objects.

68. What is a text splitter?

A text splitter divides large documents into smaller chunks that are easier to embed and retrieve.

69. What is a retriever in LangChain?

A retriever takes a query and returns relevant documents. It may use vector search, keyword search, or another retrieval method.

70. What is a chain in LangChain?

A chain combines components into a workflow, such as formatting a prompt, calling a model, and parsing its output.

71. What is a retrieval chain?

A retrieval chain retrieves relevant documents for a query and uses them, together with the query, to generate a response.

72. What is a document-combination chain?

It combines retrieved documents with a question or prompt before passing them to an LLM. Some implementations combine documents directly,
 while others summarize or refine them.

73. What is the difference between invoke() and stream()?
- invoke() returns a completed result.
- stream() yields output incrementally when supported by the runnable and underlying model.
74. How do you handle errors in a LangChain application?

Use exception handling, input validation, timeouts, controlled retries, logging, and appropriate fallback behavior.

75. How do you integrate Ollama with LangChain?

Use a compatible Ollama chat model integration and run the selected model locally.
from langchain_ollama import ChatOllamamodel = ChatOllama(    model="llama3.2",   
temperature=0)response = model.invoke(    "Explain RAG in simple terms.")print(response.content)



The model must be available in your Ollama installation, and the integration package must be installed.

Part 5: RAG and Vector Databases (76–110)
This section is particularly important because many GenAI Engineer roles involve building document question-answering systems.

76. What is RAG?

Retrieval-Augmented Generation combines information retrieval with text generation.
 The application retrieves relevant external information and supplies it to an LLM to help produce a grounded response.

77. Why do we use RAG?

RAG helps an application use private, domain-specific, or frequently updated information without retraining the LLM every time the source data changes.

78. What are the main stages of a RAG pipeline?
1. Load source documents.
2. Clean and split the documents.
3. Generate embeddings.
4. Store vectors and metadata.
5. Retrieve relevant chunks for a query.
6. Optionally rerank the retrieved chunks.
7. Construct a prompt with the evidence.
8. Generate and evaluate the answer.
79. What is a document in a RAG system?

A document is a unit of content, often containing text and metadata such as source, page number, title, or document ID.

80. What is chunking?

Chunking divides long documents into smaller pieces for embedding and retrieval.

81. What is chunk size?

Chunk size is the amount of text contained in each chunk, measured using characters, tokens, or another defined unit.

82. What is chunk overlap?

Chunk overlap is the shared content between consecutive chunks. It helps preserve context when relevant information spans chunk boundaries.

83. How do you choose chunk size?

Test different chunk sizes and overlap values against realistic questions. Consider document structure, retrieval precision, context limits, latency,
 and answer quality.

84. What happens if chunks are too small?

They may lose important context and retrieve incomplete information.

85. What happens if chunks are too large?

They may contain irrelevant information, reduce retrieval precision, and consume more of the LLM's context window.

86. What is an embedding model in RAG?

An embedding model converts document chunks and user queries into vectors so the system can retrieve semantically related content.

87. What is a vector database?

A vector database stores and searches vector representations, often with associated metadata.

Examples include Chroma , Qdrant , Pinecone , and Milvus.

88. What is semantic search?

Semantic search retrieves content based on similarity in meaning rather than requiring exact keyword matches.

89. What is cosine similarity?

Cosine similarity measures the cosine of the angle between two vectors. It is commonly used to compare embedding similarity.
\[
\operatorname{cosine}(A,B)=
\frac{A\cdot B}{\|A\|\|B\|}
\]

90. What is metadata filtering?

Metadata filtering restricts retrieval based on properties such as department, document type, date, or access permissions.

91. What is top-k retrieval?

Top-k retrieval returns the \(k\) highest-ranked results according to the retrieval system's scoring method.

92. What is a retriever?

A retriever is the component that accepts a query and returns relevant documents or passages.

93. What is the difference between a vector store and a retriever?

A vector store manages vector storage and similarity search.
 A retriever provides a broader interface for fetching documents and can use vector stores or other retrieval mechanisms.

94. What is hybrid search?

Hybrid search combines lexical retrieval, such as BM25 keyword matching, with vector-based semantic retrieval.

95. What is BM25?

BM25 is a lexical information-retrieval ranking algorithm that scores documents based on query-term matches, term frequency, and document length.

96. What is reranking?

Reranking takes an initial set of retrieved documents and reorders them using a more detailed relevance-scoring method.

97. What is a cross-encoder reranker?

A cross-encoder jointly processes a query and candidate document to produce a relevance score.
 It is often more computationally expensive than vector retrieval but can improve ranking quality.

98. What is query expansion?

Query expansion adds related terms or alternative expressions to a query to improve retrieval coverage.

99. What is query rewriting?

Query rewriting transforms a user's question into a form better suited for retrieval, for example,
by resolving references from conversation history.

100. What is HyDE?

Hypothetical Document Embeddings generates a hypothetical answer or document for a query and uses its embedding to retrieve potentially relevant real documents.
The generated text is not treated as factual evidence.

101. What is contextual compression in RAG?

Contextual compression reduces retrieved content to the portions most relevant to the query before sending it to the LLM.

102. What is parent-child retrieval?

It retrieves smaller child chunks for precise matching but returns their larger parent sections to preserve context.

103. What is multi-query retrieval?

It generates multiple alternative queries from the original question, retrieves results for each, and combines the results.

104. What is Self-RAG?

Self-RAG is a research approach that uses retrieval and self-reflective signals to help a model decide when to retrieve and assess its generated responses.

105. What is Corrective RAG (CRAG)?

CRAG is an approach that evaluates retrieved evidence and applies corrective actions when the retrieved content is insufficient or unreliable.

106. What is agentic RAG?

Agentic RAG uses an agent or decision-making workflow to select retrieval actions, reformulate questions, choose tools, or iterate based on intermediate results.

107. What is Graph RAG?

Graph RAG uses a knowledge graph or graph-based relationships to retrieve information connected through entities and their relationships,
sometimes alongside traditional vector search.

108. How do you evaluate retrieval quality?

Use metrics such as Recall@k, Precision@k, Mean Reciprocal Rank (MRR), and Normalized Discounted Cumulative Gain (NDCG),
 along with representative human-reviewed test questions.

109. What is the difference between retrieval evaluation and answer evaluation?

Retrieval evaluation measures whether relevant evidence was found. Answer evaluation measures whether the generated response is correct,
 relevant, grounded, and useful.

110. How do you troubleshoot a RAG system that gives incorrect answers?

Check document extraction, chunk boundaries, embedding compatibility, retrieval scores, metadata filters, reranking, prompt construction,
context truncation, and the model's final answer. Evaluate each stage separately to locate the failure.

Part 6: AI Agents and Tool Calling (111–130)
111. What is an AI agent?

An AI agent uses a model to determine actions, potentially calls tools, observes results, and continues until it completes a task or reaches a stopping condition.

112. What is the difference between a chatbot and an AI agent?

A basic chatbot mainly responds to messages. An agent can also take actions through tools and make decisions across multiple steps.

113. What is tool calling?

Tool calling allows a model to request a structured operation, such as a database query or API call, through a tool interface.
The application executes the call and returns the result to the model.

114. What is function calling?

Function calling is a common form of tool calling where the model produces structured arguments for a predefined function.

115. What is agent memory?

Agent memory refers to information retained or retrieved across steps or interactions. It can include conversation history, summaries, and external knowledge.

116. What is short-term memory?

Short-term memory maintains information needed within a current conversation or workflow, such as earlier messages and intermediate results.

117. What is long-term memory?

Long-term memory stores information that can be retrieved across separate sessions or tasks, subject to the application's design and permissions.

118. What is LangGraph?

LangGraph is a framework for building stateful, often cyclic workflows involving LLMs, tools, conditional routing, and human approval.

119. Why use LangGraph instead of a simple chain?

A simple chain is suitable for fixed sequential steps. LangGraph is useful when a workflow needs loops, state management, conditional branches, retries, or human intervention.

120. What is a state graph?

A state graph represents a workflow in which nodes perform operations and edges define how control moves between them while shared state is updated.

121. What is a node in LangGraph?

A node is a function or runnable that performs a step in the graph, such as calling an LLM, retrieving documents, or executing a tool.

122. What is an edge in LangGraph?

An edge connects workflow steps and determines which node executes next. Conditional edges select the next step based on state or a decision.

123. What is a conditional edge?

A conditional edge routes execution to different nodes according to a condition, such as whether the agent needs a tool.

124. What is a human-in-the-loop workflow?

It inserts human review or approval into a workflow before selected actions continue, particularly when actions are risky or irreversible.

125. What is an autonomous agent?

An autonomous agent can make decisions and execute multiple steps with limited ongoing human direction, within its configured permissions and constraints.

126. What is multi-agent architecture?

It uses multiple agents or specialized model-driven components that collaborate or divide tasks.

127. What are the challenges of multi-agent systems?

Challenges include coordination, duplicated work, conflicting outputs, increased latency, higher costs, difficult debugging, and security risks.

128. What is ReAct?

ReAct stands for Reasoning and Acting. It is a pattern that interleaves model-driven decisions with tool actions and observations.

129. How do you prevent an agent from entering an infinite loop?

Set step limits, timeouts, budgets, explicit stopping conditions, repeated-action detection, and fallbacks when progress stalls.

130. How do you secure agent tool calls?

Validate arguments, enforce server-side authorization, use least-privilege credentials, restrict available tools,
require approval for sensitive actions, and log operations.

Part 7: Fine-Tuning and Optimization (131–145)
131. What is fine-tuning?

Fine-tuning adapts a pretrained model through additional training on a task-specific dataset.

132. When should you use RAG instead of fine-tuning?

Use RAG when the model needs access to changing or private factual information. Consider fine-tuning when you need to adapt behavior,
 style, or task-specific patterns. They can also be combined.

133. What is full fine-tuning?

Full fine-tuning updates all or most trainable model parameters during additional training.
It typically requires more memory and compute than parameter-efficient methods.

134. What is PEFT?

Parameter-Efficient Fine-Tuning adapts a model by training a relatively small subset of parameters or additional parameter modules.

135. What is LoRA?

Low-Rank Adaptation introduces trainable low-rank matrices into selected model layers, allowing adaptation without updating all original weights.

136. What is QLoRA?

QLoRA combines quantized base-model weights with trainable low-rank adapters to reduce memory requirements during fine-tuning.

137. What is catastrophic forgetting?

Catastrophic forgetting occurs when training on new data degrades previously learned capabilities.

138. What is a training dataset for fine-tuning?

It is a curated set of examples used to adapt the model, often consisting of instructions and expected responses or task-specific input-output pairs.

139. Why is data quality important in fine-tuning?

Poor, inconsistent, biased, or incorrect examples can teach the model undesirable behavior and reduce generalization.

140. What is overfitting in fine-tuning?

Overfitting occurs when the model adapts too closely to training examples and performs poorly on unseen examples.

141. How do you reduce overfitting?

Use representative data, validation sets, appropriate training duration, regularization where suitable, and evaluation on unseen examples.

142. What is quantization-aware training?

It simulates or accounts for quantization effects during training so the model can better retain performance when deployed at reduced precision.

143. What is distillation?

Knowledge distillation trains a smaller student model to reproduce useful behavior or outputs from a larger teacher model.

144. What is the difference between LoRA and full fine-tuning?

LoRA trains small adapter matrices while keeping most base weights frozen.
Full fine-tuning updates the model's broader parameter set and usually requires more compute and storage.

145. How do you decide whether fine-tuning is successful?

Compare the adapted model with the baseline on held-out data using task-specific quality metrics, safety tests, latency, memory consumption, and cost.

Part 8: Evaluation, Safety and Guardrails (146–160)
146. What is LLM evaluation?

LLM evaluation measures how well a model or application performs on defined tasks and requirements.

147. What is BLEU?

BLEU is a metric that compares generated text with reference text using n-gram precision and a brevity penalty.
It is commonly associated with machine translation.

148. What is ROUGE?

ROUGE is a family of metrics used to compare generated text against reference text, often for summarization tasks.

149. What is BERTScore?

BERTScore compares candidate and reference text using contextual token embeddings to estimate semantic similarity.

150. What is an LLM-as-a-judge?

It uses an LLM to evaluate another model's responses against criteria such as relevance, correctness, or instruction following.
 Its judgments should be validated because they can be biased or inconsistent.

151. What is faithfulness in RAG?

Faithfulness measures whether an answer's claims are supported by the retrieved evidence.

152. What is answer relevance?

Answer relevance measures how well a response addresses the user's actual question.

153. What is context precision?

Context precision measures how much of the retrieved context is relevant, accounting for the ranking of relevant items.

154. What is context recall?

Context recall measures whether the retrieved evidence covers the information needed to answer the question, often judged against reference evidence.

155. What are guardrails in GenAI?

Guardrails are controls that enforce application rules, such as output validation, access restrictions, safety checks, and limits on tool execution.

156. What is PII?

Personally Identifiable Information is information that can identify a person, directly or in combination with other data.
 Applications may need to detect, protect, or redact it.

157. What is data leakage in a GenAI application?

Data leakage occurs when information is exposed to unauthorized users or systems, or when evaluation data unintentionally contaminates training or testing.

158. What is grounding?

Grounding connects a model's answer to specified evidence, such as retrieved documents or verified database results.

159. How do you test a RAG chatbot before release?

Build a representative test set, check retrieval and answer quality, test hallucinations and adversarial inputs, verify access controls,
 measure latency and cost, and conduct regression testing.

160. How do you handle a question when the answer is not in the documents?

Instruct the application to acknowledge insufficient evidence instead of inventing an answer.
You can also offer a permitted alternative source or escalate to a human.

Part 9: Deployment, MLOps and Production (161–180)
161. What is FastAPI?

FastAPI is a Python framework for building APIs with request validation, type hints, and support for asynchronous endpoints.

162. Why use FastAPI for GenAI applications?

It can expose model inference, RAG, and agent workflows through HTTP endpoints that other applications can call.

163. What is Docker?

Docker packages an application and its dependencies into a container image so it can run consistently across compatible environments.

164. Why use Docker for LLM applications?

It helps standardize deployment, dependency management, isolation, and scaling.
Large models and hardware dependencies still need separate resource planning.

165. What is CI/CD?

Continuous Integration and Continuous Delivery or Deployment automate stages such as testing, building, and releasing software.

166. What is model monitoring?

Model monitoring tracks application and model behavior after deployment, including quality, latency, errors, resource use, and potentially data or performance drift.

167. What is latency in a GenAI application?

Latency is the time required to produce a response. It may include retrieval time, model startup, prompt processing, generation, and network overhead.

168. What is time to first token?

Time to first token is the time from initiating a request until the first generated token is delivered to the user.

169. What is throughput?

Throughput measures how much work a system processes in a given period, such as requests per second or generated tokens per second.

170. What is batching?

Batching groups multiple inputs or requests into one processing operation to improve resource utilization.
 It can affect latency and depends on the serving system.

171. What is caching in a GenAI application?

Caching stores reusable results, such as embeddings, retrieval results, or exact response outputs, to avoid repeated computation.
 Cache keys and permissions must be designed carefully.

172. How do you reduce LLM API costs?

Use appropriately sized models, shorten unnecessary context, cache suitable results, optimize retrieval, limit redundant calls, and monitor token consumption.

173. How do you improve RAG response speed?

Optimize document retrieval, use suitable indexes, reduce unnecessary retrieved chunks, cache embeddings or results where appropriate, stream responses, and profile model latency.

174. What is asynchronous programming in FastAPI?

Asynchronous programming allows supported I/O operations to yield control while waiting, helping a server handle concurrent requests.
 It does not automatically make CPU-heavy or model inference work faster.

175. How do you handle rate limits?

Apply bounded retries with exponential backoff and jitter, respect provider retry guidance, limit concurrency,
 queue requests when appropriate, and return controlled errors.

176. What is observability?

Observability combines logs, metrics, and traces to help understand system behavior and diagnose failures.

177. What should you log in a production RAG application?

Log request IDs, timings, errors, retrieval metadata, model configuration, token usage, and evaluation signals.
 Avoid recording sensitive prompts or personal information unnecessarily.

178. What is model drift?

Model or data drift refers to changes in input patterns or the relationship between inputs and expected outcomes that can degrade performance.
 A fixed LLM can also be affected by changes in upstream data, prompts, or model-provider versions.

179. How do you deploy a GenAI application to the cloud?

Package the application, configure secrets and permissions, deploy to a suitable compute service, connect the model and data stores, enable monitoring, and test security, scalability, and reliability.

180. How do you manage secrets in production?

Use a secrets manager or secure environment configuration, apply least privilege, rotate credentials, and never commit API keys or passwords to source control.

Part 10: Project and Scenario-Based Questions (181–200)
These questions are especially useful when interviewers ask you to explain the GenAI projects on your resume.

181. Explain a RAG project you have worked on.

A strong answer structure is:

"I built a document question-answering application. It loads and processes documents, splits them into chunks,
creates embeddings, and stores them in a vector database. When a user asks a question, the system retrieves relevant chunks
 and supplies them to an LLM to generate an answer grounded in the available context."

Customize this answer to match what you have actually implemented.

182. Why did you choose RAG for your project?

"I chose RAG because the application needed to answer questions using external documents.
 RAG allowed me to update the knowledge base without retraining the entire language model and helped ground responses in retrieved information."

183. Explain the complete RAG architecture.

A typical architecture is:

Documents → Loaders → Chunking → Embeddings → Vector Store → Retriever → Prompt + Context → LLM → Response

Production systems may add hybrid search, reranking, citations, evaluation, and access-control checks.

184. How do you handle PDF documents in a RAG application?

Load the PDFs with an appropriate parser, extract and clean the text, 
preserve useful metadata such as page numbers, split the content, create embeddings, and index the chunks.
Inspect scanned PDFs separately because they may require OCR.

185. What if a PDF contains tables?

Use a parser that preserves table structure, or extract tables separately and represent them in a format suitable for retrieval.
Validate the extracted values against the source PDF.

186. What if the retriever returns irrelevant chunks?

Check the chunking strategy, embedding model, similarity metric, query wording, metadata filters, and top-k value.
Test hybrid retrieval or reranking and measure the effect using a labeled test set.

187. What if the LLM ignores the retrieved context?

Improve the prompt to prioritize the supplied evidence, clearly separate it from user instructions, request citations or supporting passages,
 and instruct the model to abstain when evidence is insufficient. Evaluate whether the context itself contains the answer.

188. How do you add citations to RAG answers?

Preserve source identifiers and page numbers in document metadata. Pass that information through retrieval and generation,
then validate that cited sources actually support the associated claims.

189. How do you support multiple users in a RAG application?

Authenticate users, enforce document-level authorization before returning retrieval results, isolate or filter data by permissions,
 and test for cross-user information leakage.

190. How do you update a RAG knowledge base?

Detect new, changed, and deleted documents; process the changes; regenerate affected chunks and embeddings; update the index;
and remove obsolete records. Use stable document IDs and versioning to avoid duplicate or stale content.

191. How would you build a customer-support GenAI chatbot?

Connect trusted product documentation and support policies to a RAG pipeline. Add conversation context, structured responses,
authentication, escalation to a human, evaluation, and monitoring.

192. How would you build a Text-to-SQL application?

Use an LLM to translate natural-language questions into SQL based on the database schema. Validate the generated query,
 enforce read-only permissions where possible, restrict tables and operations, execute it safely, and present the results.
 Never rely on the LLM alone for database security.

193. How would you build a chatbot using Ollama?

Run a compatible model locally using Ollama, integrate it through a supported Python interface such as LangChain, create a prompt or RAG pipeline,
expose it through an API or Streamlit interface, and evaluate response quality and local resource usage.

194. What would you do if your RAG application became slow?

Measure the latency of each component separately. Check embedding generation, vector search, reranking, model generation, and network calls.
 Optimize the slowest stage rather than changing the entire architecture blindly.

195. What would you do if your application gave different answers to the same question?

Check temperature and sampling settings, prompt consistency, retrieval stability, changing source data, model versions, and concurrency.
Use repeatable evaluation tests and deterministic settings where supported, while recognizing that exact reproducibility is not always guaranteed.

196. How would you protect a GenAI application against malicious documents?

Treat retrieved documents as untrusted data, separate their contents from system instructions,
restrict tool permissions, scan or validate content when appropriate, and test for prompt injection and unauthorized actions.

197. How do you evaluate a GenAI project on your resume?

Describe a defined test dataset, baseline, relevant retrieval and answer-quality metrics, error analysis, and performance measurements.
 Report actual results only; do not invent accuracy improvements or business impact.

198. How would you explain your role in a GenAI project?

Explain which components you personally built, why you chose the tools, how data flows through the system, how you tested it,
 what challenges you faced, and what you would improve. Clearly distinguish your own work from team contributions.

199. What are the biggest challenges in production GenAI applications?

Common challenges include hallucinations, poor retrieval, data privacy, prompt injection, latency, API cost, evaluation difficulty,
 inconsistent outputs, and monitoring. Each requires appropriate technical controls and testing.

200. Why should we hire you as a GenAI Engineer?

Use an answer that reflects your actual skills and experience. For example:

"I have a foundation in AI and machine learning and practical experience building Python-based applications.
 I understand the core components of LLM applications, including prompt engineering, embeddings, RAG, vector databases, and API integration.
 I focus on building solutions that are testable, reliable, and maintainable, and I am continuing to strengthen my production deployment and evaluation skills."

```
