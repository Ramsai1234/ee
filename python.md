```
# # Level 1 — Basic Python coding (1–15)
# # 1. Check whether a number is even or odd
# num = int(input("enter the number:"))
# if num % 2 ==0:
#   print(f"{num} is even number")
# else:
#   print(f"{num} is odd number")

# # 2. Find the largest of three numbers

# a=int(input("enter the first number:"))
# b=int(input("enter the second number:"))
# c=int(input("enter the third number:"))

# if a>b:
#   print(f"{a} is largest number")
# elif b>c:
#   print(f"{b} is largest number")
# else:
#   print(f" third number {c} is the largest number")
# 3. Swap two numbers without a third variable
# a=int(input("enter the number:"))
# b=int(input("enter the number:"))

# a,b=b,a
# print(a,b)

# # 4 Find the factorial of a number
# def factorial(num):
#   if num == 0 or num==1:
#     return 1
#   return num * factorial(num-1)

# num = int(input("enter the number:"))
# print("Factorial :", factorial(num))

# n=5
# fact=1

# for i in range (1,n+1):
#   fact *= i

# print(fact)

## print fibnocaai series

# a,b=0,1

# for i in range(10):
#   print(a, end=" ")

#   a,b = b, a+b

## check the number is prime number
# def is_prime(num):
#   if num<=1:
#     return False
#     for i in range(2,num):
#       if num%i==0:
#         return False
#     return True

# num = int(input("enter the number:"))
# if is_prime(num):
#   print("prime number")
# else:
#   print("not a prime number")


  
# reverse a number

# num = 23323
# rev =0

# while num>0:
#   digit = num % 10 
#   rev = rev * 10+digit 
#   num //= 10

# print(rev)

# # ## finding the sum of the digits 
# num = 1234
# total= 0

# while num>0:
#   total += num % 10 
#   num //= 10

# print(total)
  
# 9 check weather the number and digit is a palindrome or not
# num = 121

# if str(num) == str(num)[::-1]:
#   print("palindrome")
# else:
#   print("Not a pliandromee")

# str = "madam"

# if str == str[::-1]:
#   print("palindrome")
# else:
#   print("Not a pliandromee")

# # AMstrong number
# num = 153
# original = num
# total = 0

# while num > 0:
#   digit = num % 10
#   total += digit ** 3
#   num //= 10

# print("Amstrong" if total==original else "not Amstrong")


# num = 5

# for i in range(1, 11):
#     print(num, "x", i, "=", num * i)



```
