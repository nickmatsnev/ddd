---
title: Binary Representation of a Number Without Leading Zeros
date: 2018-12-27
languages: [C#]
scripts: [relative_date.js]
styles: [prism.css]
description: We need to output number binary representation without leading zeros.
---
 
## Task

We need to output `number` binary representation without leading zeros.

| Input | Output |
| :---- | :----- |
| 5     | 101    |
| 55    | 103    |
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

Or you can either use `Marshal.SizeOf()` function so that you don’t have to depend on the variable size. We multiply the result by 8 to get the number of bits. You should also add `using System.Runtime.InteropServices`.

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

Due to the fact that comparing a number that contains only zeros with the `0xFF` mask will give us **0**, we can use it this task.

1.  Shift the `number` to the right by **15, 14..0** places in the loop from **15** to **0** (size of `short`) or calculate it dynamically.
2.  Apply the `0xFF` mask.
3.  If the result of the comparison is non-zero, output the value of this bit.