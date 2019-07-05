---
title: Reverse a Positive Number
date: 2019-05-04
language: Python
scripts: [precode_selector.js]
description: This short snippet will help you reverse any number you are given.
---

## Task

This short snippet will help you reverse any number you are given. It converts the number to a string, writes it backward and converts to a number again.

| Input | Output |
| :---- | :----- |
| 1234  | 4321   |

## Code

```python
def reverse(x):
  return int(str(x)[::-1]);
```

Or a pure integer implementation:

```python
def reverse(x): 
  output = 0

  while x > 0:
    output = x % 10 + output * 10
    x //= 10

  return output
```