<details><summary><h2>▶ Data Types Knowledge</h2></summary>

In Java, selecting the right data type is a core skill for writing efficient and correct code. This becomes critical in **competitive coding** and **mathematical computations**, where performance limits and precise numerical boundaries determine whether your solution gets accepted.

### Why Data Types Matter in Competitive Coding & Math

* **Preventing Integer Overflow:**
  Standard integer types like `int` can only store values up to $2 \times 10^9$ ($2^{31}-1$). In competitive programming, intermediate calculations (such as factorials, array sums, or matrix multiplications) frequently exceed this limit. Failing to switch to `long` (up to $9 \times 10^{18}$) or `BigInteger` causes silent overflow, resulting in incorrect negative numbers and failed test cases.

* **Precision in Floating-Point Math:**
  Using `float` only provides ~6-7 decimal digits of precision, which leads to rounding errors in high-precision math problems. Using `double` provides 15-17 decimal digits. For financial or exact mathematical modeling, standard floating-point types fail entirely due to binary representation limits, requiring `BigDecimal` to prevent precision loss.

* **Time and Memory Efficiency:**
  Competitive programming platforms impose strict **Time Limits (e.g., 1.0s)** and **Memory Limits (e.g., 256MB)**:
  * Primitive types (`int`, `long`) are stored on the **stack**, making operations lightning-fast and memory efficient.
  * Wrapper classes (`Integer`, `Long`) introduce object overhead and garbage collection delays, which can lead to **Time Limit Exceeded (TLE)** errors when processing millions of inputs.
  * Choosing smaller types like `byte` or `short` for large arrays reduces memory consumption when working within tight limits.

* **Bitwise Operations & Optimization:**
  Low-level mathematical optimizations—like checking if a number is even/odd, subset generation, or fast exponentiation—rely heavily on bit manipulation (`&`, `|`, `^`, `<<`, `>>`). Understanding integer bit-widths is essential for bitmasking algorithms.

---

### Reference Diagram
<img src="./images/JavaDataTypes.png" alt="Java Data Types Summary Diagram" width="900"/>

</details>
