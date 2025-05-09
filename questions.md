
### Q1: What does f(n)=O(g(n)) mean?  
**A1:** There exist constants C>0 and n₀ such that for all n ≥ n₀, f(n) ≤ C·g(n).  

---

### Q2: Give the worst-case time complexity of Quick Sort and explain when it occurs.  
**A2:** O(n²), which happens if the pivot always splits off one element (e.g., sorted input with naïve pivot choice).  

---

### Q3: Why is Merge Sort Θ(n log n) in all cases?  
**A3:** It always divides the array in half (log n levels) and merges in linear time per level (n work), so total n·log n.  

---

### Q4: What’s the difference between O(n²) and Ω(n²)?  
**A4:** O(n²) is an upper bound (actual growth ≤ n² asymptotically), Ω(n²) is a lower bound (growth ≥ n² asymptotically).  

---

### Q5: Explain amortized O(1) insertion in dynamic arrays.  
**A5:** Although occasionally an insert triggers O(n) resizing, the cost averaged over many inserts is constant.  

---

### Q6: For T(n)=3T(n/4)+n, use the Master Theorem to find T(n).  
**A6:** Compare n to n^{log₄(3)}≈n^{0.79}, since n grows faster ⇒ T(n)=Θ(n).  
