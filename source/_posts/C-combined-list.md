title: C++ combined list
author: Alex Li
date: 2023-11-26 00:26:43
tags:
---

#### Task 4: Combining Data Structures
1. Create a stack of strings named **stringStack**.
2. Push at least three strings onto the stack.
3. Create a queue of floats named **floatQueue**.
4. Enqueue at least two float values into the queue.
5. Create a linked list of characters named **charList**.
6. Insert at least four characters into the linked list.
7. Combine the elements of the stack, queue, and linked list into a new data structure (e.g., another linked list, a stack, or a queue).
8. Print the elements of the new data structure.

```c++
#include <iostream>
#include <stack>
#include <queue>
#include <list>

int main() {
    // 1. Create a stack of strings named stringStack.
    std::stack<std::string> stringStack;

    // 2. Push at least three strings onto the stack.
    stringStack.push("Apple");
    stringStack.push("Banana");
    stringStack.push("Orange");

    // 3. Create a queue of floats named floatQueue.
    std::queue<float> floatQueue;

    // 4. Enqueue at least two float values into the queue.
    floatQueue.push(3.14f);
    floatQueue.push(2.718f);

    // 5. Create a linked list of characters named charList.
    std::list<char> charList;

    // 6. Insert at least four characters into the linked list.
    charList.push_back('A');
    charList.push_back('B');
    charList.push_back('C');
    charList.push_back('D');

    // 7. Combine the elements of the stack, queue, and linked list into a new data structure.
    std::list<std::string> combinedList;

    // Combine elements from the stack
    while (!stringStack.empty()) {
        combinedList.push_back(stringStack.top());
        stringStack.pop();
    }

    // Combine elements from the queue
    while (!floatQueue.empty()) {
        combinedList.push_back(std::to_string(floatQueue.front()));
        floatQueue.pop();
    }

    // Combine elements from the linked list
    for (char ch : charList) {
        combinedList.push_back(std::string(1, ch));
    }

    // 8. Print the elements of the new data structure.
    std::cout << "Combined List: ";
    for (const std::string& element : combinedList) {
        std::cout << element << " ";
    }
    std::cout << std::endl;

    return 0;
}
```