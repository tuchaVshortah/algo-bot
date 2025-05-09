### Problem 1: Analyze the following loop nest  
```python
for i in range(n):
    for j in range(i, n):
        # constant-time work
        a[i][j] = i + j
```

• Hint: Count number of (i,j) pairs. \
• Solution:
> ∑_{i=0 to n-1}(n−i) = n + (n−1)+…+1 = n(n+1)/2 = Θ(n²).

---

### Problem 2: Solve the recurrence
```python
T(n) = 2T(n/2) + n
```

• Hint: Use Master Theorem: a=2, b=2, f(n)=n. \
• Solution:
> n^{log₂2}=n; f(n)=Θ(n^{log₂2}) ⇒ T(n)=Θ(n log n).

---

### Problem 3: Compare two search algorithms

Given a sorted array of size n, which is faster:
1. Linear search
2. Binary search

• Hint: Write their worst-case time.
• Solution:
  1. O(n)
  2. O(log n)
⇒ Binary search is asymptotically faster for large n.

---

### Problem 4: Amortized cost of stack with occasional doubling
A stack starts empty; on overflow it doubles capacity. Show that n push operations take O(n) total time.

• Hint: Account for each element’s moves across resizing. \
• Solution: \
  Total copy cost ≤ 1 + 2 + 4 + … + n = 2n−1 = O(n); spread across n pushes ⇒ O(1) amortized.

---

### Problem 5: Master Theorem edge case

T(n) = 4T(n/2) + n² log n

• Hint: Compare f(n) = n² log n to n^{log₂4}=n². \
• Solution: \
  f(n)=Θ(n² log n) = Θ(n^{log_b a}·log n) ⇒ T(n)=Θ(n² log² n) (Case 2 with extra log factor).
