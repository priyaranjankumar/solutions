# Last Digit of the Sum of Fibonacci Numbers

## Problem Introduction

The goal in this problem is to find the last digit of a sum of the first 𝑛 Fibonacci numbers.

## Problem Description

**Task.** Given an integer 𝑛, find the last digit of the sum 𝐹<sub>0</sub> + 𝐹<sub>1</sub> + · · · + 𝐹<sub>n</sub>

**Input Format**. The input consists of a single integer 𝑛.

**Constraints.** 0 ≤ 𝑛 ≤ 1014
.
**Output Format.**

```md
Output the last digit of 𝐹0 + 𝐹1 + · · · + 𝐹𝑛.
```

**Sample 1.**

```md
Input:
3
Output:
4
𝐹0 + 𝐹1 + 𝐹2 + 𝐹3 = 0 + 1 + 1 + 2 = 4.
```

**Sample 2.**

```md
Input:
100
Output:
5
The sum is equal to 927 372 692 193 078 999 175, the last digit is 5.
```

## Solution

```py
def last_digit_sum(n):
    n=n%60;
    if(n==0):
        return 0
    if(n==1):
        return 1
    sum =1;
    list= [0,1]
    for i in range (2,n+1):
        list.append(list[i-1]+list[i-2])
        sum+=list[i]%10

    return sum%10

input_n = int(input())
print(last_digit_sum(input_n))
```
