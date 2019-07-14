---
title: Convert a String to an Integer Array
date: 2019-07-14
languages: [C#]
description: Convert a string of space-delimited numbers to an integer array.
---

## Task

Convert a string of space-delimited numbers to an integer array.

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

Create two arrays: `temp` and `res`. 

1. Split the given string into substrings based on space (or multiple spaces–`StringSplitOptions.RemoveEmptyEntries` option takes care of them) and put these substrings in `temp`. 
2. `res` is the resulting integer array that the function will return. In the loop every number from the temporary array gets converted to an integer and placed in the resulting array.

Here I expect the given string to contain only integers. Make sure that you handle all possible exceptions before using the above code in production.
