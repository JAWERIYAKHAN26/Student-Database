<h1>🎓 Student Database – MySQL Project</h1>

<p>
This project contains a <b>MySQL database</b> for managing students, classes, teachers, and marks.  
It also includes <b>20 SQL queries</b> to practice important concepts like 
<code>JOIN</code>, <code>GROUP BY</code>, <code>HAVING</code>, <code>ORDER BY</code>, and <code>SUBQUERIES</code>.
</p>

<hr>

<h2>📂 Project Structure</h2>
<ul>
  <li><b>Student_db.sql</b> – Contains:
    <ol>
      <li>Database creation</li>
      <li>Tables creation (<code>Students</code>, <code>Classes</code>, <code>Teachers</code>, <code>Marks</code>)</li>
      <li>Sample data insertion</li>
      <li>20 SQL queries with comments</li>
    </ol>
  </li>
</ul>

<hr>

<h2>🗄️ Database Schema</h2>

<h3>1. Students</h3>
<table>
  <tr><th>Column</th><th>Type</th><th>Description</th></tr>
  <tr><td>student_id</td><td>INT (PK)</td><td>Unique student ID</td></tr>
  <tr><td>name</td><td>VARCHAR(50)</td><td>Student name</td></tr>
  <tr><td>age</td><td>INT</td><td>Student age</td></tr>
  <tr><td>gender</td><td>VARCHAR(10)</td><td>Male/Female</td></tr>
  <tr><td>class_id</td><td>INT</td><td>References <code>Classes</code></td></tr>
</table>

<h3>2. Classes</h3>
<table>
  <tr><th>Column</th><th>Type</th><th>Description</th></tr>
  <tr><td>class_id</td><td>INT (PK)</td><td>Unique class ID</td></tr>
  <tr><td>class_name</td><td>VARCHAR(50)</td><td>Class name (e.g. 10th)</td></tr>
  <tr><td>teacher_id</td><td>INT</td><td>References <code>Teachers</code></td></tr>
</table>

<h3>3. Teachers</h3>
<table>
  <tr><th>Column</th><th>Type</th><th>Description</th></tr>
  <tr><td>teacher_id</td><td>INT (PK)</td><td>Unique teacher ID</td></tr>
  <tr><td>name</td><td>VARCHAR(50)</td><td>Teacher name</td></tr>
  <tr><td>subject</td><td>VARCHAR(50)</td><td>Subject taught</td></tr>
</table>

<h3>4. Marks</h3>
<table>
  <tr><th>Column</th><th>Type</th><th>Description</th></tr>
  <tr><td>mark_id</td><td>INT (PK)</td><td>Unique mark record ID</td></tr>
  <tr><td>student_id</td><td>INT</td><td>References <code>Students</code></td></tr>
  <tr><td>subject</td><td>VARCHAR(50)</td><td>Subject name</td></tr>
  <tr><td>marks</td><td>INT</td><td>Marks scored</td></tr>
</table>

<hr>

<h2>📊 Example Queries</h2>

<b>1️⃣ Get all student names</b>
<pre>
SELECT name FROM Students;
</pre>

<b>2️⃣ List students with their class names (JOIN example)</b>
<pre>
SELECT Students.name, Classes.class_name
FROM Students
JOIN Classes ON Students.class_id = Classes.class_id;
</pre>

<b>3️⃣ Show total male and female students per class (GROUP BY + CASE)</b>
<pre>
SELECT 
  c.class_name,
  SUM(CASE WHEN s.gender = 'Male' THEN 1 ELSE 0 END) AS male_students,
  SUM(CASE WHEN s.gender = 'Female' THEN 1 ELSE 0 END) AS female_students
FROM Students s
JOIN Classes c ON s.class_id = c.class_id
GROUP BY c.class_name;
</pre>

<hr>

<h2>🏃 How to Run</h2>
<ol>
  <li>Open <b>MySQL Workbench</b></li>
  <li>Copy or <b>import Student_db.sql</b></li>
  <li>Run the script (F5)</li>
  <li>Execute queries to see results</li>
</ol>

<hr>

<h2>📌 Concepts Covered</h2>
<ul>
  <li><code>CREATE DATABASE</code> & <code>CREATE TABLE</code></li>
  <li><code>INSERT INTO</code> statements</li>
  <li><code>INNER JOIN</code> and multi-table <code>JOIN</code></li>
  <li><code>GROUP BY</code> and <code>HAVING</code></li>
  <li><code>ORDER BY</code> and <code>LIMIT</code></li>
  <li>Subqueries & Aggregate Functions (<code>AVG</code>, <code>MAX</code>, <code>SUM</code>)</li>
  <li>Temporary Tables (<code>CREATE TEMPORARY TABLE</code>)</li>
</ul>

<hr>

<p>⭐ Feel free to <b>fork</b> and practice SQL with this dataset!</p>
