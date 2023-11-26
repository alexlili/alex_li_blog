title: c++ Definition Functions
author: Alex Li
date: 2023-11-27 00:22:52
tags:
---
#### Definition and Declaration of Functions:
a. Define a function called greet that prints "Hello, World!" to the console.
b. Create a function named calculateSum that takes two integers as parameters and returns their sum.
c. Write a function printArray that takes an array of integers and its size as parameters and prints all the elements.
d. Define a function findMax that takes two doubles as parameters and returns the larger value.
e. Create a function isEven that takes an integer as a parameter and returns true if it's even, otherwise false.

```c++
#include <iostream>

void greet() {
    std::cout << "Hello, World!" << std::endl;
}

// Declaration (not necessary in this case, as the function is defined above)
// void greet();
int calculateSum(int a, int b) {
    return a + b;
}

// Declaration (not necessary in this case, as the function is defined above)
// int calculateSum(int a, int b);
#include <iostream>

void printArray(int arr[], int size) {
    for (int i = 0; i < size; ++i) {
        std::cout << arr[i] << " ";
    }
    std::cout << std::endl;
}

// Declaration (not necessary in this case, as the function is defined above)
// void printArray(int arr[], int size);
double findMax(double a, double b) {
    return (a > b) ? a : b;
}

// Declaration (not necessary in this case, as the function is defined above)
// double findMax(double a, double b);
bool isEven(int num) {
    return (num % 2 == 0);
}

// Declaration (not necessary in this case, as the function is defined above)
// bool isEven(int num);


```