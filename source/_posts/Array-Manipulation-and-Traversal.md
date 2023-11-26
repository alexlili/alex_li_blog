title: Array Manipulation and Traversal
author: Alex Li
date: 2023-11-27 00:32:20
tags:
---
#### Array Manipulation and Traversal:
a. Calculate the average of the scores array.
b. Convert all characters in the name to uppercase.
c. Find the highest temperature in the temperatures array.
d. Print the days of the week in reverse order.
e. Transpose the matrix (swap rows and columns).

```c++
#include <iostream>
#include <iomanip>
#include <cstring>

int main() {
    // a. Calculate the average of the scores array.
    const int numScores = 5;
    double scores[numScores] = {90.5, 85.0, 92.5, 88.0, 95.5};
    double sum = 0.0;
    for (int i = 0; i < numScores; ++i) {
        sum += scores[i];
    }
    double average = sum / numScores;

    // b. Convert all characters in the name to uppercase.
    const int nameSize = 20;
    char name[nameSize];
    std::cout << "Enter your name: ";
    std::cin.getline(name, nameSize);
    for (int i = 0; i < strlen(name); ++i) {
        name[i] = toupper(name[i]);
    }

    // c. Find the highest temperature in the temperatures array.
    const int numTemperatures = 7;
    int temperatures[numTemperatures];
    std::cout << "Enter temperatures for the week:\n";
    for (int i = 0; i < numTemperatures; ++i) {
        std::cout << "Day " << (i + 1) << ": ";
        std::cin >> temperatures[i];
    }
    int maxTemperature = temperatures[0];
    for (int i = 1; i < numTemperatures; ++i) {
        if (temperatures[i] > maxTemperature) {
            maxTemperature = temperatures[i];
        }
    }

    // Clear the input buffer
    std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');

    // d. Print the days of the week in reverse order.
    const int numDays = 7;
    std::string daysOfWeek[numDays] = {"Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"};
    std::cout << "Days of the week in reverse order:\n";
    for (int i = numDays - 1; i >= 0; --i) {
        std::cout << daysOfWeek[i] << " ";
    }
    std::cout << std::endl;

    // e. Transpose the matrix (swap rows and columns).
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

    // Transpose the matrix
    int transposedMatrix[numCols][numRows];
    for (int i = 0; i < numRows; ++i) {
        for (int j = 0; j < numCols; ++j) {
            transposedMatrix[j][i] = matrix[i][j];
        }
    }

    // Output information
    std::cout << "\nAverage of Scores: " << average << std::fixed << std::setprecision(2);

    std::cout << "\nUppercase Name: " << name;

    std::cout << "\nHighest Temperature: " << maxTemperature;

    return 0;
}

```