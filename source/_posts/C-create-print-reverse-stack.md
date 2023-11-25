title: C++ create, print,reverse stack
author: Alex Li
date: 2023-11-25 17:57:42
tags:
---
#### TASK 1 Stack Operations
1. Create a stack of integers named **intStack**.
2. Push at least five integers onto the stack.
3. Print the elements of the stack.
4. Pop two elements from the stack and print the updated stack. 
5. Check if the stack is empty.
6. Implement a function to reverse the elements in the stack. 
7. Print the reversed stack.

```c++

#include <iostream>
#include <stack>
using namespace std;

// Function to print stack elements
void printStack(const stack<int>& s){
    std::cout << "Stack elements: ";
    std::stack<int> temp = s;
    while (!temp.empty())
    {
        std::cout << temp.top() << " ";
        temp.pop();
        /* code */
    }
    std::cout << std::endl;
}
void reverseStack(stack<int>& s){
    std::stack<int> temp;
    while (!s.empty())
    {
        temp.push(s.top());
        s.pop();
        /* code */
    }
    s = temp;
}

int main(int argc, char const *argv[])
{
    // create a stack of integers named intStack.
    std::stack<int> intStack;
    // push at least five integers onto the stack.
    intStack.push(10);
    intStack.push(20);
    intStack.push(30);
    intStack.push(40);
    intStack.push(50);

    printStack(intStack);
    // pop two elements from the stack and print the updated stack.

    intStack.pop();
    intStack.pop();
    printStack(intStack);
    // check if the stack is empty.
    if(intStack.empty()){
        std::cout << "stack is empty" << std::endl;
    }else{
        std::cout << "stack is not empty" << std::endl;
    }

    // implement a function to reverse the elemnts in ths stack.
    reverseStack(intStack);
    // print the reversed stack.
    printStack(intStack);

    /* code */
    return 0;
}

```