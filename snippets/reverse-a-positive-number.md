---
title: Reverse a Positive Number
modified: 2019-02-18 
language: C#
scripts: [precode_selector.js]
description: Write a function that receives the number x and prints it, “unfolding” its digits in the reverse order.
---

## Task

Write a function that receives the number `x` and prints it, “unfolding” its digits in the reverse order.

| Input | Output |
| :---- | :----- |
| 1234  | 4321   |

## Code

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

## Algorithm
1. Get `x`.
2. Add the last digit of the number `x` to the rightmost digit of the number `output`, which is empty after multiplying by **10**.
3. Divide the number `x` by **10**, getting rid of the last digit.