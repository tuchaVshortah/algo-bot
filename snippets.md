### 🔹 Big-O Notation  
Describes an **upper bound** on the growth rate of a function, f(n)=O(g(n)) means for sufficiently large n, f(n) ≤ C·g(n).  
```python
# e.g., f(n)=3n+2 is O(n) because 3n+2 ≤ 5n for n ≥ 2
# Example of O(n) - Linear Time Complexity
def linear_search(arr, target):
    for element in arr:
        if element == target:
            return True
    return False
# Worst-case time complexity: O(n)
```

---

### 🔹 Big-Θ Notation
Gives a tight bound: f(n)=Θ(g(n)) if C1·g(n) ≤ f(n) ≤ C2·g(n) for large n.

```python
# Merge Sort’s time is Θ(n log n) in worst and best cases.
def merge_sort(arr):
    if len(arr) <= 1:
        return arr
    mid = len(arr) // 2
    left = merge_sort(arr[:mid])
    right = merge_sort(arr[mid:])
    return merge(left, right)
```

---

### 🔹 Big-Ω Notation
Describes a lower bound: f(n)=Ω(g(n)) means f(n) ≥ C·g(n) for large n.

```python
# Insertion Sort - Best case is Ω(n) when the array is already sorted
def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        while j >= 0 and arr[j] > key:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key

```

---

### 🔹 Worst-Case vs Best-Case
• Worst-case: max time over all inputs of size n. \
• Best-case: min time.

```python
# Linear search: Best case is Ω(1), worst case is O(n)
def linear_search(arr, target):
    for i, v in enumerate(arr):
        if v == target:
            return i
    return -1
```

---

### 🔹 Amortized Analysis
Average cost per operation over a sequence, smoothing out spikes.

```python
# Dynamic array resizing: occasional O(n) on grow, but amortized O(1) insert
class DynamicArray:
    def __init__(self):
        self.array = []
        self.capacity = 1

    def append(self, value):
        if len(self.array) >= self.capacity:
            self._resize()
        self.array.append(value)

    def _resize(self):
        self.capacity *= 2
        new_array = [0] * self.capacity
        for i in range(len(self.array)):
            new_array[i] = self.array[i]
        self.array = new_array

```

---

### 🔹 Master Theorem (Divide & Conquer)
Recurrence T(n)=aT(n/b)+f(n) leads to three cases for comparing f(n) to n^(log_b(a)).

```python
# Example: Merge Sort - T(n) = 2T(n/2) + Θ(n)
def merge_sort(arr):
    if len(arr) <= 1:
        return arr
    mid = len(arr) // 2
    left = merge_sort(arr[:mid])
    right = merge_sort(arr[mid:])
    return merge(left, right)

```

---

### 🔹 Rule of Sum & Product
• Sum (sequential): f(n)+g(n)=O(max(f(n),g(n))) \
• Product (nested): f(n)*g(n)=O(f(n)·g(n))

```python
# Example of nested loops - O(n * m)
def nested_loops(n, m):
    for i in range(n):
        for j in range(m):
            print(i, j)
```
