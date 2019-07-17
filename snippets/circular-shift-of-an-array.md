---
title: Circular Shift of an Array
date: 2019-07-17
languages: [C#]
description: Write a function that cicrularly shifts a given array.
---

## Task

Write a function that circularly shifts a given array of `k` elements to the right. Do not use an additional array.

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

I am going to use recursion, so the first thing I should do is create a condition under which the recursion will stop. Then while `k` is greater than 0 (means we haven't shifted the array `k` times):

1. Remember the last element of the array in the `temp` variable in order to make shift circular.
2. Move the array to the right by **1** element (every execution of the shift function will move all array elements to the right by one position). Moving array to the right means that we assign each element the value of the previous one.
3. Assign the value of the last element to the first one.
4. Execute the algorithm recursively until the value of `k` becomes zero.
