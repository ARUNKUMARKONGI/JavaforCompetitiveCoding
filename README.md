<details>
<summary><h2 style="display:inline;">▶ Data Types, Conditional Stmts, Operators and Loops</h2></summary>
<br>

<p>Data types are important because they determine what kind of data you can store, how much memory it uses, and what range of values it can handle.</p>

<p>For competitive coding, choosing the correct data type helps you:</p>
<ul>
  <li>⚡ <strong>Avoid overflow</strong> — e.g., use <code>long</code> for very large numbers.</li>
  <li>💾 <strong>Manage memory efficiently</strong> — important for large arrays.</li>
  <li>🎯 <strong>Get correct results</strong> — especially in integer division and arithmetic.</li>
  <li>🧩 <strong>Match problem constraints</strong> — choose based on the maximum possible input value.</li>
</ul>

<p><strong>Example:</strong> If a problem says <em>n ≤ 10⁹</em>, <code>int</code> may be enough, but calculations like <em>n × n</em> can reach <em>10¹⁸</em>, so <code>long</code> is safer.</p>

<p>👉 <strong>Rule:</strong> In competitive coding, always check constraints before choosing a data type.</p>

<br>
<h3>Reference Diagram <em>(Click image to view/download full resolution)</em></h3>

<a href="./images/JavaDataTypes.png" target="_blank">
  <img src="./images/JavaDataTypes.png" alt="Java Data Types Diagram" width="900"/>
</a>

</details>

<hr>

<details>
<summary><h2 style="display:inline;">▶ Typecasting & Data Conversions</h2></summary>
<br>

<p>In Java, <strong>Typecasting</strong> is the process of converting a value from one data type to another. Mastering both <strong>Implicit (Widening)</strong> and <strong>Explicit (Narrowing)</strong> conversions is essential for mathematical accuracy, preventing hidden logic bugs, and avoiding runtime errors.</p>

<h3>Why Data Conversions Matter in Competitive Coding & Math</h3>

<ul>
  <li>
    <strong>Preventing Loss of Precision in Integer Division:</strong><br>
    In Java, dividing two integers always yields an integer (e.g., <code>5 / 2</code> evaluates to <code>2</code>, not <code>2.5</code>). In competitive programming math problems (like computing averages or probabilities), failing to cast at least one operand to <code>double</code> (e.g., <code>(double) 5 / 2</code>) causes truncation errors.
  </li>
  <br>
  <li>
    <strong>Avoiding Intermediate Overflow During Arithmetic:</strong><br>
    When multiplying two large <code>int</code> values, the result is calculated as an <code>int</code> <em>before</em> being assigned to a destination variable. If the product exceeds 2 × 10⁹, it silently overflows into a negative value—even if assigned to a <code>long</code>.
    <ul>
      <li>❌ <strong>Incorrect:</strong> <code>long total = a * b;</code> <em>(overflow occurs during multiplication)</em></li>
      <li>✅ <strong>Correct:</strong> <code>long total = (long) a * b;</code> <em>(forces 64-bit precision)</em></li>
    </ul>
  </li>
  <br>
  <li>
    <strong>Safe Downcasting & Range Truncation:</strong><br>
    Explicitly casting a larger type to a smaller type (e.g., <code>long</code> to <code>int</code>) clips high-order bits via modulo arithmetic. While useful in bitwise optimizations, unintended narrowing leads to unexpected negative numbers.
  </li>
</ul>

<br>
<h3>Reference Diagram <em>(Click image to view/download full resolution)</em></h3>

<a href="./images/typecasting.png" target="_blank">
  <img src="./images/typecasting.png" alt="Java Typecasting Diagram" width="900"/>
</a>

</details>

---

<details>
<summary><h2 style="display:inline;">▶ Java Important Library Functions (Math, Strings, Arrays & Collections)</h2></summary>
<br>

<p>In competitive coding and software development, re-inventing basic utility functions wastes time and often introduces subtle bugs. Java provides highly optimized built-in methods across various library classes designed to handle common mathematical, text-processing, and array-manipulation tasks efficiently.</p>

<h3>1. Math Library (<code>java.lang.Math</code>)</h3>
<p>All methods in <code>Math</code> are static and operate in constant time <span style="font-family: monospace;">O(1)</span>.</p>

<ul>
  <li><code>Math.max(a, b)</code> / <code>Math.min(a, b)</code> — Returns the maximum or minimum of two numbers.</li>
  <li><code>Math.abs(a)</code> — Returns the absolute value (useful for distance and difference calculations).</li>
  <li><code>Math.pow(base, exp)</code> — Computes <em>base<sup>exp</sup></em> (returns a <code>double</code>; cast to <code>long</code> to avoid precision issues).</li>
  <li><code>Math.sqrt(n)</code> — Calculates the square root (returns a <code>double</code>; ideal for prime-checking loops up to <em>√n</em>).</li>
  <li><code>Math.gcd(a, b)</code> — <em>Note:</em> Java doesn't have <code>Math.gcd()</code> natively; use <code>BigInteger.valueOf(a).gcd(BigInteger.valueOf(b)).longValue()</code> for quick GCD calculation.</li>
  <li><code>Math.ceil(x)</code> / <code>Math.floor(x)</code> / <code>Math.round(x)</code> — Rounds floating-point values up, down, or to the nearest integer.</li>
</ul>

<p>💡 <strong>Pro Tip for Integer Ceiling:</strong> To compute <code>ceil(a / b)</code> using integer arithmetic without floating-point errors, use: <code>(a + b - 1) / b</code>.</p>

<hr>

<h3>2. String & Character Handling</h3>

<p><strong>String Class (<code>java.lang.String</code>) — Immutable:</strong></p>
<ul>
  <li><code>str.length()</code> — Returns string length.</li>
  <li><code>str.charAt(i)</code> — Returns the character at index <code>i</code> <span style="font-family: monospace;">O(1)</span>.</li>
  <li><code>str.substring(start, end)</code> — Extracts substring from <code>start</code> to <code>end - 1</code>.</li>
  <li><code>str.indexOf("sub")</code> — Finds the first occurrence of a substring (returns <code>-1</code> if not found).</li>
  <li><code>str.toCharArray()</code> — Converts string into a character array (<code>char[]</code>) for easy modification.</li>
  <li><code>str.trim()</code> / <code>str.toLowerCase()</code> / <code>str.toUpperCase()</code> — String cleanup and normalization.</li>
</ul>

<p><strong>StringBuilder Class (<code>java.lang.StringBuilder</code>) — Mutable:</strong></p>
<p>Standard String concatenation (<code>+</code>) inside a loop creates thousands of temporary objects, leading to <span style="font-family: monospace;">O(N²)</span> time complexity and <strong>Time Limit Exceeded (TLE)</strong> errors. Always use <code>StringBuilder</code> for string construction inside loops:</p>

<ul>
  <li><code>sb.append(val)</code> — Fast <span style="font-family: monospace;">O(1)</span> string construction.</li>
  <li><code>sb.reverse()</code> — Reverses the sequence in-place in <span style="font-family: monospace;">O(N)</span> time (great for palindrome checks).</li>
  <li><code>sb.toString()</code> — Converts the builder back to a standard String.</li>
</ul>

<p><strong>Character Class Utility Methods (<code>java.lang.Character</code>):</strong></p>
<ul>
  <li><code>Character.isDigit(ch)</code> — Checks if character is between <code>'0'</code> and <code>'9'</code>.</li>
  <li><code>Character.isLetter(ch)</code> / <code>Character.isLetterOrDigit(ch)</code> — Validates alphanumeric characters.</li>
  <li><code>Character.toLowerCase(ch)</code> / <code>Character.toUpperCase(ch)</code> — Case conversions.</li>
  <li><code>ch - '0'</code> — Fast trick to convert character digit to actual integer value (e.g., <code>'7' - '0' = 7</code>).</li>
</ul>

<hr>

<h3>3. Arrays & Collections Utility Class</h3>

<p><strong>Arrays Class (<code>java.util.Arrays</code>):</strong></p>
<ul>
  <li><code>Arrays.sort(arr)</code> — Sorts primitive arrays in <span style="font-family: monospace;">O(N log N)</span> using Dual-Pivot Quicksort.</li>
  <li><code>Arrays.fill(arr, val)</code> — Fills an entire array with a specific default value (useful for DP initialization).</li>
  <li><code>Arrays.binarySearch(arr, key)</code> — Searches a <em>pre-sorted</em> array in <span style="font-family: monospace;">O(log N)</span> time.</li>
  <li><code>Arrays.equals(arr1, arr2)</code> — Checks if two arrays contain identical elements in the same order.</li>
</ul>

<p><strong>Collections Class (<code>java.util.Collections</code>):</strong></p>
<ul>
  <li><code>Collections.sort(list)</code> / <code>Collections.sort(list, Collections.reverseOrder())</code> — Sorts ArrayLists in ascending or descending order.</li>
  <li><code>Collections.max(list)</code> / <code>Collections.min(list)</code> — Finds max or min element in a collection.</li>
  <li><code>Collections.reverse(list)</code> — Reverses an ArrayList in-place.</li>
  <li><code>Collections.frequency(list, val)</code> — Counts occurrences of an element in a collection.</li>
</ul>

<br>
<h3>Reference Diagram <em>(Click image to view/download full resolution)</em></h3>

<a href="./images/java-libraries.png" target="_blank">
  <img src="./images/java-libraries.png" alt="Java Built-in Libraries and Methods Cheat Sheet" width="900"/>
</a>

</details>
