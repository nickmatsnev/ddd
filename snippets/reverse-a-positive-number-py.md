---
title: Reverse a Positive Number
date: 2019-07-17
languages: [Python]
labels: [Production ready]
description: This short snippet will help you reverse given number.
---

## Task

This short snippet will help you reverse given number. It converts the number to a string, writes it backward and converts to a number again.

| Input | Output |
| :---- | :----- |
| 1234  | 4321   |

## Code

```python
def reverse(x):
  if not x.isdigit():
    raise Exception("Invalid input")
  return int(str(x)[::-1])
```

Without using strings:

```python
def reverse(x): 
  if not x.isdigit():
    raise Exception("Invalid input")
  output = 0

  while x > 0:
    lastDigit = x % 10
    output = output * 10 + lastDigit
    x //= 10

  return output
```
