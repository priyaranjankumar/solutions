# Fibonacci Number Again

## Problem Introduction

In this problem, your goal is to compute 𝐹𝑛 modulo 𝑚, where 𝑛 may be really huge: up to 1014.

For such values of 𝑛, an algorithm looping for 𝑛 iterations will not fit into one second for sure. Therefore we need to
avoid such a loop.

## Problem Description

**Task.** Given two integers 𝑛 and 𝑚, output 𝐹𝑛 mod 𝑚 (that is, the remainder of 𝐹𝑛 when divided by 𝑚).

**Input Format.** The input consists of two integers 𝑛 and 𝑚 given on the same line (separated by a space).

**Constraints.** 1 ≤ 𝑛 ≤ 1014
, 2 ≤ 𝑚 ≤ 103
.

**Output Format.**

```md
Output 𝐹𝑛 mod 𝑚.
```

**Sample 1.**

```md
Input:
239 1000
Output:
161
𝐹239 mod 1 000 = 39 679 027 332 006 820 581 608 740 953 902 289 877 834 488 152 161 (mod 1 000) = 161.
```

**Sample 2.**

```md
Input:
2816213588 239
Output:
151
𝐹2 816 213 588 does not fit into one page of this file, but 𝐹2 816 213 588 mod 239 = 151.
```

## Solution

```py
def findPisanoPeriod(m):
    previous,current = 0,1
    for i in range (0,m*m):
        previous ,current = current, (previous+current)%m
        if(previous==0 and current==1):
            return i+1

def fibonacci_number_again(n,m):
    temp = n % findPisanoPeriod(m)
    list = [0,1]
    for i in range (2,temp+1):
        list.append( list[i-1]+list[i-2])
    return list[temp]%m


input_n, input_m = map(int, input().split())
print(fibonacci_number_again(input_n,input_m))
```
