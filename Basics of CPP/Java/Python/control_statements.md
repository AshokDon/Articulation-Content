# Control Statements: Loops & Jumps

> **Goal:** Repeat actions efficiently and control the flow of execution.

Loops allow you to execute a block of code multiple times, which is essential for iterating through arrays, processing input, or running simulations.

---

## 1. For Loop
Used when you know exactly how many times you want to repeat something.

### Code Examples

<details>
<summary><strong>C++</strong></summary>

```cpp
// Print numbers 0 to 4
for (int i = 0; i < 5; i++) {
    cout << i << " ";
}
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
for (int i = 0; i < 5; i++) {
    System.out.print(i + " ");
}
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
# range(5) generates 0, 1, 2, 3, 4
for i in range(5):
    print(i, end=" ")
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
for (int i = 0; i < 5; i++) {
    printf("%d ", i);
}
```
</details>

---

## 2. While Loop
Used when you want to repeat something *as long as* a condition is true.

### Code Examples

<details>
<summary><strong>C++</strong></summary>

```cpp
int i = 0;
while (i < 5) {
    cout << i << " ";
    i++;
}
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
int i = 0;
while (i < 5) {
    System.out.print(i + " ");
    i++;
}
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
i = 0
while i < 5:
    print(i, end=" ")
    i += 1
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
int i = 0;
while (i < 5) {
    printf("%d ", i);
    i++;
}
```
</details>

---

## 3. Do-While Loop
Similar to `while`, but guarantees the code runs **at least once**.
*   **Note:** Python does not have a `do-while` loop. You can simulate it with `while True` and a `break`.

### Code Examples

<details>
<summary><strong>C++</strong></summary>

```cpp
int i = 0;
do {
    cout << i << " ";
    i++;
} while (i < 5);
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
int i = 0;
do {
    System.out.print(i + " ");
    i++;
} while (i < 5);
```
</details>

<details>
<summary><strong>Python (Simulation)</strong></summary>

```python
i = 0
while True:
    print(i, end=" ")
    i += 1
    if i >= 5:
        break
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
int i = 0;
do {
    printf("%d ", i);
    i++;
} while (i < 5);
```
</details>

---

## 4. Break and Continue
Used to alter the flow inside loops.

*   **`break`:** Immediately **exits** the loop.
*   **`continue`:** Skips the rest of the current iteration and **jumps to the next** one.

### Code Examples

<details>
<summary><strong>C++</strong></summary>

```cpp
for (int i = 0; i < 10; i++) {
    if (i == 3) continue; // Skip 3
    if (i == 7) break;    // Stop at 7
    cout << i << " ";
}
// Output: 0 1 2 4 5 6
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
for (int i = 0; i < 10; i++) {
    if (i == 3) continue;
    if (i == 7) break;
    System.out.print(i + " ");
}
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
for i in range(10):
    if i == 3: continue
    if i == 7: break
    print(i, end=" ")
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
for (int i = 0; i < 10; i++) {
    if (i == 3) continue;
    if (i == 7) break;
    printf("%d ", i);
}
```
</details>
