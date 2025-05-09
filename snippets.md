### 🔹 Big-O Notation  
Describes an **upper bound** on the growth rate of a function, f(n)=O(g(n)) means for sufficiently large n, f(n) ≤ C·g(n).  
```python
# e.g., f(n)=3n+2 is O(n) because 3n+2 ≤ 5n for n ≥ 2
```

---

### 🔹 Big-Θ Notation
Gives a tight bound: f(n)=Θ(g(n)) if C1·g(n) ≤ f(n) ≤ C2·g(n) for large n.

```python
# Merge Sort’s time is Θ(n log n) in worst and best cases.
```

---

### 🔹 Big-Ω Notation
Describes a lower bound: f(n)=Ω(g(n)) means f(n) ≥ C·g(n) for large n.

```python
# Insertion Sort is Ω(n) in best case (already sorted).
```

---

### 🔹 Worst-Case vs Best-Case
• Worst-case: max time over all inputs of size n. \
• Best-case: min time.

```python
# Linear search: best Ω(1), worst O(n)
```

---

### 🔹 Amortized Analysis
Average cost per operation over a sequence, smoothing out spikes.

```python
# Dynamic array resizing: occasional O(n) on grow, but amortized O(1) insert.
```

---

### 🔹 Master Theorem (Divide & Conquer)
Recurrence T(n)=aT(n/b)+f(n) leads to three cases for comparing f(n) to n^(log_b(a)).

```python
# Merge Sort: T(n)=2T(n/2) + Θ(n) ⇒ Θ(n log n)
```

---

### 🔹 Rule of Sum & Product
• Sum (sequential): f(n)+g(n)=O(max(f(n),g(n)))
• Product (nested): f(n)*g(n)=O(f(n)·g(n))

```python
# Two nested loops: O(n) + O(m) = O(n+m); O(n) + O(n) = O(n)
```
