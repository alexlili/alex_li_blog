title: Return Types and Void Functions
author: Alex Li
date: 2023-11-27 00:51:37
tags:
---
#### Return Types and Void Functions:
a. Define a function calculateArea that takes the radius of a circle as a parameter and returns the area of the circle.
b. Write a function divideNumbers that takes two doubles as parameters and returns the result of their division.
c. Create a function printRectangle that takes two integers (width and height) as parameters and prints a rectangle of asterisks. The function should be of type void.
d. Define a function findRoots that takes three parameters (a, b, c) representing a quadratic equation. Return the roots of the equation (use the quadratic formula). If there are no real roots, return an error message.
e. Write a function displayMessage that takes a string as a parameter and displays it on the screen. The function should have a return type of void.
```c++
#include <iostream>
#include <cmath>

// a. Calculate the area of a circle
double calculateArea(double radius) {
    return 3.14 * radius * radius;
}

// b. Divide two numbers
double divideNumbers(double a, double b) {
    if (b != 0) {
        return a / b;
    } else {
        std::cerr << "Error: Division by zero." << std::endl;
        return 0;  // Returning 0 as an error indicator; you may choose a different approach
    }
}

// c. Print a rectangle of asterisks
void printRectangle(int width, int height) {
    for (int i = 0; i < height; ++i) {
        for (int j = 0; j < width; ++j) {
            std::cout << "* ";
        }
        std::cout << std::endl;
    }
}

// d. Find roots of a quadratic equation
void findRoots(double a, double b, double c) {
    double discriminant = b * b - 4 * a * c;
    
    if (discriminant > 0) {
        double root1 = (-b + sqrt(discriminant)) / (2 * a);
        double root2 = (-b - sqrt(discriminant)) / (2 * a);
        std::cout << "Root 1: " << root1 << "\nRoot 2: " << root2 << std::endl;
    } else if (discriminant == 0) {
        double root = -b / (2 * a);
        std::cout << "Double root: " << root << std::endl;
    } else {
        std::cerr << "No real roots." << std::endl;
    }
}

// e. Display a message
void displayMessage(const std::string& message) {
    std::cout << message << std::endl;
}

int main() {
    // Example usages of the functions
    double circleRadius = 5.0;
    std::cout << "Area of circle with radius " << circleRadius << ": " << calculateArea(circleRadius) << std::endl;

    double dividend = 10.0, divisor = 2.0;
    std::cout << "Division result: " << divideNumbers(dividend, divisor) << std::endl;

    int rectangleWidth = 4, rectangleHeight = 3;
    std::cout << "Rectangle of asterisks:\n";
    printRectangle(rectangleWidth, rectangleHeight);

    double quadraticA = 1.0, quadraticB = -3.0, quadraticC = 2.0;
    findRoots(quadraticA, quadraticB, quadraticC);

    std::string message = "Hello, world!";
    displayMessage(message);

    return 0;
}

```