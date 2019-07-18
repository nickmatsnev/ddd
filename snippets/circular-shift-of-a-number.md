---
title: Circular Shift of a Number
date: 2019-07-17
languages: [C#]
description: We need to output the binary representation of the number that was circularly shifted to the right.
---

## Task

We work with the `number` and the number of places to shift the `number` by–`shiftOffset`. We need to output the binary representation of the `number` that was circularly shifted to the right by `shiftOffset` places. Circular shift (also known as bitwise rotation) means that bits that get shifted out on the right will be inserted on the left.

For example, the number is **413**. It has the following binary representation: **0000 0001 1001 1<span style="color: #008000;">101</span>**.  
If we make a circular shift by **3** places to the right we’ll get **<span style="color: #008000;">101</span>0 0000 0011 00<span style="color: #a31515;">11</span>**.  
And if we make one more circular shift by **2** places the result will be the following: **<span style="color: #a31515;">11</span><span style="color: #008000;">10 1</span>000 0000 1100**.

| Input      | Output            |
| :--------- | :---------------- |
| 413<br>3   | 1010000000110011  |
| 5<br>2     | 0100000000000001* |

## Code

```csharp
ushort number = ushort.Parse(Console.ReadLine());
ushort shiftOffset = ushort.Parse(Console.ReadLine());

int shiftedNumber = number >> shiftOffset;
int rightDroppedBits = number << (16 - shiftOffset);
    
int result = shiftedNumber | rightDroppedBits;
    
for (int i = 15; i >= 0; i--)
    Console.Write((result >> i) & 1);

Console.ReadKey();
```

## Algorithm

***Note**: since we deal with the `ushort` variables, even small numbers will have two-byte binary representation (many leading zeros).

1. Shift the number and put the result in the `shiftedNumber` variable. If we look at `shiftedNumber`'s binary representation, we'll notice that first `shiftOffset` number of bits will be set to 0. Indeed:  
100 >> 1 -> 010  
111 >> 1 -> 011  
10111 >> 2 -> 00101
2. During the shift in step 1, we have lost the `shiftOffset` number of bits as they got shifted out on the right end. To make our shift circular we have to get them back in the final number. To achieve this, we move the given number to the left so that the `rightDroppedBits` contains only bits that were lost in the previous step. For example, if we shift 1000011 to the right by 3 places, we lose 011. To save them, we have to turn 1000011 into 011. In order to achieve this we shift the given number to the left by 7 - 3 = 4 places.
3. To get the final number we combine the shifted number's binary representation with the bits that were dropped. To do this we apply bitwise OR on `shiftedNumber` and `rightDroppedBits`. After it, the zero bits we got in step 1 will be replaced by the dropped bits, others will stay intact.
4. Output the final number's binary representation.