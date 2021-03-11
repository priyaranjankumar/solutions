# Last Digit of the Sum of Fibonacci Numbers Again

## Problem Introduction

Now, we would like to find the last digit of a partial sum of Fibonacci numbers: 𝐹<sub>m</sub> + 𝐹<sub>m+1</sub> + · · · + 𝐹<sub>n</sub>

## Problem Description

**Task.** Given two non-negative integers 𝑚 and 𝑛, where 𝑚 ≤ 𝑛, find the last digit of the sum 𝐹𝑚 + 𝐹𝑚+1 +
· · · + 𝐹𝑛.

**Input Format.** The input consists of two non-negative integers 𝑚 and 𝑛 separated by a space.

**Constraints.** 0 ≤ 𝑚 ≤ 𝑛 ≤ 1014

**Output Format.**

```md
Output the last digit of 𝐹𝑚 + 𝐹𝑚+1 + · · · + 𝐹𝑛.
```

**Sample 1.**

```md
Input:
3 7
Output:
1
𝐹3 + 𝐹4 + 𝐹5 + 𝐹6 + 𝐹7 = 2 + 3 + 5 + 8 + 13 = 31.
```

**Sample 2.**

```md
Input:
10 10
Output:
5
𝐹10 = 55.
```

**Sample 3.**

```md
Input:
10 200
Output:
2
𝐹10 + 𝐹11 + · · · + 𝐹200 = 734 544 867 157 818 093 234 908 902 110 449 296 423 262
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
