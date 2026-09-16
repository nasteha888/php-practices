# 📌 Chapter 1: Introduction to PHP & MySQL

### 1. Course Objectives & Technologies
* **Goal:** Learn how to build dynamic websites and web applications.
* **Technologies Used:** HTML, CSS, JavaScript, jQuery, PHP, MySQL, and the Laravel Framework.
* **Reference Book:** *Learning PHP, MySQL & JavaScript with jQuery, CSS & HTML5 (6th Edition)* by Robin Nixon.

### 2. How the Web Works (HTTP Request/Response Procedure)
* **Client (Browser):** Sends an HTTP Request to the web server.
* **Web Server:** Processes the request and returns an HTTP Response (Web Page).
* **HTTP & HTML:** HTTP is the protocol used for client-server communication. HTML defines the structure of web pages.

### 3. What is PHP & What Can It Do?
* **Definition:** PHP (Hypertext Preprocessor) is a server-side scripting language used to create dynamic web applications.
* **PHP Features:**
  * Free and open-source software.
  * Can be seamlessly embedded directly into HTML.
  * Supports both Procedural and Object-Oriented Programming (OOP) paradigms.
  * Connects with various database management systems like MySQL, Oracle, and SQL Server.
* **Famous Platforms Built with PHP:** Facebook, Wikipedia, WordPress, Yahoo, Tumblr, and Mailchimp.

### 4. Setting Up the Development Environment
* **Required Software:**
  * **Local Server:** XAMPP (Apache, MySQL, PHP, Perl).
  * **Code Editor:** Visual Studio Code.
  * **Browser:** Google Chrome, Microsoft Edge, or Mozilla Firefox.
* **Document Root:** PHP files must be placed inside the `htdocs` directory (e.g., `C:/xampp/htdocs`).
* **Testing Local Server:** Open your browser and type `http://localhost` or `http://127.0.0.1` in the address bar.

---

# 📌 Chapter 2: PHP Fundamentals & Control Structures

### 1. PHP Syntax, Comments & Output Essentials
* PHP files end with the `.php` file extension.
* PHP code starts with `<?php` and ends with `?>`. Every statement must terminate with a semicolon `;`.
* **Comments:** `//` or `#` for single-line comments, and `/* ... */` for multi-line comments.
* **`echo` vs `print`:** `echo` is slightly faster and can accept multiple parameters, while `print` returns a value of 1.

#### 💻 Example 1: Basic Output, Variables & String Concatenation (`.`)

```php
<?php
// Variable Declarations
$name = "Nasteexo";
$course = "Web Application Development";
$year = 3;

// Double Quotes (Variables are parsed inside double quotes)
echo "Welcome to $course, student$name.<br>";

// Using the Concatenation Operator (.)
echo "She is a student currently in year " . $year . " at the university.";
?>
2. Conditional Statements
Used to execute specific blocks of code based on conditions.

💻 Example 2 (A): if...elseif...else Statement
PHP
<?php
$score = 85;

if ($score >= 90) {
    echo "Grade: A";
} elseif ($score >= 75) {     echo "Grade: B"; } elseif ($score >= 50) {
    echo "Grade: C";
} else {
    echo "Grade: Fail";
}
?>
💻 Example 2 (B): switch Statement
PHP
<?php
$day = "Saturday";

switch ($day) {
    case "Saturday":
        echo "Beginning of the week!";
        break;
    case "Thursday":
        echo "End of the week!";
        break;
    default:
        echo "Regular weekday.";
        break;
}
?>
3. Loop Control Structures
Loops repeat a block of code as long as a specified condition is met.

💻 Example 3 (A): for Loop (Counting)
PHP
<?php
// Displays numbers from 1 to 5
for ($i = 1; $i <= 5; $i++) {
    echo "Number: $i <br>";
}
?>
💻 Example 3 (B): while Loop
PHP
<?php
$x = 1;

while ($x <= 3) {
    echo "Count value: $x <br>";
    $x++;
}
?>
💻 Example 3 (C): foreach Loop (Array Iteration)
PHP
<?php
$technologies = array("HTML", "CSS", "JavaScript", "PHP", "MySQL");

foreach ($technologies as$tech) {
    echo "Technology: $tech <br>";
}
?>
🚀 Advanced Concepts: Arrays, Forms, Functions & Database Integration
1. Arrays in PHP
PHP supports 3 main types of arrays:

Indexed Array: Arrays with numeric index positions starting at 0.

Associative Array: Arrays with named key-value pairs.

Multidimensional Array: Arrays containing one or more arrays inside them.

💻 Example 4: Indexed & Associative Arrays
PHP
<?php
// 1. Indexed Array
$languages = array("HTML", "CSS", "JavaScript", "PHP", "MySQL");
echo "First language: " . $languages[0] . "<br><br>";

// 2. Associative Array
$student = array("Name" => "Nasteexo", "Age" => 21, "Role" => "Developer");
echo "Student Name: " . $student["Name"];
?>
2. Form Handling ($_GET vs $_POST)
$_GET: Data is appended to the URL string (not suitable for sensitive data like passwords).

$_POST: Data is sent invisibly inside the HTTP request body (ideal for secure data submission).

💻 Example 5: HTML Form & PHP Processor
HTML Form (index.html):

HTML
<form action="process.php" method="POST">
    <label>User Name:</label>
    <input type="text" name="username" required>
    <input type="submit" value="Submit">
</form>
PHP Handling Script (process.php):

PHP
<?php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $user =$_POST['username'];
    echo "Welcome, " . htmlspecialchars($user);
}
?>
3. Custom Functions
Functions organize code into reusable blocks to maintain clean, modular programs.

💻 Example 6: Custom Function with Parameters
PHP
<?php
function calculateSum($num1, $num2) {$total = $num1 +$num2;
    return $total;
}

// Function Call
$result = calculateSum(15, 25);
echo "The total sum is: $result";
?>
4. Database Connection (PHP & MySQLi)
Standard code used to establish a connection between PHP and a MySQL server.

💻 Example 7: MySQL Database Connection
PHP
<?php
$servername = "localhost";
$username = "root";
$password = "";
$dbname = "my_database";

// Create Connection
$conn = new mysqli($servername,$username, $password,$dbname);

// Check Connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}

echo "Database connected successfully!";
?>