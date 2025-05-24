# EX 50 C function to delete a node from a Doubly Linked List at the beginning of the list.
## DATE:
## AIM:
To write a C function to delete a node from a Doubly Linked List at the beginning of the list.

## Algorithm
1. Start. 
2. Define a variables. 
3. Write a function to insert a node in a linked list. 
4. Read the value using scanf. 
5. Ask the user to make an input. 
6. Print out the answer. 
7. End 

## Program:
```
#include <stdio.h>
#include <stdlib.h>

// Structure for a node in a doubly linked list
struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
};

// Function to delete the first node of the list
void deleteAtBeginning(struct Node** head) {
    if (*head == NULL) {
        printf("List is empty. Nothing to delete.\n");
        return;
    }

    struct Node* temp = *head;
    *head = temp->next;

    if (*head != NULL) {
        (*head)->prev = NULL;
    }

    printf("Deleted node with data: %d\n", temp->data);
    free(temp);
}
// Function to insert a node at the beginning (for testing)
void insertAtBeginning(struct Node** head, int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = *head;

    if (*head != NULL) {
        (*head)->prev = newNode;
    }

    *head = newNode;
}

// Function to display the list
void displayList(struct Node* head) {
    struct Node* temp = head;
    printf("List: ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    struct Node* head = NULL;

    // Insert nodes
    insertAtBeginning(&head, 30);
    insertAtBeginning(&head, 20);
    insertAtBeginning(&head, 10);

    displayList(head);

    // Delete the first node
    deleteAtBeginning(&head);
    displayList(head);

    return 0;
}

```

## Output:



## Result:
Thus the program was executed and the output was verified successfully.
