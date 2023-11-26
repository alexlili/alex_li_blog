title: Declaring and Accessing Arrays
author: Alex Li
date: 2023-11-27 00:27:33
tags:
---
#### Declaring and Accessing Arrays:
a. Initialize the scores array with some sample test scores.
b. Input the name into the name array using cin.
c. Set values in the temperatures array using a loop.
d. Initialize the daysOfWeek array with the names of the days.
e. Assign values to the elements of the matrix using nested loops.

```c++
#include <iostream>
#include <string>

int main() {
    // a. Initialize the scores array with some sample test scores.
    const int numScores = 5;
    double scores[numScores] = {90.5, 85.0, 92.5, 88.0, 95.5};

    // b. Input the name into the name array using cin.
    const int nameSize = 20;
    char name[nameSize];
    std::cout << "Enter your name: ";
    std::cin.getline(name, nameSize);

    // c. Set values in the temperatures array using a loop.
    const int numTemperatures = 7;
    int temperatures[numTemperatures];
    std::cout << "Enter temperatures for the week:\n";
    for (int i = 0; i < numTemperatures; ++i) {
        std::cout << "Day " << (i + 1) << ": ";
        std::cin >> temperatures[i];
    }

    // Clear the input buffer
    std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');

    // d. Initialize the daysOfWeek array with the names of the days.
    const int numDays = 7;
    std::string daysOfWeek[numDays] = {"Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"};

    // e. Assign values to the elements of the matrix using nested loops.
    const int numRows = 3;
    const int numCols = 3;
    int matrix[numRows][numCols];

    std::cout << "Enter values for the 3x3 matrix:\n";
    for (int i = 0; i < numRows; ++i) {
        for (int j = 0; j < numCols; ++j) {
            std::cout << "Matrix[" << i << "][" << j << "]: ";
            std::cin >> matrix[i][j];
        }
    }

    // Output information
    std::cout << "\nScores: ";
    for (int i = 0; i < numScores; ++i) {
        std::cout << scores[i] << " ";
    }

    std::cout << "\nName: " << name;

    std::cout << "\nTemperatures: ";
    for (int i = 0; i < numTemperatures; ++i) {
        std::cout << temperatures[i] << " ";
    }

    std::cout << "\nDays of the Week: ";
    for (int i = 0; i < numDays; ++i) {
        std::cout << daysOfWeek[i] << " ";
    }

    std::cout << "\nMatrix:\n";
    for (int i = 0; i < numRows; ++i) {
        for (int j = 0; j < numCols; ++j) {
            std::cout << matrix[i][j] << " ";
        }
        std::cout << std::endl;
    }

    return 0;
}

```