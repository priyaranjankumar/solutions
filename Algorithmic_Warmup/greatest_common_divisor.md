# Greatest Common Divisor

## Problem Introduction

The greatest common divisor GCD(๐, ๐) of two non-negative integers ๐ and ๐
(which are not both equal to 0) is the greatest integer ๐ that divides both ๐ and ๐.
Your goal in this problem is to implement the Euclidean algorithm for computing
the greatest common divisor.
Efficient algorithm for computing the greatest common divisor is an important
basic primitive of commonly used cryptographic algorithms like RSA.

```md
GCD(1344, 217)
= GCD(217, 42)
= GCD(42, 7)
= GCD(7, 0)
=7
```

## Problem Description

**Task.** Given two integers ๐ and ๐, find their greatest common divisor.

**Input Format.** The two integers ๐, ๐ are given in the same line separated by space.

**Constraints.** 1 โค ๐, ๐ โค 2 ยท 10^9

**Output Format.**

```md
Output GCD(๐, ๐).
```

**Sample 1.**

```md
Input:
18 35
Output:
1
18 and 35 do not have common non-trivial divisors.
```

**Sample 2.**

```md
Input:
28851538 1183019
Output:
17657
28851538 = 17657 ยท 1634, 1183019 = 17657 ยท 67.
```

## Solution

```py
def gcd(a,b):
    if b==0:
        return a

    else:
        return gcd(b, a/b)

input_a, input_b = map(int, input().split())
print(gcd(input_a, input_b))
```
