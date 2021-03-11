# Fibonacci Number

## Problem Introduction

Recall the definition of Fibonacci sequence: 𝐹0 = 0, 𝐹1 = 1, and 𝐹𝑖 = 𝐹𝑖−1 + 𝐹𝑖−2 for
𝑖 ≥ 2. Your goal in this problem is to implement an efficient algorithm for computing
Fibonacci numbers.

```md
Fibonacci(𝑛):
if 𝑛 ≤ 1:
return 𝑛
return Fibonacci(𝑛 − 1) + Fibonacci(𝑛 − 2)
```

## Problem Description

**Task.**
Given an integer 𝑛, find the 𝑛th Fibonacci number 𝐹𝑛.

**Input Format.** The input consists of a single integer 𝑛.
Constraints. 0 ≤ 𝑛 ≤ 45.

**Output Format.**

```md
Output 𝐹𝑛.
```

**Sample 1.**

```md
Input:
10
Output:
55
𝐹10 = 55.
```

## Solution

```py
def fibonacci_number(n):
    # Create the list to save the value and intializing the values
    list = [0,1]

    for i in range(2,n+1):
        list.append(list[i-1]+list[i-2])
    return list[n]


input_n = int(input())
print(fibonacci_number(input_n))
```

