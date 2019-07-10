---
title: Cyclic Shift of an Array
date: 2018-12-27
languages: [C#]
scripts: [relative_date.js, code_selector.js]
styles: [prism.css]
description: Write a function that cyclically shifts a given array of k elements to the right.
---

## Task

Write a function that cyclically shifts a given array of `k` elements to the right. Do not use an additional array.

## Code

```csharp
static void Shift(int[] arr, int k)
{
    if (k <= 0) 
        return; 

    int temp = arr[arr.Length - 1]; 

    for (int i = arr.Length - 1; i > 0; i--)
        arr[i] = arr[i - 1];

    arr[0] = temp;

    Shift(arr, k - 1);
}
```

## Algorithm

1. Remember the last element of the array.
2. Move the array to the right by **1** element, assigning each element the value of the previous one.
3. Assign the value of the last element to the first one.
4. Execute the algorithm recursively until the value of `k` becomes zero.