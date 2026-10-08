# Algorithms & Complexity Analysis

A collection of foundational computer science algorithms, classic algorithmic problem solutions.
---

## Repository Structure

```text
.
├── problems/
│   └── maximumSubArr.ipynb       # Maximum Subarray problem via Divide and Conquer
└── sortingAlgorithems/
    └── algorithem.ipynb          # Sorting algorithms & empirical runtime benchmark
```

---

## Contents

### 1. Sorting Algorithms (`sortingAlgorithems/algorithem.ipynb`)

Implementations of classic comparison-based and non-comparison (linear/distribution) sorting algorithms, accompanied by empirical benchmark tests comparing execution times on random datasets of varying sizes.

#### Complexity Summary

| Algorithm | Best Time | Average Time | Worst Time | Space Complexity | Paradigm / Classification |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Bubble Sort** | $\mathcal{O}(n)$ | $\mathcal{O}(n^2)$ | $\mathcal{O}(n^2)$ | $\mathcal{O}(1)$ | Comparison / Exchange (with swapped flag) |
| **Insertion Sort** | $\mathcal{O}(n)$ | $\mathcal{O}(n^2)$ | $\mathcal{O}(n^2)$ | $\mathcal{O}(1)$ | Comparison / Incremental Insertion |
| **Selection Sort** | $\mathcal{O}(n^2)$ | $\mathcal{O}(n^2)$ | $\mathcal{O}(n^2)$ | $\mathcal{O}(1)$ | Comparison / Selection |
| **Heap Sort** | $\mathcal{O}(n \log n)$ | $\mathcal{O}(n \log n)$ | $\mathcal{O}(n \log n)$ | $\mathcal{O}(1)$ | Comparison / Heap Data Structure |
| **Merge Sort** | $\mathcal{O}(n \log n)$ | $\mathcal{O}(n \log n)$ | $\mathcal{O}(n \log n)$ | $\mathcal{O}(n)$ | Comparison / Divide and Conquer |
| **Quick Sort** | $\mathcal{O}(n \log n)$ | $\mathcal{O}(n \log n)$ | $\mathcal{O}(n^2)$ | $\mathcal{O}(n)$ | Comparison / Divide and Conquer (middle pivot) |
| **Counting Sort** | $\mathcal{O}(n + k)$ | $\mathcal{O}(n + k)$ | $\mathcal{O}(n + k)$ | $\mathcal{O}(n + k)$ | Non-comparison / Integer Key Counting |
| **Radix Sort** | $\mathcal{O}(d \cdot (n + b))$ | $\mathcal{O}(d \cdot (n + b))$ | $\mathcal{O}(d \cdot (n + b))$ | $\mathcal{O}(n + b)$ | Non-comparison / LSD Digit Sorting (Base 10) |
| **Bucket Sort** | $\mathcal{O}(n + k)$ | $\mathcal{O}(n + k)$ | $\mathcal{O}(n^2)$ | $\mathcal{O}(n)$ | Non-comparison / Distribution + Insertion Sort |

*Notes:*
- $n$: number of elements.
- $k$: range of input values ($\max - \min + 1$).
- $d$: maximum number of digits in the input numbers.
- $b$: base/radix used (e.g., base 10).

#### Empirical Runtime Analysis

The notebook includes a comparative benchmark that measures execution times across input sizes ranging from $n = 100$ up to $n = 20,000$ using randomly generated input arrays:
- Benchmarks execution time via Python's `time` module with copy isolation.
- Visualizes scaling behavior and runtime growth using `matplotlib` plots to observe how $\mathcal{O}(n^2)$ algorithms deviate from $\mathcal{O}(n \log n)$ and linear-time algorithms as $n$ scales.

---

### 2. Algorithmic Problems (`problems/maximumSubArr.ipynb`)

#### Maximum Subarray Problem (Divide and Conquer)
- **Problem Formulation:** Finds the contiguous subarray within a one-dimensional array of numbers that has the largest sum.
- **Approach:**
  - Recursively splits the array into left and right halves.
  - Computes:
    1. Maximum subarray entirely in the left half (`Left_MSS`).
    2. Maximum subarray entirely in the right half (`Right_MSS`).
    3. Maximum subarray spanning across the midpoint (`Crossing_Sum`).
  - Returns `max(Left_MSS, Right_MSS, Crossing_Sum)`.
- **Recurrence & Complexity:**
  - Recurrence Relation: $T(n) = 2T(n/2) + \Theta(n)$
  - **Time Complexity:** $\mathcal{O}(n \log n)$ by the Master Theorem.
  - **Space Complexity:** $\mathcal{O}(\log n)$ due to the recursive call stack.
