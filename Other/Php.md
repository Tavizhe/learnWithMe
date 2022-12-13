# Learn PHP with [w3schools.com](https://www.w3schools.com/php/default.asp)

PHP is a =server= scripting language, and a powerful tool for making dynamic and interactive Web pages.

PHP is a widely-used, free, and efficient alternative to competitors such as Microsoft's ASP.

PHP files can contain text, HTML, CSS, JavaScript, and PHP code and PHP code is executed on the server, and the result is returned to the browser as plain HTML and PHP files have extension `.php`.

## What Can PHP Do?

- PHP can generate dynamic page content
- PHP can create, open, read, write, delete, and close files on the server
- PHP can collect form data
- PHP can send and receive cookies
- PHP can add, delete, modify data in your database
- PHP can be used to control user-access
- PHP can encrypt data

You can also output images, PDF files, and even Flash movies. You can also output any text, such as XHTML and XML.

## What Do I Need?

To start using PHP, you can:

- Find a web host with PHP and MySQL support
- Install a web server on your own PC, and then install PHP and MySQL

---

## how to write in php?

```php
<?php
code here;
?>
```

---

if you want to write php in html always put `.php` at end of file.

## dynamic data

```php
$title = "hello world";
<h1> <?php echo $title; ?> </h1>
// we can use # or // and Multi-line comments are placed between /* and */.
```

---

## variables

Variable names can contain numbers, letters, and underscores `(\_)`. A sigil `($)` must always precede a variable name. They cannot start with a number and they cannot have spaces or any special characters.
PHP supports ten primitive types.

> In PHP, the reference assignment operator (=&) is used to create a new variable as an alias to an existing spot in memory.
> In other words, the reference assignment operator (=&) creates two variable names which point to the same value. So, changes to one variable will affect the other, without having to copy the existing data.

1. bool - true or false.
2. int - An int is a number of the set ℤ = {..., -2, -1, 0, 1, 2, ...}.
3. float (floating-point number, aka double)
4. string - any kind of text
5. array
6. object - with classes
7. callable - Callbacks can be denoted by the callable type declaration.
8. iterable - function foo(iterable $iterable) {foreach ($iterable as $value)
9. resource - holding a reference to an external resource.
10. NULL

> Note: To check the type and value of an expression, use the var_dump() function. after putting `$` we name the variable. we can use `.` to put together some words.
> To get a human-readable representation of a type for debugging, use the gettype() function.
> We can create an alias for a variable, instead of just a copy, using the reference assignment operator `(=&)`.
> The concatenating assignment operator `(.=)` is a shorthand notation for reassigning a string variable to its current value appended with another string value.

```php
  echo "1. Teach PHP";
  echo "\n2. [Another thing to do]";
  echo "\n3. Learn to have \"fun\"";
$name = 'Edwin';
$number = 100;
$Number_List = 100.5;

echo $name . " " . $Number_List;
```

constants values can't be changed.
`define("name",1000);`

### String Escape Sequences

## sometimes special characters must be escaped in order to include them in a string. Escape sequences start with a backslash character `(\)`.

## math

doing math is simple as any other language.

```php
// + - / % *
echo 2 ** 4;
// Output: 16
```

we cannot simply ad `</br>` in php we got to do it like this:
`echo "<br>";`

---

## Arrays

just as JavaScript we do us arrays too. The built-in `print_r()` function outputs arrays in a human readable format.

> The built-in PHP `count()` function takes an array as its argument and returns the number of elements in that array.
> The PHP built-in `array_pop()` function takes an array as its argument. It permanently removes the last element of an array and returns the removed element.
> The PHP built-in `array_unshift()` function takes an array as its first argument. The arguments that follow are elements to be added to the array.
> The built-in implode() function makes a string from an array. The function takes two arguments: a string to place between each element of an array and the array to be joined together.`$pieces = [1, "2", "three", 4.0]; $glue = " and a "; echo implode($glue, $pieces); // 1 and a 2 and a three and a 4`
> The PHP built-in `array_shift()` function takes an array as its argument, permanently removes the first element from the array, and returns the removed element.

```php
$numberList = array(267,8765,345,'5345', 345, '<h1>Hello</h1>');
//or
$string_array = ["first element", "second element"];
$string_array[] = "third element"; // adds to it
echo $numberList[5];
$some_numbers = ["1", 2, 3.0];
echo array_push($some_numbers, "four"); //Returns: 4
// $some_numbers is now: ["1", 2, 3.0, "four"]
```

### Associative Array

```php
$names = array("first_name" => 'Edwin', "Last_Name" => 'ali' );
echo $names['first_name'] . " " . $names['Last_Name'];
```

---

## Statements

if statement

```php
if(3 > 10){
echo "three is less than ten";
} elseif( 4 > 5) {
echo "of course four is less than five";
}
else {
echo "it is not";
}
```

switch statement

```php
switch($number){
    case 34:
    echo "it is 34";
    break;
    case 37:
    echo "is it 34";
    break;
    case 35:
    echo "is it 34";
     break;
    case 24:
    echo "is it 24";
      break;
    default :
     echo "we could not find anything";
    break;
}
```

while loop statement

```php
$counter = 0;
while($counter <= 10 ){
    echo $counter;
    $counter++;
}
```

for statement

```php
for($counter = 0; $counter < 10; $counter++){
    echo $counter . "<br>" ;
}
```

foreach statement

```php
$numbers = array(345,397,676,385,2657,5784);
foreach($numbers as $number){
echo $number . "<br>";
}
```

---

## Functions

```php
function say_Something(){
   echo "Hello Student, do you like the class? yes? okay great";
}
say_Something();
```

passing parameters in functions

```php
function addNumbers($number1, $number2){
$sum = $number1 + $number2;
echo $sum;
}
addNumbers(345,3462);
```

returning a value in functions

```php
function addNumbers($number1, $number2){
$sum = $number1 + $number2;
return $sum;
}
$result = addNumbers(34,64);
echo $result;
```
