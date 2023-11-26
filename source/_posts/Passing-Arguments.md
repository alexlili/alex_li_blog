title: Passing Arguments
author: Alex Li
date: 2023-11-27 00:50:12
tags:
---
#### Passing Arguments (By Value, By Reference):
a. Write a function incrementByValue that takes an integer parameter and increments it by 1. Call the function and observe the changes.
b. Create a function multiplyByTwo that takes a reference to an integer as a parameter and multiplies it by 2. Print the result.
c. Define a function swapValues that takes two integers by reference and swaps their values. Print the values before and after swapping.
d. Write a function modifyArray that takes an array of doubles and its size as parameters. Multiply each element by 1.5 and print the modified array.
e. Create a function appendText that takes a reference to a string and appends " (Modified)" to it. Print the modified string.

```c++
#include <iostream>
#include <string>

// a. Increment an integer by value
void incrementByValue(int num) {
    num += 1;
}

// b. Multiply an integer by two using reference
void multiplyByTwo(int &num) {
    num *= 2;
}

// c. Swap values of two integers using reference
void swapValues(int &a, int &b) {
    std::cout << "Before swapping: a = " << a << ", b = " << b << std::endl;
    int temp = a;
    a = b;
    b = temp;
    std::cout << "After swapping: a = " << a << ", b = " << b << std::endl;
}

// d. Modify each element of an array of doubles
void modifyArray(double arr[], int size) {
    for (int i = 0; i < size; ++i) {
        arr[i] *= 1.5;
    }
}

// e. Append text to a string using reference
void appendText(std::string &text) {
    text += " (Modified)";
}

int main() {
    // a. Increment by value
    int numA = 5;
    incrementByValue(numA);
    std::cout << "After incrementByValue: " << numA << std::endl;

    // b. Multiply by two using reference
    int numB = 8;
    multiplyByTwo(numB);
    std::cout << "After multiplyByTwo: " << numB << std::endl;

    // c. Swap values using reference
    int a = 10, b = 20;
    swapValues(a, b);

    // d. Modify array of doubles
    const int arraySize = 3;
    double arr[arraySize] = {1.0, 2.0, 3.0};
    modifyArray(arr, arraySize);
    std::cout << "Modified Array: ";
    for (int i = 0; i < arraySize; ++i) {
        std::cout << arr[i] << " ";
    }
    std::cout << std::endl;

    // e. Append text to a string using reference
    std::string text = "Original Text";
    appendText(text);
    std::cout << "Modified Text: " << text << std::endl;

    return 0;
}

```