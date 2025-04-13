
📘 Topic: Algorithm Analysis
🧠 Overview
Algorithm analysis is the foundation of evaluating how efficient an algorithm is in terms of time and space. It allows us to compare solutions before implementation and ensures scalability as input sizes grow.

We typically measure an algorithm’s performance using asymptotic notations such as Big-O, Big-Theta, and Big-Omega.

⏱ Time Complexity
Time complexity estimates how the execution time of an algorithm increases with input size n.

Name	Growth Rate	Example
Constant	O(1)	Accessing array element
Logarithmic	O(log n)	Binary Search
Linear	O(n)	Traversing an array
Linearithmic	O(n log n)	Merge Sort, Quick Sort (avg)
Quadratic	O(n^2)	Nested loops (e.g., bubble sort)
Exponential	O(2^n)	Solving Tower of Hanoi

❗ Worst vs Best vs Average Case
Worst case (Big-O): Upper bound on running time

Best case (Big-Omega): Lower bound (rarely used alone)

Average case (Big-Theta): Expected running time on average input

💾 Space Complexity
Space complexity refers to the additional memory used by the algorithm, not including input size.

Examples:

Using recursion consumes call stack space

Using a hash map for lookups adds O(n) space

🔄 Recursive Algorithm Analysis
Many recursive algorithms follow a pattern that can be described using recurrence relations.

Example: Merge Sort
python
Copy
Edit
T(n) = 2T(n/2) + O(n)
We solve this using the Master Theorem:

If T(n) = aT(n/b) + O(n^d), then:

If d < log_b(a) → T(n) = Θ(n^log_b(a))

If d = log_b(a) → T(n) = Θ(n^d * log n)

If d > log_b(a) → T(n) = Θ(n^d)

For Merge Sort:

a = 2, b = 2, d = 1 → d = log₂(2) → T(n) = Θ(n log n)

📈 Comparing Algorithms
Even with the same result, two algorithms may have very different performance.

Problem	Algorithm A	Algorithm B
Search in sorted array	Linear Search O(n)	Binary Search O(log n)
Sorting	Bubble Sort O(n^2)	Merge Sort O(n log n)
Conclusion: Always consider time & space tradeoffs when choosing your approach.

🧩 Key Takeaways
Big-O measures the upper bound on time or space.

Time and space complexity help evaluate algorithms before coding.

Recursion often leads to recurrence relations.

Master Theorem is essential for analyzing divide-and-conquer algorithms.

