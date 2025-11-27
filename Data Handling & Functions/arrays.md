# Strings: Text Processing

> **Goal:** Manipulate sequences of characters efficiently.

Strings are fundamental for processing text, parsing input, and solving problems involving patterns or anagrams.

---

## 1. Basics & Declaration
A string is essentially an array of characters.

<details>
<summary><strong>C++</strong></summary>

```cpp
#include <string>
using namespace std;

string s = "Hello";
cout << s;
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
String s = "Hello";
System.out.println(s);
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
s = "Hello"
print(s)
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
char s[] = "Hello";
printf("%s", s);
```
</details>

---

## 2. Common Operations
Key operations: Finding length, accessing characters, and joining strings.

### Code Examples

<details>
<summary><strong>C++</strong></summary>

```cpp
string s = "Code";

// Length
int len = s.length(); // 4

// Access
char c = s[0]; // 'C'

// Concatenation
string s2 = s + "Forces"; // "CodeForces"
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
String s = "Code";

// Length
int len = s.length(); // 4

// Access
char c = s.charAt(0); // 'C'

// Concatenation
String s2 = s + "Forces"; // "CodeForces"
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
s = "Code"

# Length
length = len(s) # 4

# Access
c = s[0] # 'C'

# Concatenation
s2 = s + "Forces" # "CodeForces"
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
#include <string.h>

char s[20] = "Code";

// Length
int len = strlen(s); // 4

// Access
char c = s[0]; // 'C'

// Concatenation
strcat(s, "Forces"); // s becomes "CodeForces"
```
</details>

---

## 3. Mutability (Important!)
*   **Mutable (Changeable):** C++, C. You can change `s[0] = 'X'`.
*   **Immutable (Unchangeable):** Java, Python. You **cannot** do `s[0] = 'X'`. You must create a new string.

<details>
<summary><strong>C++ (Mutable)</strong></summary>

```cpp
string s = "Hello";
s[0] = 'J'; 
// s is now "Jello"
```
</details>

<details>
<summary><strong>Java (Immutable)</strong></summary>

```java
String s = "Hello";
// s.charAt(0) = 'J'; // ERROR!
s = "J" + s.substring(1); // Creates NEW string "Jello"
```
</details>

<details>
<summary><strong>Python (Immutable)</strong></summary>

```python
s = "Hello"
# s[0] = 'J' # ERROR!
s = "J" + s[1:] # Creates NEW string "Jello"
```
</details>

---

## 4. Problem Solving Patterns

### Pattern A: Iterating Characters
**Problem:** Count the number of 'A's in a string.

<details>
<summary><strong>C++</strong></summary>

```cpp
string s = "BANANA";
int count = 0;
for (char c : s) {
    if (c == 'A') count++;
}
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
String s = "BANANA";
int count = 0;
for (char c : s.toCharArray()) {
    if (c == 'A') count++;
}
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
s = "BANANA"
count = 0
for c in s:
    if c == 'A': count += 1
```
</details>

### Pattern B: Substrings
**Problem:** Extract the first 3 characters.

<details>
<summary><strong>C++</strong></summary>

```cpp
string s = "HelloWorld";
// substr(start_index, length)
string sub = s.substr(0, 3); // "Hel"
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
String s = "HelloWorld";
// substring(start_index, end_index_exclusive)
String sub = s.substring(0, 3); // "Hel"
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
s = "HelloWorld"
# s[start : end_exclusive]
sub = s[0:3] # "Hel"
```
</details>

### Pattern C: Efficient Building
**Problem:** Append numbers 0 to 1000 to a string.
*   **Bad:** `s += str(i)` (Slow in Java/Python due to immutability).
*   **Good:** Use a Builder.

<details>
<summary><strong>Java (StringBuilder)</strong></summary>

```java
StringBuilder sb = new StringBuilder();
for (int i = 0; i < 1000; i++) {
    sb.append(i);
}
String res = sb.toString();
```
</details>

<details>
<summary><strong>Python (List Join)</strong></summary>

```python
parts = []
for i in range(1000):
    parts.append(str(i))
res = "".join(parts)
```
</details>
