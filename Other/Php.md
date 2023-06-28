# Learn PHP with [w3schools](w3schools.com)

- PHP files can contain text, HTML, CSS, JavaScript, and PHP code
- PHP code is executed on the server, and the result is returned to the browser as plain HTML
- PHP files have extension "`.php`"

## What Can PHP Do?

- PHP can generate dynamic page content
- PHP can create, open, read, write, delete, and close files on the server
- PHP can collect form data
- PHP can send and receive cookies
- PHP can add, delete, modify data in your database
- PHP can be used to control user-access
- PHP can encrypt data

With PHP you are not limited to output HTML. You can output images or PDF files. You can also output any text, such as XHTML and XML.

## PHP Syntax

A PHP script starts with `<?php` and ends with `?>`:

```php
<?php
// PHP code goes here
?>
```

- `echo` - output the text on a web page. `echo` has no return value while `print` has a return value of 1 so it can be used in expressions. `echo` can take multiple parameters (although such usage is rare) while `print` can take one argument. `echo` is marginally faster than `print`.
- In PHP 7, type declarations were added. This gives an option to specify the data type expected when declaring a function, and by enabling the strict requirement, it will throw a "Fatal Error" on a type mismatch.
- Commenting - `//` & `#` makes a single-line comment, starting with `/*` and end with `*/` makes This is a multiple-lines comment block. You can also use comments to leave out parts of a code line like bellow:

```php
$x = 5 /* + 15 */ + 5;
echo $x;
```

> **Note:** PHP statements end with a semicolon (`;`). all variable names are case-sensitive!

### Variables

Variables are "containers" for storing information. a variable starts with the `$` sign, followed by the name of the variable like `$txt = "Hello world!";`. variable is created the moment you first assign a value to it.

Rules for PHP variables:

- A variable starts with the `$` sign, followed by the name of the variable
- PHP automatically associates a data type to the variable, depending on its value.
- A variable name must start with a letter or the underscore character
- A variable name **cannot start with a number**
- A variable name can only contain alpha-numeric characters and underscores (A-z, 0-9, and \_ )
- Variable names are case-sensitive (`$age` and `$AGE` are two different variables).
- Remember that PHP variable names are case-sensitive!

PHP has three different variable scopes:

- local - A variable declared within a function has a LOCAL SCOPE and can only be accessed within that function.

```php
<?php
function myTest()
{
  $x = 5; // local scope
  echo "<p>Variable x inside function is: $x</p>";
}
myTest();

// using x outside the function will generate an error
echo "<p>Variable x outside function is: $x</p>";
?>
```

- global - A variable declared **outside** a function has a GLOBAL SCOPE and can only be accessed outside a function

```php
$x = 5; // global scope
function myTest()
{
  // using x inside this function will generate an error
  echo "<p>Variable x inside function is: $x</p>";
}
myTest();

echo "<p>Variable x outside function is: $x</p>"; //will give us result
```

> The global keyword is used to access a global variable from within a function. To do this, use the global keyword before the variables (inside the function):

```php
function myTest()
{
  global $x, $y;
  $y = $x + $y;
}

myTest();
echo $y; // outputs 15
```

- static - Normally, when a function is completed/executed, all of its variables are deleted. However, sometimes we want a local variable NOT to be deleted. We need it for a further job.

```php
<?php
function myTest()
{
  static $x = 0;
  echo $x;
  $x++;
}

myTest();
myTest();
myTest();
?>
```

### PHP Data Types

- String
- Integer
- Float (floating point numbers - also called double)
- Boolean
- Array `$cars = array("Volvo","BMW","Toyota");`
- Object
- NULL (a variable that has no value assigned to it)

#### PHP String Functions

- `strlen()` function returns the length of a string.
- `str_word_count()` function counts the number of words in a string.
- `strrev()` function reverses a string.
- `strpos()` function searches for a specific text within a string. If a match is found, the function returns the character position of the first match. (with bool `true` or else)
- `str_replace()` function replaces some characters with some other characters in a string.

> Complete [PHP String Reference](https://www.w3schools.com/php/php_ref_string.asp).

#### PHP Numbers

- `is_int()` - checks if the type of a variable is integer.
- `is_float()` - checks if the type of a variable is float.
- `is_finite(), is_infinite()`- checks if a numeric value is finite or infinite.
- `is_nan()` - checks if a value is not a number.
