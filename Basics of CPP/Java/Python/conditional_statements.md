# Conditional Statements: Making Decisions

> **Goal:** Control the flow of your program based on specific conditions.

Your code needs to handle different situations differently. Conditional statements allow your program to "think" and choose a path.

---

## 1. If / Else
The most basic form of decision making.
*   **If:** Executes code only if the condition is true.
*   **Else:** Executes code if the condition is false.

### Code Examples

<details>
<summary><strong>C++</strong></summary>

```cpp
int score = 85;

if (score >= 50) {
    cout << "Pass";
} else {
    cout << "Fail";
}
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
int score = 85;

if (score >= 50) {
    System.out.println("Pass");
} else {
    System.out.println("Fail");
}
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
score = 85

if score >= 50:
    print("Pass")
else:
    print("Fail")
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
int score = 85;

if (score >= 50) {
    printf("Pass");
} else {
    printf("Fail");
}
```
</details>

---

## 2. Else If / Elif
Used when you have more than two possible paths. It checks conditions in order.

### Code Examples

<details>
<summary><strong>C++</strong></summary>

```cpp
int score = 85;

if (score >= 90) {
    cout << "Grade A";
} else if (score >= 80) {
    cout << "Grade B";
} else {
    cout << "Grade C";
}
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
int score = 85;

if (score >= 90) {
    System.out.println("Grade A");
} else if (score >= 80) {
    System.out.println("Grade B");
} else {
    System.out.println("Grade C");
}
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
score = 85

if score >= 90:
    print("Grade A")
elif score >= 80:  # Note: 'elif' not 'else if'
    print("Grade B")
else:
    print("Grade C")
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
int score = 85;

if (score >= 90) {
    printf("Grade A");
} else if (score >= 80) {
    printf("Grade B");
} else {
    printf("Grade C");
}
```
</details>

---

## 3. Switch Statement
Useful when checking a single variable against many specific values (constants).
*   **Note:** Python does not have a traditional `switch`. Use `if-elif` or `match` (Python 3.10+).

### Code Examples

<details>
<summary><strong>C++</strong></summary>

```cpp
int day = 2;

switch (day) {
    case 1:
        cout << "Monday";
        break; // Don't forget break!
    case 2:
        cout << "Tuesday";
        break;
    default:
        cout << "Other";
}
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
int day = 2;

switch (day) {
    case 1:
        System.out.println("Monday");
        break;
    case 2:
        System.out.println("Tuesday");
        break;
    default:
        System.out.println("Other");
}
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
# Python uses if-elif for this
day = 2

if day == 1:
    print("Monday")
elif day == 2:
    print("Tuesday")
else:
    print("Other")
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
int day = 2;

switch (day) {
    case 1:
        printf("Monday");
        break;
    case 2:
        printf("Tuesday");
        break;
    default:
        printf("Other");
}
```
</details>

---

## 4. Ternary Operator (Short If-Else)
A one-line shortcut for simple `if-else` assignments.
*   **Syntax (C/C++/Java):** `condition ? value_if_true : value_if_false`
*   **Syntax (Python):** `value_if_true if condition else value_if_false`

### Code Examples

<details>
<summary><strong>C++</strong></summary>

```cpp
int a = 10, b = 20;
int max_val = (a > b) ? a : b;
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
int a = 10, b = 20;
int maxVal = (a > b) ? a : b;
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
a = 10
b = 20
max_val = a if a > b else b
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
int a = 10, b = 20;
int max_val = (a > b) ? a : b;
```
</details>
