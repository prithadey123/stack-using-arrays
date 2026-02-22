 Source Code

```c
#include <stdio.h>
#include <stdlib.h>

#define MAX 5

int stack[MAX];
int top = -1;

// Push operation
void push(int value) {
    if (top == MAX - 1) {
        printf("Stack Overflow! Cannot push %d\n", value);
    } else {
        top++;
        stack[top] = value;
        printf("%d pushed into stack\n", value);
    }
}

// Pop operation
void pop() {
    if (top == -1) {
        printf("Stack Underflow! Cannot pop\n");
    } else {
        printf("%d popped from stack\n", stack[top]);
        top--;
    }
}

// Display stack
void display() {
    if (top == -1) {
        printf("Stack is empty\n");
    } else {
        printf("Stack elements are:\n");
        for (int i = top; i >= 0; i--) {
            printf("%d\n", stack[i]);
        }
    }
}

int main() {
    push(10);
    push(20);
    push(30);
    display();

    pop();
    display();

    return 0;
}
```

---

 Explanation

 Stack Declaration
- `#define MAX 5` → Maximum stack size.
- `stack[MAX]` → Array used to store elements.
- `top = -1` → Indicates stack is initially empty.

 Push Operation
- Checks for **Overflow** (`top == MAX - 1`).
- Increments `top`.
- Inserts element at `stack[top]`.

 Pop Operation
- Checks for **Underflow** (`top == -1`).
- Removes element from `stack[top]`.
- Decrements `top`.

 Display Operation
- Prints elements from `top` to `0`.

---

 Sample Output

```
10 pushed into stack
20 pushed into stack
30 pushed into stack
Stack elements are:
30
20
10
30 popped from stack
Stack elements are:
20
10
```

---

 Time Complexity

- Push: **O(1)**
- Pop: **O(1)**
- Display: **O(n)**

---

 How to Compile and Run

 Compile:
```
gcc stack_array.c -o stack
```

Run:
```
./stack
```

---

 Concepts Used
- Arrays in C
- Stack Data Structure
- LIFO Principle
- Overflow & Underflow Conditions
- Functions C
