# Solution: SubArrayRangeSum

In this section, we will explore different approaches to solve the `SubArrayRangeSum` problem, progressing from the brute force method to the most efficient solution. Solutions will be provided in C++, Java, and Python.

---

## Approach 1: Brute Force

### Idea
For each query, iterate through the subarray from index `l` to `r` and compute the sum. This approach has a time complexity of \(O(q \times (r - l))\), which can be slow for large inputs.

### Complexity
- **Time Complexity:** \(O(q \times n)\)
- **Space Complexity:** \(O(1)\)

### Code

#### C++
```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    int n, q;
    cin >> n >> q;
    vector<int> arr(n);
    for (int i = 0; i < n; i++) {
        cin >> arr[i];
    }
    while (q--) {
        int l, r;
        cin >> l >> r;
        int sum = 0;
        for (int i = l; i <= r; i++) {
            sum += arr[i];
        }
        cout << sum << endl;
    }
    return 0;
}
```

#### Java
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int q = sc.nextInt();
        int[] arr = new int[n];
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }
        while (q-- > 0) {
            int l = sc.nextInt();
            int r = sc.nextInt();
            int sum = 0;
            for (int i = l; i <= r; i++) {
                sum += arr[i];
            }
            System.out.println(sum);
        }
        sc.close();
    }
}
```

#### Python
```python
n, q = map(int, input().split())
arr = list(map(int, input().split()))
for _ in range(q):
    l, r = map(int, input().split())
    print(sum(arr[l:r+1]))
```

---

## Approach 2: Prefix Sum

### Idea
Use a prefix sum array to store cumulative sums. For any query, the sum of elements from `l` to `r` can be calculated as:
\[
\text{sum} = \text{prefix}[r+1] - \text{prefix}[l]
\]
This reduces the time complexity for each query to \(O(1)\) after preprocessing.

### Complexity
- **Preprocessing Time Complexity:** \(O(n)\)
- **Query Time Complexity:** \(O(q)\)
- **Space Complexity:** \(O(n)\)

### Code

#### C++
```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    int n, q;
    cin >> n >> q;
    vector<int> arr(n), prefix(n + 1, 0);
    for (int i = 0; i < n; i++) {
        cin >> arr[i];
        prefix[i + 1] = prefix[i] + arr[i];
    }
    while (q--) {
        int l, r;
        cin >> l >> r;
        cout << prefix[r + 1] - prefix[l] << endl;
    }
    return 0;
}
```

#### Java
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int q = sc.nextInt();
        int[] arr = new int[n];
        int[] prefix = new int[n + 1];
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
            prefix[i + 1] = prefix[i] + arr[i];
        }
        while (q-- > 0) {
            int l = sc.nextInt();
            int r = sc.nextInt();
            System.out.println(prefix[r + 1] - prefix[l]);
        }
        sc.close();
    }
}
```

#### Python
```python
n, q = map(int, input().split())
arr = list(map(int, input().split()))
prefix = [0] * (n + 1)
for i in range(n):
    prefix[i + 1] = prefix[i] + arr[i]
for _ in range(q):
    l, r = map(int, input().split())
    print(prefix[r + 1] - prefix[l])
```

---

## Comparison

| Approach      | Preprocessing Time | Query Time | Space Complexity |
|---------------|--------------------|------------|------------------|
| Brute Force   | \(O(1)\)           | \(O(n)\)   | \(O(1)\)         |
| Prefix Sum    | \(O(n)\)           | \(O(1)\)   | \(O(n)\)         |

The prefix sum approach is significantly faster for large inputs with multiple queries due to its efficient preprocessing and query handling.
