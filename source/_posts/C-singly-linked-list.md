title: C++ singly linked list
author: Alex Li
date: 2023-11-25 23:55:20
tags:
---
1. Define a structure for a singly linked list node with an integer value.
2. Create a linked list named **intList** with at least five nodes.
3. Print the elements of the linked list.
4. Implement a function to insert a new node at the end of the linked list.
5. Print the updated linked list.
6. Implement a function to delete a node with a specific value from the linked list. 
7. Print the updated linked list.

```c++
#include <iostream>

// 1. Define a structure for a singly linked list node with an integer value.
struct ListNode {
    int data;
    ListNode* next;

    // Constructor to initialize the node
    ListNode(int value) : data(value), next(nullptr) {}
};

// Function to print the elements of the linked list.
void printList(ListNode* head) {
    std::cout << "Linked List: ";
    while (head != nullptr) {
        std::cout << head->data << " ";
        head = head->next;
    }
    std::cout << std::endl;
}

// 4. Implement a function to insert a new node at the end of the linked list.
void insertAtEnd(ListNode*& head, int value) {
    ListNode* newNode = new ListNode;
    newNode->data = value;
    std::cout << "head: " << head << std::endl;

    if (head == nullptr) {
        // If the list is empty, the new node becomes the head.
        head = newNode;
    } else {
        // Traverse the list to find the last node and append the new node.
        ListNode* temp = head;
        std::cout << "temp->next: " <<temp->next << std::endl;
        while (temp->next != nullptr) {
            temp = temp->next;
        }
        temp->next = newNode;
    }
}

// 6. Implement a function to delete a node with a specific value from the linked list.
void deleteNode(ListNode*& head, int value) {
    // Handle the case where the node to be deleted is the head.
    if (head != nullptr && head->data == value) {
        ListNode* temp = head;
        head = head->next;
        delete temp;
        return;
    }

    // Traverse the list to find the node with the specified value.
    ListNode* current = head;
    ListNode* prev = nullptr;
    while (current != nullptr && current->data != value) {
        prev = current;
        current = current->next;
    }

    // If the node is found, unlink it from the list and delete it.
    if (current != nullptr) {
        prev->next = current->next;
        delete current;
    }
}

int main() {
    // 2. Create a linked list named intList with at least five nodes.
    ListNode* intList = nullptr;
    for (int i = 1; i <= 5; ++i) {
        insertAtEnd(intList, i * 10);
    }

    // 3. Print the elements of the linked list.
    printList(intList);

    // 5. Insert a new node at the end of the linked list.
    insertAtEnd(intList, 60);

    // 7. Delete a node with a specific value from the linked list.
    deleteNode(intList, 30);

    // Print the updated linked list.
    printList(intList);

    return 0;
}

```