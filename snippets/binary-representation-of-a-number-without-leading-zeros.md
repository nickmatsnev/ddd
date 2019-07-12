---
title: Binary Representation of a Number Without Leading Zeros
date: 2019-07-11
languages: [C#]
scripts: [relative_date.js, code_selector.js, anchor.js]
styles: [prism.css]
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
short number = short.Parse(Console.ReadLine());

for (int i = 15; i >= 0; i--)
{
    if (((number >> i) & 0xFF) != 0)
        Console.Write((number >> i) & 1);
}

Console.ReadKey();
```

In order to deal with different variable types consider using `Marshal.SizeOf()` function from the `System.Runtime.InteropServices` namespace:

```csharp
short number = short.Parse(Console.ReadLine());

for (int i = Marshal.SizeOf(number) * 8 - 1; i >= 0; i--)
{
    if (((number >> i) & 0xFF) != 0)
        Console.Write((number >> i) & 1);
}

Console.ReadKey();
```

## Algorithm

The bitwise AND of a number and 0xFF mask has the result 0 only if this number is zero. In the first iteration we deal with the leftmost bit of the given number. If this bit is set to 0, then we skip it. We continue to skip all the bits until the first positive one is found (00 & 0xFF == 0, 000 & 0xFF == 0, but 0001 & 0xFF != 0). All bits after will be printed.