```
---
aliases:
---
```

Tags:

# Big O Notation
In [computer science](https://en.wikipedia.org/wiki/Computer_science "Computer science"), big O notation is used to [classify algorithms](https://en.wikipedia.org/wiki/Computational_complexity_theory) according to how their run time or space requirements grow as the input size grows. In [analytic number theory](https://en.wikipedia.org/wiki/Analytic_number_theory "Analytic number theory"), big O notation is often used to express a bound on the difference between an [arithmetical function](https://en.wikipedia.org/wiki/Arithmetic_function "Arithmetic function") and a better understood approximation; a famous example of such a difference is the remainder term in the [prime number theorem](https://en.wikipedia.org/wiki/Prime_number_theorem "Prime number theorem"). Big O notation is also used in many other fields to provide similar estimates.

## List of Notations

Here is a list of classes of functions that are commonly encountered when analyzing the running time of an algorithm. In each case, _c_ is a positive constant and _n_ increases without bound. The slower-growing functions are generally listed first.

Notation | Name | Example
--- | --- | ---
O(1) | [constant](https://en.wikipedia.org/wiki/Constant_time "Bell number") | Determining if a binary number is even or odd
O(log log _n_) | double logarithmic | Number of comparisons spent finding an item using [interpolation search](https://en.wikipedia.org/wiki/Interpolation_search "Interpolation search") in a sorted array of uniformly distributed values
O(log _n_) | [logarithmic](https://en.wikipedia.org/wiki/Logarithmic_time "Time complexity") | Finding an item in a sorted array with a [binary search](https://en.wikipedia.org/wiki/Binary_search_algorithm "Binary search algorithm") or a balanced search [tree](https://en.wikipedia.org/wiki/Tree_data_structure) as well as all operations in a [Binomial heap](https://en.wikipedia.org/wiki/Binomial_heap "Polylogarithmic time")
O((log _n_)$^c$) _c>1_ | [polylogarithmic](https://en.wikipedia.org/wiki/Polylogarithmic_time) | Matrix chain ordering can be solved in polylogarithmic time on a [parallel random-access machine](https://en.wikipedia.org/wiki/Parallel_random-access_machine)
O(n$^c$)  _0<c<1_ | fractional power | Searching in a [k-d tree](https://en.wikipedia.org/wiki/K-d_tree "K-d tree")
O(n) | [linear](https://en.wikipedia.org/wiki/Linear_time "Parallel random-access machine") | Finding an item in an unsorted list or in an unsorted array; adding two _n_-bit integers by [ripple carry](https://en.wikipedia.org/wiki/Ripple_carry_adder "Ripple carry adder")
O(n$^2$) | [quadratic](https://en.wikipedia.org/wiki/Quadratic_time "Quadratic time") | Multiplying two _n_-digit numbers by a simple algorithm; simple sorting algorithms, such as [bubble sort](https://en.wikipedia.org/wiki/Bubble_sort "Travelling salesman problem"), [selection sort](https://en.wikipedia.org/wiki/Selection_sort) and [insertion sort](https://en.wikipedia.org/wiki/Insertion_sort "Insertion sort"); (worst case) bound on some usually faster sorting algorithms such as [quicksort](https://en.wikipedia.org/wiki/Quicksort "Quicksort"), [Shellsort](https://en.wikipedia.org/wiki/Shellsort "Shellsort"), and [tree sort](https://en.wikipedia.org/wiki/Tree_sort "Tree sort")
O(n$^c$) | [polynomial](https://en.wikipedia.org/wiki/Polynomial_time "Polynomial time") or algebraic | [Tree-adjoining grammar](https://en.wikipedia.org/wiki/Tree-adjoining_grammar "Tree-adjoining grammar") parsing; maximum [matching](https://en.wikipedia.org/wiki/Matching_(graph_theory) "Matching (graph theory)") for [bipartite graphs](https://en.wikipedia.org/wiki/Bipartite_graph "Bipartite graph"); finding the [determinant](https://en.wikipedia.org/wiki/Determinant) with [LU decomposition](https://en.wikipedia.org/wiki/LU_decomposition "LU decomposition")
O(n!) | [factorial](https://en.wikipedia.org/wiki/Factorial "Factorial") | Solving the [travelling salesman problem](https://en.wikipedia.org/wiki/Travelling_salesman_problem) via brute-force search; generating all unrestricted permutations of a [poset](https://en.wikipedia.org/wiki/Partially_ordered_set "Partially ordered set"); finding the [determinant](https://en.wikipedia.org/wiki/Determinant "Determinant") with [Laplace expansion](https://en.wikipedia.org/wiki/Laplace_expansion); enumerating [all partitions of a set](https://en.wikipedia.org/wiki/Bell_number)

Complete list [here](https://en.wikipedia.org/wiki/Big_O_notation#Orders_of_common_functions)