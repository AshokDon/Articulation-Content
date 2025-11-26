# Input and Output: Speed Matters

> **Goal:** Read data and print answers fast enough to avoid **Time Limit Exceeded (TLE)**.

In competitive programming, reading $10^6$ integers can take longer than processing them if you use slow I/O methods.

---

## 1. Standard I/O
The basic way to read from the console and print to it.

### Code Examples

<details>
<summary><strong>C++</strong></summary>

```cpp
#include <iostream>
using namespace std;

int main() {
    int a;
    string s;
    
    cin >> a >> s;       // Reads integer and string
    cout << a << " " << s << endl; // Prints output
    return 0;
}
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        
        if (sc.hasNext()) {
            int a = sc.nextInt();
            String s = sc.next();
            System.out.println(a + " " + s);
        }
        sc.close();
    }
}
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
# Reads a line and splits it
line = input().split() 
a = int(line[0])
s = line[1]

print(f"{a} {s}")
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
#include <stdio.h>

int main() {
    int a;
    char s[100];
    
    scanf("%d %s", &a, s);
    printf("%d %s\n", a, s);
    return 0;
}
```
</details>

---

## 2. Fast I/O (Crucial for $N \ge 10^5$)
Standard methods like `cin` and `Scanner` can be too slow when input is huge.

### Code Examples

<details>
<summary><strong>C++ (The Magic Lines)</strong></summary>

```cpp
#include <iostream>
using namespace std;

int main() {
    // Add these two lines at the start of main
    ios::sync_with_stdio(0);
    cin.tie(0);
    
    // Now use cin/cout as normal, but it's much faster!
    // Avoid using endl (use "\n" instead)
    int n;
    cin >> n;
    cout << n << "\n"; 
    return 0;
}
```
</details>

<details>
<summary><strong>Java (BufferedReader)</strong></summary>

```java
import java.io.*;
import java.util.StringTokenizer;

public class Main {
    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        PrintWriter out = new PrintWriter(System.out);
        
        StringTokenizer st = new StringTokenizer(br.readLine());
        int n = Integer.parseInt(st.nextToken());
        
        out.println(n);
        out.close(); // Don't forget to close!
    }
}
```
</details>

<details>
<summary><strong>Python (sys.stdin)</strong></summary>

```python
import sys

# Read all input at once or line by line
input = sys.stdin.readline

n = int(input())
sys.stdout.write(str(n) + "\n")
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
// scanf/printf are already fast enough!
// No special optimization needed.
```
</details>

---

## 3. File I/O (Using `freopen`)
Some contests (like older USACO) require reading from a file named `problem.in` and writing to `problem.out`.

### Code Examples

<details>
<summary><strong>C++</strong></summary>

```cpp
int main() {
    freopen("problem.in", "r", stdin);
    freopen("problem.out", "w", stdout);
    
    // Use cin/cout normally
    int n;
    cin >> n;
    cout << n;
    return 0;
}
```
</details>

<details>
<summary><strong>Java</strong></summary>

```java
import java.io.*;
import java.util.*;

public class Main {
    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new FileReader("problem.in"));
        PrintWriter out = new PrintWriter(new BufferedWriter(new FileWriter("problem.out")));
        
        // ... code ...
        
        out.close();
    }
}
```
</details>

<details>
<summary><strong>Python</strong></summary>

```python
import sys

sys.stdin = open("problem.in", "r")
sys.stdout = open("problem.out", "w")

# Use input()/print() normally
```
</details>

<details>
<summary><strong>C</strong></summary>

```c
int main() {
    freopen("problem.in", "r", stdin);
    freopen("problem.out", "w", stdout);
    
    // Use scanf/printf normally
    return 0;
}
```
</details>
