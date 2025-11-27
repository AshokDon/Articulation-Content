# Arrays: Storing Collections

> **Goal:** Store multiple values of the same type in a single variable.

Arrays are the most fundamental data structure. They allow you to access data instantly using an index.

---

## 1. 1D Arrays (Fixed Size)
A list of elements with a specific size defined at creation.
*   **Indexing:** Starts at 0.
*   **Access:** $O(1)$ time complexity.

### Code Examples

<details>
<summary><strong>C++</strong></summary>

```cpp
int arr[5] = {10, 20, 30, 40, 50};

// Accessing
cout << arr[0] << endl; // 10

// Modifying
arr[2] = 99;

// Iterating
for (int i = 0; i < 5; i++) {
    cout << arr[i] << " ";
}
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
int[] arr = {10, 20, 30, 40, 50};

// Accessing
System.out.println(arr[0]); // 10

// Modifying
arr[2] = 99;

// Iterating
for (int i = 0; i < arr.length; i++) {
    System.out.print(arr[i] + " ");
}
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
# Python lists act as dynamic arrays
arr = [10, 20, 30, 40, 50]

// Accessing
print(arr[0]) # 10

// Modifying
arr[2] = 99

// Iterating
for x in arr:
    print(x, end=" ")
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
int arr[5] = {10, 20, 30, 40, 50};

// Accessing
printf("%d\n", arr[0]); // 10

// Modifying
arr[2] = 99;

// Iterating
for (int i = 0; i < 5; i++) {
    printf("%d ", arr[i]);
}
```
</details>

---

## 2. Dynamic Arrays (Resizable)
Used when you don't know the size beforehand or it changes.
*   **C++:** `std::vector`
*   **Java:** `ArrayList`
*   **Python:** `list` (Default)

### Code Examples

<details>
<summary><strong>C++ (Vector)</strong></summary>

```cpp
#include <vector>
using namespace std;

vector<int> v;
v.push_back(10); // Add to end
v.push_back(20);

cout << v.size(); // 2
```
</details>

<details>
<summary><strong>Java (ArrayList)</strong></summary>

```java
import java.util.ArrayList;

ArrayList<Integer> list = new ArrayList<>();
list.add(10); // Add to end
list.add(20);

System.out.println(list.size()); // 2
```
</details>

<details>
<summary><strong>Python (List)</strong></summary>

```python
v = []
v.append(10) # Add to end
v.append(20)

print(len(v)) # 2
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
// C does not have built-in dynamic arrays.
// You must use malloc/realloc manually (complex).
// In contests, just declare a large fixed array:
int arr[100005]; 
int size = 0;
arr[size++] = 10;
```
</details>

---

## 3. 2D Arrays (Matrices)
Used for grids, mazes, and tables. Think of it as an "array of arrays".

### Code Examples

<details>
<summary><strong>C++</strong></summary>

```cpp
int grid[3][3] = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};

cout << grid[1][2]; // Row 1, Col 2 -> 6
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
int[][] grid = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};

System.out.println(grid[1][2]); // 6
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
grid = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

print(grid[1][2]) # 6
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
int grid[3][3] = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};

printf("%d", grid[1][2]); // 6
```
</details>

---

## 4. Problem Solving Patterns
Knowing syntax isn't enough. Here are the standard techniques used to solve array problems.

### Pattern A: Frequency Array (Counting)
**Problem:** Given $N$ numbers (all $< 100$), count how many times each number appears.
**Idea:** Use the *value* of the number as the *index* of a count array.

<details>
<summary><strong>C++</strong></summary>

```cpp
int n = 7;
int arr[] = {1, 5, 1, 2, 5, 5, 3};
int count[101] = {0}; // Initialize with 0

for (int i = 0; i < n; i++) {
    count[arr[i]]++; // Increment index corresponding to value
}

// count[5] is now 3
// count[1] is now 2
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
int[] arr = {1, 5, 1, 2, 5, 5, 3};
int[] count = new int[101]; // Java inits to 0 by default

for (int x : arr) {
    count[x]++;
}
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
arr = [1, 5, 1, 2, 5, 5, 3]
count = [0] * 101

for x in arr:
    count[x] += 1
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
int arr[] = {1, 5, 1, 2, 5, 5, 3};
int count[101] = {0};

for (int i = 0; i < 7; i++) {
    count[arr[i]]++;
}
```
</details>

### Pattern B: Prefix Sums (Range Queries)
**Problem:** Calculate the sum of elements from index $L$ to $R$ many times.
**Idea:** Precompute a running total. `Sum(L, R) = P[R] - P[L-1]`.

<details>
<summary><strong>C++</strong></summary>

```cpp
int arr[] = {10, 20, 30, 40, 50};
int P[6] = {0}; // 1-based prefix array usually easier

// Build Prefix Array
for (int i = 0; i < 5; i++) {
    P[i+1] = P[i] + arr[i];
}
// P is {0, 10, 30, 60, 100, 150}

// Sum from index 1 to 3 (20+30+40 = 90)
// In 1-based P, this corresponds to P[4] - P[1]
int sum = P[4] - P[1]; // 100 - 10 = 90
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
int[] arr = {10, 20, 30, 40, 50};
int[] P = new int[6];

for (int i = 0; i < 5; i++) {
    P[i+1] = P[i] + arr[i];
}

int sum = P[4] - P[1]; // 90
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
arr = [10, 20, 30, 40, 50]
P = [0] * 6

for i in range(5):
    P[i+1] = P[i] + arr[i]

sum_val = P[4] - P[1] # 90
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
int arr[] = {10, 20, 30, 40, 50};
int P[6] = {0};

for (int i = 0; i < 5; i++) {
    P[i+1] = P[i] + arr[i];
}

int sum = P[4] - P[1];
```
</details>

### Pattern C: Two Pointers (Reversing)
**Problem:** Reverse an array without creating a new one.
**Idea:** Swap the first and last elements, then move inward.

<details>
<summary><strong>C++</strong></summary>

```cpp
int arr[] = {1, 2, 3, 4, 5};
int L = 0, R = 4;

while (L < R) {
    swap(arr[L], arr[R]);
    L++;
    R--;
}
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
int[] arr = {1, 2, 3, 4, 5};
int L = 0, R = 4;

while (L < R) {
    int temp = arr[L];
    arr[L] = arr[R];
    arr[R] = temp;
    L++;
    R--;
}
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
arr = [1, 2, 3, 4, 5]
L, R = 0, 4

while L < R:
    arr[L], arr[R] = arr[R], arr[L]
    L += 1
    R -= 1
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
int arr[] = {1, 2, 3, 4, 5};
int L = 0, R = 4;

while (L < R) {
    int temp = arr[L];
    arr[L] = arr[R];
    arr[R] = temp;
    L++;
    R--;
}
```
</details>
