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
