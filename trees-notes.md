# Logarithms

* What is a Logarithm?

    • Exponent Review:
        - An exponent represents how many times a number (the base) is multiplied by itself
        - Example: 2^5 = 2 x 2 x 2 x 2 x 2 = 32

    • Logarithm Definition:
        - A logarithm is the inverse of an exponent
        - The logarithm base-n of a number is the exponent to which the base must be raised to produce that number
        - Example: log2(32) = 5, because 2^5 = 32

    • Logarithm and Exponent Relationship
        - if b^x = y, then logb(y) = x
        - Example: 10^3 = 1000 means log10(1000) = 3


* Binary Logarithm (Base-2 Logarithm)
    • Binary Exponent Table:
        - 2^0 = 1
        - 2^1 = 2
        - 2^2 = 4
        - 2^3 = 8
        - 2^4 = 16
        - 2^5 = 32

    • Binary Logarithm Table:
        - log2(1) = 0
        - log2(2) = 1
        - log2(4) = 2
        - log2(8) = 3
        - log2(16) = 4
        - log2(32) = 5

    • Calculation in Code:
        - in JavaScript:

        ```js
        Math.log2(32) // 5
        ```

* Why Are Logarithms Important?

    • Growth Comparison
        - Logarithmic growth is much slower than linear (O(n)) or quadratic (O(n^2)) growth
        - Example: for large inputs, logarithmic functions grow very slowly, almost appearing constant on a graph

    • Real World Impact:
        - For large input sizes, algorithms with O(log n) complexity vastly outperform those with O(n) complexity
        - Example: to reach a logarithmic value of 100, n would need to be astronomically large (around 1.27 x 10^30)


* Summary
    • Logarithms: the inverse of exponents, telling you the number of times a base must be multiplied to reach a given value
    • Binary Logarithms: logarithms with base-2, crucial for understanding the performance of algorithms, particularly those with O(log n) complexity
    • Importance in Algorithms: logarithmic time complexity is extremely efficient, especially for large inputs, making it a key concept in optimising code performance


# Binary Search

1. Overview:
    • Purpose: efficiently search for a target value in a sorted array
    • Complexity: time complexity is O(log n), which is significantly faster than a linear search (O(n)) for large data sets

2. Divide and Conquer Approach:
    • Concept: binary search uses a divide-and-conquer strategy by repeatedly dividing the search range in half
    • Example: searching for "dictionary" in a dictionary by continuously splitting the range of pages in half until the target word is found

3. Preconditions for Binary Search:
    • Data must be sorted: the array or list needs to be in a sorted order
    • Constant-time access by index: the data structure must allow direct access to elements via indices (e.g. arrays)

4. Binary Search Algorithm:
    • Initial Setup:
        - Define two pointers: `lo` (start of the array) and `hi` (end of the array)
    • Midpoint Calculation:
        - Calculate the midpoint: `mid = (lo + hi) / 2`
    • Comparison:
        - Compare the target with `arr[mid]`
        - if `arr[mid] === target`, return `mid`
        - if `arr[mid] < target`, move the `lo` pointer to `mid + 1`
        - if `arr[mid] > target`, move the `hi` pointer to `mid - 1`
    • Repeat: continue the process until the target is found or `lo` exceeds `hi`
    • Return: if the target is not found, return `-1`

5. Pseudocode:

    ```js
    function binarySearch(arr, target) {
    lo = 0
    hi = arr.length - 1

    while (lo <= hi) {
        mid = Math.floor((lo + hi) / 2)

        if (arr[mid] == target) {
        return mid
        } else if (arr[mid] < target) {
        lo = mid + 1
        } else {
        hi = mid - 1
        }
    }

    return -1
    }
    ```

6. Performance Analysis:
    • Time Complexity: O(log n) due to halving the search space with each comparison
    • Space complexity: O(1) as only a few variables (lo, hi, mid) are used regardless of input size

7. Comparison with Linear Search:
    • Linear Search:
        - Compares each element sequentially until the target is found
        - Time complexity is O(n), making it inefficient for large datasets
    • Binary search:
        - Performs log base 2 comparisons, greatly reducing the number of checks needed

8. Practical Performance Test:
    • Experiment: run a binary search on a large dataset and compare its performance with linear search
    • Results: binary search typically performs significantly faster, especially as the dataset grows

9. Key Takeaways:
    • Binary search is an essential algorithm for efficiently finding elements in assorted arrays
    • Understanding its preconditions (sorted data and index access) and implementation is crucial for optimising search operations for software development
