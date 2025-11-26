# Data Types: The Building Blocks

> **Goal:** Choose the right container for your data to avoid **Overflow** and **Precision Errors**.

In competitive programming, picking the wrong data type is the most common cause of "Wrong Answer" on hidden test cases. You must know the limits of your tools.

---

## 1. Integers (Whole Numbers)
Used for counting, indices, and discrete values.

### Key Concepts
*   **Overflow:** If a number gets too big for its box, it wraps around to a negative number. This is catastrophic.
*   **32-bit vs 64-bit:**
    *   **32-bit (`int`):** Max value $\approx 2 \cdot 10^9$. Use for $N \le 10^9$.
    *   **64-bit (`long long` / `long`):** Max value $\approx 9 \cdot 10^{18}$. Use for sums, products, or $N > 10^9$.

### Code Examples: Declaring & Printing

<details>
<summary><strong>C++</strong></summary>

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 1000000000;       // 10^9 (Fits in 32-bit)
    long long b = 1000000000000LL; // 10^12 (Needs 64-bit)
    
    cout << a << endl;
    cout << b << endl;
    return 0;
}
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
public class Main {
    public static void main(String[] args) {
        int a = 1000000000;      // 32-bit
        long b = 1000000000000L; // 64-bit (Note the 'L')
        
        System.out.println(a);
        System.out.println(b);
    }
}
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
# Python handles large integers automatically!
# You don't need to worry about overflow for integers.
a = 1000000000
b = 1000000000000000000000000 # Arbitrary precision

print(a)
print(b)
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
#include <stdio.h>

int main() {
    int a = 1000000000;
    long long b = 1000000000000LL;
    
    printf("%d\n", a);
    printf("%lld\n", b); // Use %lld for long long
    return 0;
}
```
</details>

---

## 2. Floating Point (Decimals)
Used for measurements, geometry, and probabilities.

### Key Concepts
*   **Precision Error:** Computers cannot store $1/3$ or $\pi$ exactly. `0.1 + 0.2 != 0.3` in many cases.
*   **`double` vs `float`:** Always use **`double`** (64-bit) in contests. `float` (32-bit) is not precise enough.

### Code Examples

<details>
<summary><strong>C++</strong></summary>

```cpp
double pi = 3.1415926535;
printf("%.9f\n", pi); // Print with 9 decimal places
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
double pi = 3.1415926535;
System.out.printf("%.9f\n", pi);
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
pi = 3.1415926535
print(f"{pi:.9f}")
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
double pi = 3.1415926535;
printf("%.9f\n", pi);
```
</details>

---

## 3. Booleans (True/False)
Used for flags and logic conditions.

*   **Values:** `true` (1) or `false` (0).
*   **Size:** Usually 1 byte.

<details>
<summary><strong>C++</strong></summary>

```cpp
bool is_valid = true;
if (is_valid) cout << "Yes";
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
boolean isValid = true;
if (isValid) System.out.print("Yes");
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
is_valid = True  # Capital 'T'
if is_valid:
    print("Yes")
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
#include <stdbool.h> // Required for 'bool' in C99

bool is_valid = true;
if (is_valid) printf("Yes");
```
</details>

---

## 4. Characters & Strings (Text)
Used for processing text input.

*   **`char`:** A single character (e.g., 'A'). Stored as an integer (ASCII value).
*   **String:** A sequence of characters.

<details>
<summary><strong>C++</strong></summary>

```cpp
char c = 'A';
string s = "Hello World"; // Requires #include <string>
cout << s[0]; // Access first character ('H')
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
char c = 'A';
String s = "Hello World"; // Capital 'S'
System.out.print(s.charAt(0));
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
c = 'A'
s = "Hello World"
print(s[0])
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
char c = 'A';
char s[] = "Hello World"; // Array of chars
printf("%c", s[0]);
```
</details>
