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
