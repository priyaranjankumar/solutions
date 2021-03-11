# Least Common Multiple

## Problem Introduction

The least common multiple of two positive integers 𝑎 and 𝑏 is the least positive
integer 𝑚 that is divisible by both 𝑎 and 𝑏.

## Problem Description

**Task.** Given two integers 𝑎 and 𝑏, find their least common multiple.

**Input Format.** The two integers 𝑎 and 𝑏 are given in the same line separated by space.

**Constraints.** 1 ≤ 𝑎, 𝑏 ≤ 107

**Output Format.** Output the least common multiple of 𝑎 and 𝑏.

**Sample 1.**

```md
Input:
6 8
Output:
24
Among all the positive integers that are divisible by both 6 and 8 (e.g., 48, 480, 24), 24 is the smallest
one.
```

**Sample 2.**

```md
Input:
761457 614573
Output:
467970912861
```

## Solution

```py
def gcd(a,b):
    if(b==0):
        return a
    else:
        return gcd(b,a%b)

def lcm(a,b):
    if(b>a):
        lcm(b,a)
    p = gcd(a,b)
    return int((a*b)/p)

input_a, input_b = map(int, input().split())
print(lcm(input_a, input_b))
```
