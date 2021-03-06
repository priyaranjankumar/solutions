# Last Digit of the Sum of Fibonacci Numbers Again

## Problem Introduction

Now, we would like to find the last digit of a partial sum of Fibonacci numbers: ๐น<sub>m</sub> + ๐น<sub>m+1</sub> + ยท ยท ยท + ๐น<sub>n</sub>

## Problem Description

**Task.** Given two non-negative integers ๐ and ๐, where ๐ โค ๐, find the last digit of the sum ๐น๐ + ๐น๐+1 +
ยท ยท ยท + ๐น๐.

**Input Format.** The input consists of two non-negative integers ๐ and ๐ separated by a space.

**Constraints.** 0 โค ๐ โค ๐ โค 1014

**Output Format.**

```md
Output the last digit of ๐น๐ + ๐น๐+1 + ยท ยท ยท + ๐น๐.
```

**Sample 1.**

```md
Input:
3 7
Output:
1
๐น3 + ๐น4 + ๐น5 + ๐น6 + ๐น7 = 2 + 3 + 5 + 8 + 13 = 31.
```

**Sample 2.**

```md
Input:
10 10
Output:
5
๐น10 = 55.
```

**Sample 3.**

```md
Input:
10 200
Output:
2
๐น10 + ๐น11 + ยท ยท ยท + ๐น200 = 734 544 867 157 818 093 234 908 902 110 449 296 423 262
```

## Solution

```py
def last_digit_sum(n,m):
    sum =0
    list= [0,1]
    for i in range (2,m+1):
        list.append((list[i-1]+list[i-2])%10)
    # list with containing last digit of the number is created
    for i in range (n,m+1):
        sum+=list[i]

    return sum%10


def reducer(n,m):
    n=n%60
    m=m%60
    if(n>m):

        return last_digit_sum(n,60) +last_digit_sum(0,m)

    else:

        return last_digit_sum(n,m)


input_n, input_m = map(int, input().split())
print(reducer(input_n,input_m))
```
