## Data Types, Conditional stmts, Operators and Loops 
Data types are important because they determine what kind of data you can store, how much memory it uses, and what range of values it can handle.
For competitive coding, choosing the correct data type helps you:
* ⚡ Avoid overflow — e.g., use long for very large numbers.
* 💾 Manage memory efficiently — important for large arrays.
* 🎯 Get correct results — especially in integer division and arithmetic.
* 🧩 Match the problem constraints — choose based on the maximum possible input/value.

Example: If a problem says n ≤ 10^9, int may be enough, but calculations like n × n can reach 10^18, so long is safer.
- **Rule**: In competitive coding, always check the constraints before choosing a data type.
<details>
  <summary><b>▶ Click to view more</b></summary>
  <br>
  <img src="./images/JavaDataTypes.png" alt="Java Data Types Diagram" width="900"/>
</details>

---

<details>
<summary><h2>▶ Typecasting & Data Conversions</h2></summary>

In Java, **Typecasting** is the process of converting a value from one data type to another. Mastering both **Implicit (Widening)** and **Explicit (Narrowing)** conversions is essential for mathematical accuracy, preventing hidden logic bugs, and avoiding runtime errors.

### Why Data Conversions Matter in Competitive Coding & Math

* **Preventing Loss of Precision in Integer Division:**
  In Java, dividing two integers always yields an integer (e.g., `5 / 2` evaluates to `2`, not `2.5`). In competitive programming math problems (like computing averages, probabilities, or geometric coordinates), failing to cast at least one operand to `double` (e.g., `(double) 5 / 2`) causes truncation errors that fail exact test cases.

* **Avoiding Intermediate Overflow During Arithmetic:**
  When multiplying two large `int` values, the result is calculated as an `int` *before* being assigned to a destination variable. If the product exceeds $2 \times 10^9$, it silently overflows into a negative value—even if the receiving variable is declared as `long`. 
  * **Incorrect:** `long total = a * b;` *(overflow occurs during multiplication)*
  * **Correct:** `long total = (long) a * b;` *(forces intermediate computation in 64-bit precision)*

* **Safe Downcasting & Range Truncation:**
  Explicitly casting a larger type to a smaller type (e.g., `long` to `int` or `int` to `byte`) clips the high-order bits via **modulo arithmetic** ($2^{\text{bits}}$). While useful in low-level hashing algorithms or bitwise optimizations, unintended narrowing can lead to negative or unpredictable numbers.

---

<details>
  <summary><b>▶ Click to view more</b></summary>
  <br>
  <img src="./images/typecasting.png" alt="Java Data Types Diagram" width="900"/>
</details>

</details>
