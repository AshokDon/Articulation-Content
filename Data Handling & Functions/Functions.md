# Functions: Modular Code

> **Goal:** Organize code into reusable blocks to avoid repetition and bugs.

Functions (or methods) allow you to break a complex problem into smaller, manageable pieces.

---

## 1. Basic Syntax
A function consists of a **return type**, a **name**, **parameters**, and a **body**.

### Code Examples

<details>
<summary><strong>C++</strong></summary>

```cpp
#include <iostream>
using namespace std;

// Function definition
int add(int a, int b) {
    return a + b;
}

int main() {
    int result = add(5, 3);
    cout << result; // 8
    return 0;
}
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
public class Main {
    // Method definition
    static int add(int a, int b) {
        return a + b;
    }

    public static void main(String[] args) {
        int result = add(5, 3);
        System.out.println(result); // 8
    }
}
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
# Function definition
def add(a, b):
    return a + b

result = add(5, 3)
print(result) # 8
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
#include <stdio.h>

// Function definition
int add(int a, int b) {
    return a + b;
}

int main() {
    int result = add(5, 3);
    printf("%d", result); // 8
    return 0;
}
```
</details>

---

## 2. Void Functions
Functions that perform an action but **do not return a value**.

### Code Examples

<details>
<summary><strong>C++</strong></summary>

```cpp
void greet(string name) {
    cout << "Hello, " << name << endl;
}
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
static void greet(String name) {
    System.out.println("Hello, " + name);
}
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
def greet(name):
    print(f"Hello, {name}")
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
void greet(char name[]) {
    printf("Hello, %s\n", name);
}
```
</details>

---

## 3. Pass by Value vs. Reference (CRITICAL)
This is where many bugs happen.
*   **Pass by Value:** The function gets a **copy**. Changing it inside *doesn't* affect the original.
*   **Pass by Reference:** The function gets the **original**. Changing it inside *changes* the original.

> **Performance Tip:** In C++, passing large vectors/strings by value is SLOW (it copies the whole thing). Always pass by reference (`&`) to save time.

### Code Examples

<details>
<summary><strong>C++ (The '&' Symbol)</strong></summary>

```cpp
// Pass by Value (Copy)
void noChange(int x) {
    x = 100;
}

// Pass by Reference (Original)
void change(int &x) {
    x = 100;
}

int main() {
    int a = 5;
    noChange(a); // a is still 5
    change(a);   // a becomes 100
    return 0;
}
```
</details>

<details>
<summary><strong>Java (References)</strong></summary>

```java
// Primitives (int, double) are always Pass by Value (Copy).
// Objects (Arrays, Classes) are Pass by Reference (Pointer to Object).

static void changeArray(int[] arr) {
    arr[0] = 100; // This changes the original array!
}
```
</details>

<details>
<summary><strong>Python (Object Reference)</strong></summary>

```python
# Integers/Strings are Immutable (Like Pass by Value)
def try_change(x):
    x = 100 # Creates new local variable

# Lists are Mutable (Like Pass by Reference)
def change_list(arr):
    arr[0] = 100 # Changes original list
```
</details>

<details>
<summary><strong>C (Pointers)</strong></summary>

```c
// Pass by Value
void noChange(int x) {
    x = 100;
}

// Pass by Pointer (Reference)
void change(int *x) {
    *x = 100; // Dereference to change value
}

int main() {
    int a = 5;
---

## 4. Returning Different Types
You can return almost any data type from a function.

### A. Returning `bool` (True/False)
Useful for checking conditions (e.g., is a number prime?).

<details>
<summary><strong>C++</strong></summary>

```cpp
bool isEven(int n) {
    return n % 2 == 0;
}
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
static boolean isEven(int n) {
    return n % 2 == 0;
}
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
def is_even(n):
    return n % 2 == 0
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
// C99+ uses <stdbool.h>, or use int (0/1)
int isEven(int n) {
    return n % 2 == 0;
}
```
</details>

### B. Returning `char` & `string`
Returning text data.

<details>
<summary><strong>C++</strong></summary>

```cpp
char getGrade(int score) {
    if (score >= 90) return 'A';
    return 'B';
}

string getMessage() {
    return "Welcome!";
}
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
static char getGrade(int score) {
    if (score >= 90) return 'A';
    return 'B';
}

static String getMessage() {
    return "Welcome!";
}
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
def get_grade(score):
    if score >= 90: return 'A'
    return 'B'

def get_message():
    return "Welcome!"
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
char getGrade(int score) {
    if (score >= 90) return 'A';
    return 'B';
}

// C cannot return strings easily. 
// Usually, you return a pointer to a string literal 
// or pass a buffer to be filled.
char* getMessage() {
    return "Welcome!"; // Valid for string literals
}
```
</details>

### C. Returning Arrays (Collections)
Returning multiple values.
*   **C++:** Return `std::vector`.
*   **Java:** Return `int[]` or `ArrayList`.
*   **Python:** Return `list`.
*   **C:** **Cannot** return arrays directly. You must return a pointer (risky) or pass an array to fill (preferred).

<details>
<summary><strong>C++ (Vector)</strong></summary>

```cpp
vector<int> getFirstThree() {
    return {1, 2, 3};
}
```
</details>

<details>
<summary><strong>Java (Array)</strong></summary>

```java
static int[] getFirstThree() {
    return new int[]{1, 2, 3};
}
```
</details>

<details>
<summary><strong>Python (List)</strong></summary>

```python
def get_first_three():
    return [1, 2, 3]
```
</details>
