<!-- content.md -->
📘 Topic: Algorithm Analysis (Complexities)

🧠 Overview  
Algorithm analysis is the foundation for evaluating how efficient an algorithm is in terms of time and space as the input size grows. We use **asymptotic notations**—Big-O, Big-Θ, and Big-Ω—to describe upper bounds, tight bounds, and lower bounds on an algorithm’s running time (or space usage). Understanding these helps you choose the right algorithm for large inputs and guide optimizations.

⏱ Time Complexity  

| Name             | Notation       | Growth Rate          | Example                      |
|------------------|----------------|----------------------|------------------------------|
| Constant         | O(1)           | 1                    | Accessing an array element  |
| Logarithmic      | O(log n)       | log n                | Binary Search               |
| Linear           | O(n)           | n                    | Single loop over an array   |
| Linearithmic     | O(n log n)     | n log n              | Merge Sort, Quick Sort (avg)|
| Quadratic        | O(n²)          | n²                   | Simple nested loops         |
| Exponential      | O(2ⁿ)          | 2ⁿ                   | Recursive Tower of Hanoi    |

> **Best-case, Average-case, Worst-case**  
> • *Best-case* (Ω) gives a lower bound (e.g., O(1) for binary search if the target is at the middle).  
> • *Average-case* often assumes a random distribution of inputs.  
> • *Worst-case* (O) is most critical for guarantees (e.g., quicksort’s O(n²) when pivot is always worst).

---

### 🔹 Optimized Idea  
To illustrate optimization, compare **linear search** (O(n)) vs **binary search** (O(log n)) on a sorted array:
1. **Linear search** scans each element until it finds the target.  
2. **Binary search** repeatedly splits the search interval in half.

By switching to binary search whenever the data is sorted, you reduce growth from linear to logarithmic—hugely significant for large n (e.g. n = 1 000 000 ⇒ 20 steps vs 1 000 000 steps).

---

### 🔹 Code Fragment  
```python
def binary_search(arr, target):
    lo, hi = 0, len(arr) - 1
    while lo <= hi:
        mid = (lo + hi) // 2
        if arr[mid] == target:
            return mid        # O(1) access
        elif arr[mid] < target:
            lo = mid + 1     # halves the search space
        else:
            hi = mid - 1
    return -1
# Overall time complexity: O(log n)
```

---

### 🔹 Binary Search
```python
def binary_search(arr, target):
    lo, hi = 0, len(arr) - 1
    while lo <= hi:
        mid = (lo + hi) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            lo = mid + 1
        else:
            hi = mid - 1
    return -1
# Worst-case: O(log n)
```

Switching from linear to binary search on sorted data reduces steps from n to log n—critical for large n.

---

### 🔹 Space Complexity
Measures extra memory usage. \
• In-place algorithms use O(1) extra space (e.g., in-place quicksort). \
• Not in-place may require O(n) auxiliary space (e.g., mergesort’s merge).

---

### 🔹 Amortized Analysis
Smooths out occasional expensive operations by averaging over a sequence. \
• Dynamic array resizing: occasional O(n) copy, but amortized O(1) per insert.

---

### 🔹 Master Theorem
For recurrences of form T(n) = a T(n/b) + f(n), compare f(n) to n^{log_b(a)}:

1. If f(n)=O(n^{log_b(a)−ε}), T(n)=Θ(n^{log_b(a)})
2. If f(n)=Θ(n^{log_b(a)}·log^k n), T(n)=Θ(n^{log_b(a)}·log^{k+1} n)
3. If f(n)=Ω(n^{log_b(a)+ε}) and regularity holds, T(n)=Θ(f(n))

> Example: Merge Sort \
> T(n)=2 T(n/2)+Θ(n) ⇒ case 2 ⇒ Θ(n log n)
