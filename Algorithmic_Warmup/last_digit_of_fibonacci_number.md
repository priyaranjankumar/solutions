# Last Digit of a Large Fibonacci Number

## Problem Introduction

Your goal in this problem is to find the last digit of π-th Fibonacci number. Recall that Fibonacci numbers
grow exponentially fast. For example,

```md
πΉ200 = 280 571 172 992 510 140 037 611 932 413 038 677 189 525 .
```

## Problem Description

**Task.** Given an integer π, find the last digit of the πth Fibonacci number πΉπ (that is, πΉπ mod 10).

**Input Format.** The input consists of a single integer π.
**Constraints.** 0 β€ π β€ 107.

**Output Format.** Output the last digit of πΉπ.
**Sample 1.**

```md
Input:
3
Output:
2
πΉ3 = 2.
```

```md
**Sample 2.**
Input:
331
Output:
9
πΉ331 = 668 996 615 388 005 031 531 000 081 241 745 415 306 766 517 246 774 551 964 595 292 186 469.
```

```md
**Sample 3.**
Input:
327305
Output:
5
πΉ327305 does not fit into one line of this pdf, but its last digit is equal to 5.
```

## Solution

```py
def last_digit_of_fibonacci_number(n):
    #Pisano Period for 10 is 60
    # Reducing the size of n
    temp = n%60
    list = [0,1]
    for i in range (2,temp+1):
        list.append( list[i-1]+list[i-2])


    return list[temp]%10

input_n = int(input())

print(last_digit_of_fibonacci_number(input_n))
```
