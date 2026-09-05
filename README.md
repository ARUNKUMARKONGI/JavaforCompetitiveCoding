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
