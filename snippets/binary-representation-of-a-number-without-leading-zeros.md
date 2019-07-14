---
title: Binary Representation of a Number Without Leading Zeros
date: 2019-07-14
languages: [C#]
description: We need to output number's binary representation without leading zeros.
---
 
## Task

We need to output number's binary representation without leading zeros.

| Input | Output |
| :---- | :----- |
| 5     | 101    |
| 55    | 110111 |
| 103   | 1100111|

## Code

```csharp
int number = int.Parse(Console.ReadLine());
// Get the size of number variable (number of bits)
int size = BitConverter.GetBytes(number).Length * 8;

for (int i = size - 1; i >= 0; i--)
{
    if (((number >> i) & 0xFF) != 0)
        Console.Write((number >> i) & 1);
}

Console.ReadKey();
```

## Algorithm

The bitwise AND of a number and 0xFF mask has the result 0 only if this number is zero. In the first iteration we deal with the leftmost bit of the given number. If this bit is set to 0, then we skip it. We continue to skip all the bits until the first positive one is found (00 & 0xFF == 0, 000 & 0xFF == 0, but 0001 & 0xFF != 0). All bits going after will be printed.
