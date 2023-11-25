title: YOOBEE-WEEK2-ACTIVITY
author: Alex Li
tags:
  - C++
categories:
  - algorithm
date: 2023-11-17 13:12:18
---
## Control structure
### a.Write a C++ program to check whether a given number is even or odd using the if statement.

```c++
int main()
{
    int number;
    
    std::cout << "enter a number" << std::endl;
    
    std::cin >> number;
    
    std::cout << "you input " << number << std::endl;
    
    if(number%2==0){
        std::cout << number << " is even" << std::endl;
    } else{
        std::cout << number << " is odd" << std::endl;
    }

    return 0;
}
```

### b. Create a program that prompts the user for their age and displays whether they are a child, teenager, or adult using the if-else statement.

```c++
int main()
{
    int number;
    
    std::cout << "enter his/her age" << std::endl;
    
    std::cin >> number;
    
    std::cout << "you input " << number << std::endl;
    
    if(number<=8){
        std::cout << " his/her is a child" << std::endl;
    } else if(number>8&&number<=18){
        std::cout << " his/her is a teenager" << std::endl;
    }else{
        std::cout << " his/her is an adult" << std::endl;
    }

    return 0;
}
```
### c. Implement a menu-driven program that performs basic arithmetic operations (addition, subtraction, multiplication, division) based on user input. Use a switch statement for the menu selection.

```c++
#include <iostream>

// using namespace std;

int main()
{
    char operation;
    int number1, number2;
    
    std::cout << "menu \n";
    std::cout << "1, addition" ;
    std::cout << "2, subtraction" ;
    std::cout << "3, multiplication" ;
    std::cout << "4, division" ;
    
    std::cout << "please select the type of operation(1-4)" ;
    std::cin >> operation;
    
    std::cout << "please input the first number" ;
    std::cin >> number1;
    std::cout << "please input the second number" ;
    std::cin >> number2;
    
    switch(operation){
        case '1':
        std::cout << "the result is "<< number1+number2 << std::endl;
        break;
        case '2':
        std::cout << "the result is "<< number1-number2 << std::endl;
        break;
        case '3':
        std::cout << "the result is "<< number1*number2 << std::endl;
        break;
        case '4':
        if(number2==0){
            std::cout << "Error: Division by zero is undefined.\n";
        }else{
            std::cout << "the result is "<< number1/number2 << std::endl;
        }
        break;
        default:
        std::cout << "Please input a number between 1-4.\n";
        
    }
    return 0;
}
```
## Conditional statements
### a. Write a program that takes three integer inputs and finds the largest of the three using if-else statements.
```c++
#include <iostream>

// using namespace std;

int main()
{
    int number1, number2, number3;
    int temp;
    
    std::cout << "please input the first number" ;
    std::cin >> number1;
    std::cout << "please input the second number" ;
    std::cin >> number2;
    if(number2>=number1){
        temp=number2;
    }else{
        temp=number2;
    }
    std::cout << "please input the third number" ;
    std::cin >> number3;
     if(temp>=number3){
        std::cout << "the largest number is "<< temp << std::endl;
    }else{
        std::cout << "the largest number is "<< number3 << std::endl;
    }
    
    return 0;
}
```
### b. Create a simple calculator program that allows the user to input two numbers and an arithmetic operator (+, -, *, or /) to perform the operation using if-else statements.
```c++
#include <iostream>

// using namespace std;

int main()
{
    int number1, number2;
    char operation;
    
    
    std::cout << "please input the first number" ;
    std::cin >> number1;
    std::cout << "please input an arithmetic operator" ;
    std::cin >> operation ;
    std::cout << "please input the second number" ;
    std::cin >> number2;

    if(operation=='+'){
        std::cout << "the result is "<< number1 + number2 << std::endl;
    }else if(operation=='-'){
        std::cout << "the result is "<< number1 - number2 << std::endl;
    }else if(operation=='*'){
        std::cout << "the result is "<< number1 * number2 << std::endl;
    }else if(operation=='/'){
        if(number2==0){
            std::cout << "Error: Division by zero is undefined"<< std::endl;
        }else{
            std::cout << "the result is "<< number1/number2 << std::endl;
        }
    }else{
        std::cout << "please input a correct arithmetic operator" << std::endl;
    }

    return 0;
}
```
### c. Write a program to determine the type of a given character (uppercase letter, lowercase letter, digit, special character) using if-else statements.
```c++
#include <iostream>

int main() {
    char inputChar;

    // Prompt the user to enter a character
    std::cout << "Enter a character: ";
    std::cin >> inputChar;

    // Check the type of the character using if-else statements
    if (isalpha(inputChar)) {
        if (isupper(inputChar)) {
            std::cout << "Uppercase letter\n";
        } else {
            std::cout << "Lowercase letter\n";
        }
    } else if (isdigit(inputChar)) {
        std::cout << "Digit\n";
    } else {
        std::cout << "Special character\n";
    }

    return 0;
}
```
## Looping Statements(while, do-while, for)
### a. Write a C++ program to print the first 10 natural numbers using a while loop.
```c++
#include <iostream>

int main()
{
    int number = 1;
    
    while(number<=10){
        std::cout << number << std::endl;
        number++;
    }

    return 0;
}
```
### b. Create a program that takes an integer input from the user and calculates the factorial of that number using a for loop.
```c++
#include <iostream>

int main()
{
    int integer;
    long long factorial=1;
    std::cout << "Please enter a number" << std::endl;
    std::cin >> integer;
    
    if(integer<0){
        std::cout << "Please enter a correct number" << std::endl;
    }else{
        for (int i = 1; i <=integer; i++) {
            /* code */
            factorial = factorial*i;
        }
    }
    std::cout << "the result of factorial("<< integer <<") is " << factorial << std::endl;
    return 0;
}
```
### c. Write a program that uses a do-while loop to ask the user for a number until the user enters a negative number.
```c++
#include <iostream>

int main()
{
    int integer;
    do{
        std::cout << "Please enter a number" << std::endl;
        std::cin >> integer;
    }while(integer>=0);

    return 0;
}
```
## Break and Continue Statements
### a. Write a program to find the sum of all positive integers entered by the user until they enter a negative number. Use a break statement to terminate the loop.
```c++
#include <iostream>

int main() {
    int number;
    int sum = 0;

    while (true) {
        // Prompt the user to enter an integer
        std::cout << "Enter an integer (negative to exit): ";
        std::cin >> number;

        // Check if the entered number is negative
        if (number < 0) {
            break;  // Exit the loop if the number is negative
        }

        // Add the positive number to the sum
        sum += number;
    }

    // Display the sum of positive integers
    std::cout << "Sum of positive integers: " << sum << std::endl;

    return 0;
}
```
### b. Implement a program that prints all odd numbers from 1 to 50, but skips the number 13 using the continue statement.
```c++
#include <iostream>

int main() {
    for (int i = 1; i <= 50; i += 2) {
        if (i == 13) {
            continue;  // Skip the number 13
        }
        std::cout << i << " ";
    }

    std::cout << std::endl;

    return 0;
}
```
### c. Create a simple guessing game where the program generates a random number between 1 and 100, and the user has to guess the number. Use a break statement to exit the loop when the user guesses the correct number.
```c++
#include <iostream>
#include <cstdlib>
#include <ctime>

int main() {
    // Seed the random number generator with the current time
    std::srand(static_cast<unsigned int>(std::time(nullptr)));

    // Generate a random number between 1 and 100
    int secretNumber = std::rand() % 100 + 1;

    int guess;

    // Main game loop
    while (true) {
        // Prompt the user to guess the number
        std::cout << "Guess the number between 1 and 100: ";
        std::cin >> guess;

        // Check if the guess is correct
        if (guess == secretNumber) {
            std::cout << "Congratulations! You guessed the correct number." << std::endl;
            break;  // Exit the loop if the guess is correct
        } else {
            // Provide a hint and continue the loop
            std::cout << "Wrong guess! Try again." << std::endl;
            if (guess < secretNumber) {
                std::cout << "Hint: The secret number is greater." << std::endl;
            } else {
                std::cout << "Hint: The secret number is smaller." << std::endl;
            }
        }
    }

    return 0;
}
```
