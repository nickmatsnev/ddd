---
title: Reverse a Positive Number
date: 2019-07-17
languages: [C#]
description: Write a function to reverse a given number.
---

## Task

Write a function to reverse a given number.

| Input | Output |
| :---- | :----- |
| 1234  | 4321   |

## Code

{{< code-header name="main.cs" >}}
```csharp
static uint ReverseInteger(uint x) 
{
	uint output = 0;

	do
	{
		output = x % 10 + output * 10;
		x /= 10;
	}
	while (x > 0);

	return output;
}
```
