---
title: Convert a String to an Integer Array
date: 2018-12-27
language: C#
scripts: [precode_selector.js]
description: Parse the string with numbers divided by spaces into an integer array.
---

## Task

Parse the string with numbers divided by spaces into an integer array.

## Code

```csharp
static int[] parseNumbers(string input)
{
    string[] temp = input.Split(new char[] { ' ' }, StringSplitOptions.RemoveEmptyEntries);
    int[] res = new int[temp.Length];

    for (int i = 0; i < temp.Length; i++)
        res[i] = int.Parse(temp[i]);

    return res;
}
```

## Algorithm

1. Get the string `input`, that consists of numbers divided by spaces.
2. Split the string into a string array, so that each element contains a number.
3. In a loop, parse each element of the string array into `int`, filling in the array.
4. Return an integer array.