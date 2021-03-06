# Fibonacci Number

## Problem Introduction

Recall the definition of Fibonacci sequence: πΉ0 = 0, πΉ1 = 1, and πΉπ = πΉπβ1 + πΉπβ2 for
π β₯ 2. Your goal in this problem is to implement an efficient algorithm for computing
Fibonacci numbers.

```md
Fibonacci(π):
if π β€ 1:
return π
return Fibonacci(π β 1) + Fibonacci(π β 2)
```

## Problem Description

**Task.**
Given an integer π, find the πth Fibonacci number πΉπ.

**Input Format.** The input consists of a single integer π.
Constraints. 0 β€ π β€ 45.

**Output Format.**

```md
Output πΉπ.
```

**Sample 1.**

```md
Input:
10
Output:
55
πΉ10 = 55.
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

