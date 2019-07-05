---
title: Cyclic Shift of Binary Numbers
date: 2019-01-19
languages: [C#]
scripts: [precode_selector.js, relative_date.js]
description: We need to output the binary representation of the final number after cyclic shifting the number by shiftOffset places to the right.
---

## Task

We work with the `number` and the number of bits to shift `shiftOffset`. We need to output the binary representation of the final number after cyclic shifting the `number` by `shiftOffset` places to the right. With this cyclic shift, bits that drop to the right are added to the left.

| Input      | Output           |
| :--------- | :--------------- |
| 413<br>3   | 1010000000110011 |

## Code

```csharp
ushort number = ushort.Parse(Console.ReadLine());
ushort shiftOffset = ushort.Parse(Console.ReadLine());

for (int i = 15; i >= 0; i--)
    Console.Write((((number << (16 - shiftOffset)) | (number >> shiftOffset)) >> i) & 1);

Console.ReadKey();
```

## Algorithm

For example, initial number **413** has the following binary representation: **0000 0001 1001 1<span style="color: #008000;">101</span>**  
If we make a cyclic shift by **3** places we’ll get **<span style="color: #008000;">101</span>0 0000 0011 00<span style="color: #a31515;">11</span>**  
And if we make another cyclic shift by **2** places the result will be the following **<span style="color: #a31515;">11</span><span style="color: #008000;">10 1</span>000 0000 1100**

1.  Get `number`.
2.  Get `shiftOffset`.
3.  Apply the mask in which bits that drop to the right are shifted to the left border **16 – n**, on a number shifted to the right by `shiftOffset` places.
4.  Output binary representation in the loop, comparing with the `1` mask.

For optimization **3rd** and **4th** steps are combined.