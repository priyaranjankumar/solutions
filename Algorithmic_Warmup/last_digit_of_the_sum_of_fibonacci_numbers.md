# Last Digit of the Sum of Fibonacci Numbers

## Problem Introduction

The goal in this problem is to find the last digit of a sum of the first ๐ Fibonacci numbers.

## Problem Description

**Task.** Given an integer ๐, find the last digit of the sum ๐น<sub>0</sub> + ๐น<sub>1</sub> + ยท ยท ยท + ๐น<sub>n</sub>

**Input Format**. The input consists of a single integer ๐.

**Constraints.** 0 โค ๐ โค 1014
.
**Output Format.**

```md
Output the last digit of ๐น0 + ๐น1 + ยท ยท ยท + ๐น๐.
```

**Sample 1.**

```md
Input:
3
Output:
4
๐น0 + ๐น1 + ๐น2 + ๐น3 = 0 + 1 + 1 + 2 = 4.
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
