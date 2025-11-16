EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.
Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:

```#include <stdio.h>   // 1. Include Necessary Header Files
#include <stdlib.h>

// 2. Declare Global Variables
#define SIZE 5
int stack[SIZE];
int top = -1;

// 3. Define Stack Functions

// Function to push an element
void push(int value) {
    if (top == SIZE - 1) {
        printf("Stack Overflow! Cannot push %d\n", value);
    } else {
        top++;
        stack[top] = value;
        printf("%d pushed to stack.\n", value);
    }
}

// Function to pop an element
void pop() {
    if (top == -1) {
        printf("Stack Underflow! No elements to pop.\n");
    } else {
        printf("%d popped from stack.\n", stack[top]);
        top--;
    }
}

// 3. Define the Display Function
void display() {
    if (top == -1) {
        printf("Stack is empty.\n");
    } else {
        printf("Stack elements are:\n");
        for (int i = top; i >= 0; i--) {
            printf("%d\n", stack[i]);
        }
    }
}

// 4. Main Function
int main() {
    int choice, value;

    while (1) {
        printf("\n--- Stack Menu ---\n");
        printf("1. Push\n");
        printf("2. Pop\n");
        printf("3. Display\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter value to push: ");
                scanf("%d", &value);
                push(value);
                break;
            case 2:
                pop();
                break;
            case 3:
                display();
                break;
            case 4:
                printf("Exiting program.\n");
                exit(0);
            default:
                printf("Invalid choice! Try again.\n");
        }
    }

    return 0;
}
```

Output:


<img width="762" height="510" alt="513429674-1958f6b0-1e66-4825-afdb-2c248dce100e" src="https://github.com/user-attachments/assets/a9120a76-b942-4bfe-8713-d6fe10d1d0f4" />



Result:
Thus, the program to display stack elements using an array is verified successfully.
 

EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
Aim:
To create a C program to push the given element in to a stack using array.
Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:

```#include <stdio.h>

// 1. Declare global variables for the stack size, top index, and the stack itself
#define SIZE 5
float stack[SIZE];
int top = -1;

// 2. Define the push function to add a floating-point number to the stack
void push(float value) {
    if (top == SIZE - 1) {
        printf("Stack Overflow! Cannot push %.2f\n", value);
    } else {
        top++;
        stack[top] = value;
        printf("%.2f pushed into the stack.\n", value);
    }
}

// 3. Main function: Initialize and call the push function
int main() {
    float num;
    int n, i;

    printf("Enter how many elements to push (max %d): ", SIZE);
    scanf("%d", &n);

    if (n > SIZE) {
        printf("You can push only up to %d elements.\n", SIZE);
        return 0;
    }

    // 4. Call the push function as needed
    for (i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%f", &num);
        push(num);
    }

    // Display the final stack contents
    printf("\nStack elements are:\n");
    for (i = top; i >= 0; i--) {
        printf("%.2f\n", stack[i]);
    }

    return 0;
}

```

Output:


<img width="632" height="352" alt="513430383-bf48adf2-68b8-4741-90d6-31f75019ef75" src="https://github.com/user-attachments/assets/c35418fd-638d-45c1-bddb-c788c8ac9710" />




Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

#define SIZE 5

// 1. Declare global variables for the queue, rear, front, and iteration
int queue[SIZE];
int front = -1;
int rear = -1;

// Function to insert (enqueue) an element
void enqueue(int value) {
    if (rear == SIZE - 1) {
        printf("Queue Overflow! Cannot insert %d\n", value);
    } else {
        if (front == -1)
            front = 0;
        rear++;
        queue[rear] = value;
        printf("%d inserted into the queue.\n", value);
    }
}

// Function to delete (dequeue) an element
void dequeue() {
    if (front == -1 || front > rear) {
        printf("Queue Underflow! No elements to delete.\n");
    } else {
        printf("%d deleted from the queue.\n", queue[front]);
        front++;
    }
}

// 2. Define the display function to print the elements of the queue
void display() {
    if (front == -1 || front > rear) {
        printf("Queue is empty.\n");
    } else {
        printf("Queue elements are:\n");
        for (int i = front; i <= rear; i++) {
            printf("%d ", queue[i]);
        }
        printf("\n");
    }
}

// 3 & 4. Main Function — Initialize and perform queue operations
int main() {
    int choice, value;

    while (1) {
        printf("\n--- Queue Menu ---\n");
        printf("1. Enqueue (Insert)\n");
        printf("2. Dequeue (Delete)\n");
        printf("3. Display\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter value to enqueue: ");
                scanf("%d", &value);
                enqueue(value);
                break;
            case 2:
                dequeue();
                break;
            case 3:
                display();
                break;
            case 4:
                printf("Exiting program.\n");
                exit(0);
            default:
                printf("Invalid choice! Try again.\n");
        }
    }

    return 0;
}

```

Output:


<img width="663" height="455" alt="513431406-699eb857-a44f-4884-bb52-1e4a19fa6de9" src="https://github.com/user-attachments/assets/b27ab92f-8fdd-42b5-a581-bb77ad4aae77" />


Result:
Thus, the program to display queue elements using array is verified successfully.


 
EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:

```
#include <stdio.h>

#define SIZE 5  // Maximum size of the queue

// Step 1: Declare global variables
float queue[SIZE];
int front = -1, rear = -1;

// Step 2: Define the enqueue function
void enqueue(float value) {
    if (rear == SIZE - 1) {
        printf("Queue is full! Cannot insert %.2f\n", value);
    } else {
        if (front == -1)
            front = 0;  // Initialize front when inserting first element
        rear++;
        queue[rear] = value;
        printf("%.2f inserted into the queue.\n", value);
    }
}

// Step 3: Define the display function
void display() {
    if (front == -1) {
        printf("Queue is empty!\n");
    } else {
        printf("\nCurrent Queue Elements:\n");
        for (int i = front; i <= rear; i++) {
            printf("%.2f ", queue[i]);
        }
        printf("\n");
    }
}

// Step 4: Main function
int main() {
    // Inserting elements into the queue
    enqueue(10.5);
    enqueue(20.3);
    enqueue(30.7);
    enqueue(40.2);
    enqueue(50.8);

    // Display the queue
    display();

    // Trying to insert when queue is full
    enqueue(60.1);

    // Display again to show no new element was added
    display();

    return 0;
}
```

Output:

<img width="493" height="394" alt="513431819-33c171e1-275c-4dd3-9fd9-d436005586bb" src="https://github.com/user-attachments/assets/b8c5ba85-83b8-4c6f-8f12-1f2c74181527" />



Result:

Thus, the program to insert elements in queue using array is verified successfully.



 
EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



Aim:

To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



Program:

```
#include <stdio.h>

#define SIZE 5  // Maximum size of the queue

// Global variables
float queue[SIZE];
int front = -1, rear = -1;

// Function to insert (for testing deletion)
void enqueue(float value) {
    if (rear == SIZE - 1) {
        printf("Queue is full! Cannot insert %.2f\n", value);
    } else {
        if (front == -1)
            front = 0;  // Initialize front when first element is inserted
        rear++;
        queue[rear] = value;
        printf("%.2f inserted into the queue.\n", value);
    }
}

// Step-by-step function to delete (dequeue) an element
void dequeue() {
    // Step 1: Check if the Queue is Empty
    if (front == -1) {
        printf("Queue is empty! No elements to delete.\n");
    } else {
        // Step 2: Delete the Front Element
        printf("Deleted element: %.2f\n", queue[front]);
        front++;

        // Step 3: Check if the Queue Becomes Empty After Deletion
        if (front > rear) {
            front = rear = -1;  // Reset queue
            printf("Queue is now empty after deletion.\n");
        }
    }
}

// Function to display the queue contents
void display() {
    if (front == -1) {
        printf("Queue is empty!\n");
    } else {
        printf("\nCurrent Queue Elements:\n");
        for (int i = front; i <= rear; i++) {
            printf("%.2f ", queue[i]);
        }
        printf("\n");
    }
}

// Main function to test queue operations
int main() {
    enqueue(10.5);
    enqueue(20.3);
    enqueue(30.7);
    display();

    dequeue();
    display();

    dequeue();
    dequeue();
    dequeue();  // Attempting extra deletion to show empty case

    return 0;
}

```

Output:


<img width="605" height="435" alt="513432402-0ffbe64c-579f-49c7-a661-37af64728695" src="https://github.com/user-attachments/assets/6b23979c-c07c-49e5-9251-158276efe146" />


Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
