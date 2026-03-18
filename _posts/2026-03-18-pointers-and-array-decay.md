---
title: "Pointers in C: Why sizeof(arr) Doesn't Work as You Think"
excerpt: "Understanding 'Array Decay' and Pass-by-Reference to avoid common memory bugs in C."
categories:
  - Computer Engineering
tags:
  - C Programming
  - Pointers
  - Memory Management
---

In C, the relationship between arrays and pointers is one of the most powerful, yet confusing, concepts for beginners. Let's inspect a common snippet that looks correct but contains two fundamental bugs.

### The Buggy Code
```c
void maxAndMin(int arr[], int max, int min) {
    int size = sizeof(arr) / sizeof(arr[0]); 
    max = arr[0];
    min = arr[0];

    for (int i = 0; i < size; i++) {
        if (max < arr[i]) max = arr[i];
        if (min > arr[i]) min = arr[i];
    }

    printf("size is %d\n", size);
    printf("max = %d and min = %d", max, min);
}

### Problem #1: Array Decay

When you pass an array to a function in C, it decays into a pointer to its first element.

Inside the function, arr is technically an int *. Therefore, sizeof(arr) returns the size of the pointer (usually 8 bytes on a 64-bit system), not the total size of the array. Dividing the pointer size by the size of an integer will result in a "size" calculation that is almost always wrong.
### Problem #2: Pass-by-Value

In the code above, max and min are passed by value. This means the function creates local copies. Any changes made inside the function disappear once the function finishes. To update the original variables in your main() function, you must pass them by reference using pointers.
The Corrected Version

To fix this, we must pass the size explicitly and use pointers (*) to modify the original max and min values.
C

void maxAndMin(int arr[], int size, int *max, int *min) {
    *max = arr[0];
    *min = arr[0];

    for (int i = 1; i < size; i++) {
        if (arr[i] > *max) *max = arr[i];
        if (arr[i] < *min) *min = arr[i];
    }
}

###Key Takeaways

    Always pass the size: Since functions lose the array's size information, always pass it as a separate argument.

    Pointers for Persistence: Use pointers when you want a function to modify variables outside its own scope.

    Array vs. Pointer: Remember that while they are related, an array is a block of memory, while a pointer is just an address.
