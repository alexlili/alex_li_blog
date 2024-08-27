title: 'Intro Pointers and Their Role:'
author: Alex Li
tags: []
categories:
  - backend
date: 2023-11-27 00:33:50
---
#### Introduction to Pointers and Their Role:
a. Declare a pointer variable to an integer named ptr.
b. Assign the address of an integer variable to the pointer ptr.
c. Use the pointer to modify the value of the integer variable.
d. Create a pointer to an array and access its elements.
e. Write a function that takes a pointer to an integer and doubles its value
```c++
#include <iostream>

// e. Write a function that takes a pointer to an integer and doubles its value.
void doubleValue(int* ptr) {
    *ptr *= 2;
}

int main() {
    // a. Declare a pointer variable to an integer named ptr.
    int* ptr;

    // b. Assign the address of an integer variable to the pointer ptr.
    int number = 42;
    ptr = &number;

    // c. Use the pointer to modify the value of the integer variable.
    std::cout << "Original value: " << number << std::endl;
    *ptr = 99;
    std::cout << "Modified value using pointer: " << number << std::endl;

    // d. Create a pointer to an array and access its elements.
    const int arraySize = 5;
    int intArray[arraySize] = {1, 2, 3, 4, 5};
    int* arrayPtr = intArray;

    std::cout << "Accessing elements of the array using a pointer:\n";
    for (int i = 0; i < arraySize; ++i) {
        std::cout << "Element " << i << ": " << *(arrayPtr + i) << std::endl;
    }

    // e. Call the function to double the value using a pointer.
    int valueToDouble = 7;
    int* valuePtr = &valueToDouble;

    std::cout << "\nOriginal value before function call: " << valueToDouble << std::endl;
    doubleValue(valuePtr);
    std::cout << "Value after doubling using function: " << valueToDouble << std::endl;

    return 0;
}

```