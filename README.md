#include <iostream>
using namespace std;

#define MAX 5

int queue[MAX];
int front = -1;
int rear = -1;

// Enqueue operation
void enqueue() {
    int value;
    if (rear == MAX - 1) {
        cout << "Queue Overflow" << endl;
    }
    else {
        if (front == -1)
            front = 0;

        cout << "Enter value to insert: ";
        cin >> value;

        rear++;
        queue[rear] = value;

        cout << value << " inserted into queue" << endl;
    }
}

// Dequeue operation
void dequeue() {
    if (front == -1 || front > rear) {
        cout << "Queue Underflow" << endl;
    }
    else {
        cout << queue[front] << " deleted from queue" << endl;
        front++;
    }
}

// Display operation
void display() {
    if (front == -1 || front > rear) {
        cout << "Queue is empty" << endl;
    }
    else {
        cout << "Queue elements are: ";
        for (int i = front; i <= rear; i++) {
            cout << queue[i] << " ";
        }
        cout << endl;
    }
}

int main() {
    int choice;

    do {
        cout << "\n--- QUEUE OPERATIONS ---" << endl;
        cout << "1. Enqueue" << endl;
        cout << "2. Dequeue" << endl;
        cout << "3. Display" << endl;
        cout << "4. Exit" << endl;
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1: enqueue(); break;
            case 2: dequeue(); break;
            case 3: display(); break;
            case 4: cout << "Exit Program"; break;
            default: cout << "Invalid choice";
        }

    } while (choice != 4);

    return 0;
}
