# Operators: The Tools of Logic

> **Goal:** Manipulate data, make decisions, and optimize calculations using the right operators.

Operators are the symbols that tell the compiler to perform specific mathematical or logical manipulations.

### Theory: Precedence & Associativity
Just like in math ($3 + 4 \times 5 = 23$, not $35$), programming operators have an order of operations.
*   **Precedence:** Which operator happens first. `*` and `/` happen before `+` and `-`.
*   **Associativity:** Direction of evaluation (usually Left-to-Right).
*   **Tip:** When in doubt, use **parentheses `()`**. They have the highest precedence and make your code readable.

---

## 1. Arithmetic Operators
Used for basic math.
*   **Standard:** `+`, `-`, `*`, `/`
*   **Modulo (`%`):** Remainder after division. Crucial for "cyclic" problems or checking divisibility.
*   **Increment/Decrement:** `++`, `--` (Not in Python).

### Code Examples

<details>
<summary><strong>C++</strong></summary>

```cpp
int a = 10, b = 3;
cout << (a + b) << endl; // 13
cout << (a / b) << endl; // 3 (Integer division truncates!)
cout << (a % b) << endl; // 1 (Remainder)
a++; // a becomes 11
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
int a = 10, b = 3;
System.out.println(a + b); // 13
System.out.println(a / b); // 3
System.out.println(a % b); // 1
a++; // a becomes 11
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
a = 10
b = 3
print(a + b)  # 13
print(a / b)  # 3.333... (Float division!)
print(a // b) # 3 (Integer division)
print(a % b)  # 1
a += 1        # Python has no ++
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
int a = 10, b = 3;
printf("%d\n", a + b); // 13
printf("%d\n", a / b); // 3
printf("%d\n", a % b); // 1
a++;
```
</details>

---

## 2. Relational Operators
Used to compare two values. Returns `true` or `false`.
*   `==` (Equal to)
*   `!=` (Not equal to)
*   `>` (Greater than), `<` (Less than)
*   `>=` (Greater or equal), `<=` (Less or equal)

### Code Examples

<details>
<summary><strong>C++</strong></summary>

```cpp
int x = 5, y = 10;
if (x < y) cout << "x is smaller";
if (x == 5) cout << "x is 5";
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
int x = 5, y = 10;
if (x < y) System.out.println("x is smaller");
if (x == 5) System.out.println("x is 5");
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
x = 5
y = 10
if x < y: print("x is smaller")
if x == 5: print("x is 5")
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
int x = 5, y = 10;
if (x < y) printf("x is smaller");
if (x == 5) printf("x is 5");
```
</details>

---

## 3. Logical Operators
Used to combine multiple conditions.
*   **AND:** `&&` (C/Java), `and` (Python) - True if *both* are true.
*   **OR:** `||` (C/Java), `or` (Python) - True if *at least one* is true.
*   **NOT:** `!` (C/Java), `not` (Python) - Reverses the boolean value.

### Code Examples

<details>
<summary><strong>C++</strong></summary>

```cpp
bool has_ticket = true;
bool is_vip = false;

if (has_ticket || is_vip) {
    cout << "Allowed";
}
if (has_ticket && !is_vip) {
    cout << "Regular Entry";
}
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
boolean hasTicket = true;
boolean isVip = false;

if (hasTicket || isVip) {
    System.out.println("Allowed");
}
if (hasTicket && !isVip) {
    System.out.println("Regular Entry");
}
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
has_ticket = True
is_vip = False

if has_ticket or is_vip:
    print("Allowed")
if has_ticket and not is_vip:
    print("Regular Entry")
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
int has_ticket = 1; // 1 is true
int is_vip = 0;     // 0 is false

if (has_ticket || is_vip) printf("Allowed");
if (has_ticket && !is_vip) printf("Regular Entry");
```
</details>

---

## 4. Bitwise Operators
Operates directly on the binary bits of integers. Very fast and useful for subsets/masks.
*   `&` (AND), `|` (OR), `^` (XOR)
*   `~` (NOT/Complement)
*   `<<` (Left Shift - Multiply by 2), `>>` (Right Shift - Divide by 2)

### Code Examples

<details>
<summary><strong>C++</strong></summary>

```cpp
int a = 5;      // 0101
int b = 3;      // 0011

cout << (a & b) << endl; // 0001 -> 1
cout << (a | b) << endl; // 0111 -> 7
cout << (a ^ b) << endl; // 0110 -> 6
cout << (a << 1) << endl; // 1010 -> 10 (Doubled)
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
int a = 5;
int b = 3;

System.out.println(a & b); // 1
System.out.println(a | b); // 7
System.out.println(a ^ b); // 6
System.out.println(a << 1); // 10
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
a = 5
b = 3

print(a & b)  # 1
print(a | b)  # 7
print(a ^ b)  # 6
print(a << 1) # 10
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
int a = 5, b = 3;
printf("%d\n", a & b); // 1
printf("%d\n", a | b); // 7
printf("%d\n", a ^ b); // 6
printf("%d\n", a << 1); // 10
```
</details>
