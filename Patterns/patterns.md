# Pattern Printing: Mastering Nested Loops

> **Goal:** Visualize and control nested loops to create patterns and understand 2D iteration.

Pattern printing is an excellent exercise for understanding how nested loops work. It teaches you to think in rows and columns.

### Theory: The Row-Column Framework
When printing patterns, we use **nested loops**:
*   **Outer Loop (Rows):** Controls which row we're on (vertical position).
*   **Inner Loop (Columns):** Controls what to print in that row (horizontal position).

**Mental Model:**
```
for each row i from 1 to N:
    for each column j in this row:
        decide what to print (*, space, number)
    move to next line
```

The key insight: **Your position determines what you print.** If you're at row `i` and column `j`, you can use their relationship to decide whether to print a star, a space, or nothing.

---

## Pattern 1: Right-Aligned Triangle
Print a triangle aligned to the right using spaces.

```
    *
   **
  ***
 ****
*****
```

**Logic:**
*   For row `i`, print `(N - i)` spaces, then `i` stars.

<details>
<summary><strong>C++</strong></summary>

```cpp
int n = 5;
for (int i = 1; i <= n; i++) {
    // Print (n - i) spaces
    for (int j = 1; j <= n - i; j++) {
        cout << " ";
    }
    // Print i stars
    for (int j = 1; j <= i; j++) {
        cout << "*";
    }
    cout << endl;
}
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
int n = 5;
for (int i = 1; i <= n; i++) {
    // Print (n - i) spaces
    for (int j = 1; j <= n - i; j++) {
        System.out.print(" ");
    }
    // Print i stars
    for (int j = 1; j <= i; j++) {
        System.out.print("*");
    }
    System.out.println();
}
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
n = 5
for i in range(1, n + 1):
    # Print (n - i) spaces
    print(" " * (n - i), end="")
    # Print i stars
    print("*" * i)
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
int n = 5;
for (int i = 1; i <= n; i++) {
    // Print (n - i) spaces
    for (int j = 1; j <= n - i; j++) {
        printf(" ");
    }
    // Print i stars
    for (int j = 1; j <= i; j++) {
        printf("*");
    }
    printf("\n");
}
```
</details>

---

## Pattern 2: Pyramid (Centered)
Print a centered pyramid using spaces on both sides.

```
    *
   ***
  *****
 *******
*********
```

**Logic:**
*   For row `i`, print `(N - i)` leading spaces, then `(2*i - 1)` stars.

<details>
<summary><strong>C++</strong></summary>

```cpp
int n = 5;
for (int i = 1; i <= n; i++) {
    // Leading spaces
    for (int j = 1; j <= n - i; j++) {
        cout << " ";
    }
    // Stars (odd number: 1, 3, 5, 7...)
    for (int j = 1; j <= 2 * i - 1; j++) {
        cout << "*";
    }
    cout << endl;
}
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
int n = 5;
for (int i = 1; i <= n; i++) {
    for (int j = 1; j <= n - i; j++) {
        System.out.print(" ");
    }
    for (int j = 1; j <= 2 * i - 1; j++) {
        System.out.print("*");
    }
    System.out.println();
}
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
n = 5
for i in range(1, n + 1):
    print(" " * (n - i) + "*" * (2 * i - 1))
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
int n = 5;
for (int i = 1; i <= n; i++) {
    for (int j = 1; j <= n - i; j++) {
        printf(" ");
    }
    for (int j = 1; j <= 2 * i - 1; j++) {
        printf("*");
    }
    printf("\n");
}
```
</details>

---

## Pattern 3: Inverted Pyramid
Print an upside-down pyramid with leading spaces.

```
*********
 *******
  *****
   ***
    *
```

**Logic:**
*   For row `i`, print `(i - 1)` spaces, then `(2 * (N - i + 1) - 1)` stars.

<details>
<summary><strong>C++</strong></summary>

```cpp
int n = 5;
for (int i = 1; i <= n; i++) {
    // Leading spaces increase
    for (int j = 1; j < i; j++) {
        cout << " ";
    }
    // Stars decrease (9, 7, 5, 3, 1)
    for (int j = 1; j <= 2 * (n - i + 1) - 1; j++) {
        cout << "*";
    }
    cout << endl;
}
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
int n = 5;
for (int i = 1; i <= n; i++) {
    for (int j = 1; j < i; j++) {
        System.out.print(" ");
    }
    for (int j = 1; j <= 2 * (n - i + 1) - 1; j++) {
        System.out.print("*");
    }
    System.out.println();
}
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
n = 5
for i in range(1, n + 1):
    print(" " * (i - 1) + "*" * (2 * (n - i + 1) - 1))
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
int n = 5;
for (int i = 1; i <= n; i++) {
    for (int j = 1; j < i; j++) {
        printf(" ");
    }
    for (int j = 1; j <= 2 * (n - i + 1) - 1; j++) {
        printf("*");
    }
    printf("\n");
}
```
</details>

---

## Pattern 4: Diamond
Combine a pyramid and an inverted pyramid.

```
    *
   ***
  *****
 *******
*********
 *******
  *****
   ***
    *
```

**Logic:**
*   First half: Pyramid (rows 1 to N).
*   Second half: Inverted Pyramid (rows 1 to N-1).

<details>
<summary><strong>C++</strong></summary>

```cpp
int n = 5;
// Upper pyramid
for (int i = 1; i <= n; i++) {
    for (int j = 1; j <= n - i; j++) cout << " ";
    for (int j = 1; j <= 2 * i - 1; j++) cout << "*";
    cout << endl;
}
// Lower inverted pyramid
for (int i = 1; i < n; i++) {
    for (int j = 1; j <= i; j++) cout << " ";
    for (int j = 1; j <= 2 * (n - i) - 1; j++) cout << "*";
    cout << endl;
}
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
int n = 5;
// Upper pyramid
for (int i = 1; i <= n; i++) {
    for (int j = 1; j <= n - i; j++) System.out.print(" ");
    for (int j = 1; j <= 2 * i - 1; j++) System.out.print("*");
    System.out.println();
}
// Lower inverted pyramid
for (int i = 1; i < n; i++) {
    for (int j = 1; j <= i; j++) System.out.print(" ");
    for (int j = 1; j <= 2 * (n - i) - 1; j++) System.out.print("*");
    System.out.println();
}
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
n = 5
# Upper pyramid
for i in range(1, n + 1):
    print(" " * (n - i) + "*" * (2 * i - 1))
# Lower inverted pyramid
for i in range(1, n):
    print(" " * i + "*" * (2 * (n - i) - 1))
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
int n = 5;
// Upper pyramid
for (int i = 1; i <= n; i++) {
    for (int j = 1; j <= n - i; j++) printf(" ");
    for (int j = 1; j <= 2 * i - 1; j++) printf("*");
    printf("\n");
}
// Lower inverted pyramid
for (int i = 1; i < n; i++) {
    for (int j = 1; j <= i; j++) printf(" ");
    for (int j = 1; j <= 2 * (n - i) - 1; j++) printf("*");
    printf("\n");
}
```
</details>

---

## Key Takeaways
1.  **Think in Rows & Columns:** Outer loop = rows, inner loop = columns.
2.  **Find the Relationship:** Use `i` (row number) and `j` (column number) to determine what to print.
3.  **Break it Down:** Complex patterns are just simple patterns combined (like the diamond).
4.  **Spaces Matter:** Leading spaces control alignment. Count them carefully!
