title: C++ create,duplicate queue
author: Alex Li
date: 2023-11-25 18:30:50
tags:
---
#### Task 2: Queue Operations
1. Create a queue of characters named **charQueue**.
2. Enqueue at least four characters into the queue.
3. Print the elements of the queue.
4. Dequeue one element and print the updated queue.
5. Check if the queue is empty.
6. Implement a function to duplicate the elements in the queue.
7. Print the duplicated queue.

```c++
#include <iostream>
#include <queue>

// Function to print queue elements
void printQueue(const std::queue<char>& q) {
    std::cout << "Queue elements: ";
    // Since queue doesn't provide direct access to elements,
    // we need to use a copy for printing without modifying the original queue
    std::queue<char> temp = q;
    while (!temp.empty()) {
        std::cout << temp.front() << " ";
        temp.pop();
    }
    std::cout << std::endl;
}

// Function to duplicate the elements in the queue
void duplicateQueue(std::queue<char>& q) {
    std::queue<char> temp;
    while (!q.empty()) {
        char frontElement = q.front();
        temp.push(frontElement);
        temp.push(frontElement);
        q.pop();
    }
    q = temp; // Assign the duplicated queue back to the original queue
}

int main() {
    // 1. Create a queue of characters named charQueue.
    std::queue<char> charQueue;

    // 2. Enqueue at least four characters into the queue.
    charQueue.push('A');
    charQueue.push('B');
    charQueue.push('C');
    charQueue.push('D');

    // 3. Print the elements of the queue.
    printQueue(charQueue);

    // 4. Dequeue one element and print the updated queue.
    charQueue.pop();
    printQueue(charQueue);

    // 5. Check if the queue is empty.
    if (charQueue.empty()) {
        std::cout << "Queue is empty." << std::endl;
    } else {
        std::cout << "Queue is not empty." << std::endl;
    }

    // 6. Implement a function to duplicate the elements in the queue.
    duplicateQueue(charQueue);

    // 7. Print the duplicated queue.
    printQueue(charQueue);

    return 0;
}

```