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
