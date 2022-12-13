# javaScript Learning 2022

> Learning By JohnSmilga

## Part 1: javaScript Basics

in order to do some debugging we are going tro need these codes:
we can always do simple commenting too.

```JavaScript
document.write('hello world');
alert('hello world');
console.log('hello world');
console.log(typeof text); //shows the type of returned value
@ts-check helps to debug errors as intellisense with //
```

---

### Variables:

with ==let== you can re-assign it as many times az you want.
in order to using ==const== (CONSTANT) - you can't re-assign it later.
you need to remember that numbers will be ==blue== in console but string of anything like numbers are ==black==.
`let value1 = "hello", const value2 = 1401;`
we can always just announce the variable without giving it a value, it will help JavaScript to render codes better.
remember that variables can contain digits, letters, underscore, $
and must start with letter, $ or \_. it can't start with numbers.
variables are ==case sensitive== and ==camelCase== is the way to type in JavaScript.
using ==var== always make problems in codes cause it will render codes in difference way so always use let and const to be up to date as new es6 and higher.

> var have different way in javaScript playground, check below codes:

```JavaScript
let total = 1000;
let test = true;
if (test) {
  // local scope
  let total = 'oranges and onions';
  let value = 'some random value';
  console.log('hello there');
}
 console.log(total);
 // console will show oranges and onions. but if we use let, scopes will work the normal way.
```

```JavaScript
console.log(amount);
//will not give you error bt the answer in undefined
var amount = 10;
```

---

#### combining values together:

```JavaScript
// in order to do this we use +
const website = "youtube";
const url = "https://www." + website + ".com";
```

#### Quotation Marks:

most of times we start with " in order to use ' inside of ". later we
use ` to have template literals.

### Playing Around String Methods:

```JavaScript
const person = 'Peter Smith';
const employee = '23456-EMP-PETER-SMITH';
const manager = '23456-MAN-JOHN-DOE';
//startsWith checks the start with 1 parameter, with 2 it will change as starting position.
console.log(person.startsWith('Pet', 6));
//endsWith same thing here too but if we add second argument it will check end of last of that index.
console.log(manager.endsWith('MAN', 9));
// includes
console.log(manager.includes('MAN'));

const multiplyPeople = (person, amount) => person.repeat(amount);
// repeat the same string multiple times. from person and how many times as amount
const people = multiplyPeople(person, 10);
```

---

### Arrays:

arrays are index based for knowing where we are.

```JavaScript
const friends = ['john', 'peter', 'bob', 'suse', 45, undefined, null];
const values = [firstValue, secondValue, add(5, 6)];
```

#### Arrays Part 2:

instead of using index to find what's the value of array is we can go with below example:

```JavaScript
const friends = ['john', 'peter', 'bob', 'anna', 'kelly'];
const [john, , enemy, bob, susan] = friends;
console.log(john, enemy, bob, susan);
```

> destructive Swap Variables is faster way to swap values in array: `[second, first]= [first, second];`
> Spread Operator `...arrayName` doesn't change original array and Splits into single items from given text and copy them individually.

```JavaScript
const udemy = 'udemy';
const letters = [...udemy];
console.log(letters);
```

> we can use `Array.of` to create a new Array instance from a variable number of arguments. example `const friends = Array.of('john', 2, true);` > `Array.from` - returns Array Object from any object with a length property or an iterable object. (can turn array like functions or objects to array)

```JavaScript
function countTotal() {
  // console.log(arguments);
  let total = Array.from(arguments).reduce(
    (total, currNum) => (total += currNum),
    0
  );
  console.log(total);
}
countTotal(67, 89, 54, 100);
// Array.from in nodeList
const p = document.querySelectorAll('p');
const result = document.getElementById('result');
const second = document.getElementById('second');

let newText = Array.from(p);
newText = newText.map(item => `<span>${item.textContent}</span>`).join(' ');
result.innerHTML = newText;
// or in professionally way
const text = Array.from(document.querySelectorAll('p'), item => {
  return `<span>${item.textContent}</span>`;
}).join(' ');
second.innerHTML = text;
```

> `Array.find` gets specific item in our array.
> `Array.findIndex` get's index of the item.
> `Array.every` every item in other array match our array.
> `Array.some` at least one item matches our array.

```JavaScript
const people=[
  {id:1, name:"john"},
  {id:2, name:"peter"},
  {id:3, name:"anna"},
  ];
const grades = ["A","B", "A" , "B"< "C"];
const goodGrades = ["A","B","A","B"];
//Array.find
const anna = people.find(person => person.name === "anna");
//Array.findIndex
const person = people.findIndex(item => item.id === 3);
//Array.every
const allGoodGrades = grades.every(grade => grade !== "C");
// Array.some
const oneBadGrades = grades.some(grade => grade === "C");
```

---

### Functions:

```JavaScript
// simple way to show func:
function addValues(num1, num2) {
  return num1 + num2;
}
// another way that shows object in parameters and invoke them inside
function fullName({ firstName, lastName }) {
  const fullName = `${firstName} ${lastName}`;
  return fullName.toUpperCase();
}
console.log(fullName({ lastName: 'jordan', firstName: 'peter' }));
// curly brackets {} here let us choose the input order of objects
// and way of function expiration
 greeting() {
    console.log("Hello my name is JOHN");
    //OR greeting: function () {console.log("Hello my name is JOHN");},
  }
function calculateTotal(arr) {
    // as you can see we have use arr to represent it doesn't matter
    // what yo put in it can be array or obj or simple value
  let total = 0;
  for (let i = 0; i < arr.length; i++) {
    total += arr[i];
  }
  if (total > 100) {
    console.log(`Whoa! You are spending way too much`);
    return total;
  }
  console.log(`You are good total is less than 100`);

  return total;
}
```

### Functions Part 2:

let's play around functions
usually it's important that what we use in functions and it's depended on this keyword.

> Spread Operator:

```JavaScript
const numbers = [23, 45, 66, 88, 2345];
console.log(Math.max(...numbers));

const sayHello = (name, lastName) => {
  console.log(`Hello ${name} ${lastName}`);
};
sayHello(...john);
```

> Function destructing:

```JavaScript
function printPerson({first, last, city}){}
//means that i'm getting a object that has these properties.
```

#### IIFE

IIFE means Immediately Invoked Function Expression. how to do it: (Simply add () around the function)
not only it happens immediately but it's good way at protecting the scope of your function and the variables within it.
`(function (arguments) {codes}) (invoke); `

```JavaScript
(function () {
  const num3 = 30;
  const num4 = 50;
  console.log(`the result is : ${num3 + num4}`);
})();
```

#### Arrow Function:

arrow function has no name so we always assign it to a variable

```JavaScript
// function sayHi() {
//   console.log("hello");
// }
// sayHi();
//will be
const hello = () => console.log("hello");
hello();
// with 1 parameter
const double = value => value * 2;
const num = double(4);
console.log(num);
// with 2 parameters
const multiply = (num1, num2) => {
  const result = num1 * num2;
  // more code here
  return result;
};
// return object
const object = () => ({ name: "bob", age: 25 });
const person = object();
console.log(person);
// arrow functions as callback functions
const numbers = [1, 2, 3, 4, 5, 6];
const big = numbers.filter(number => number > 2);
console.log(big);
const btn = document.querySelector(".btn");
btn.addEventListener("click", () => console.log("you clicked me"));
```

==hoisted has been bypassed because of confusing var functionality==.

#### Closure

closure gives you an access to an outer function's scope from an inner function. best thing about closure is that nobody can have access the balance in second example.

```JavaScript
function outer() {
  let privateVar = 'secret';
  function inner() {
    console.log(`hello there secret is : ${privateVar} `);
  }
  return inner;
  //because of returning function we can still have access to private out of our scope
}
outer()();
//outer() is func and with () we instantly invoked it
```

cool example:

```JavaScript
function newAccount(name, initialBalance) {
  let balance = initialBalance;
  function showBalance() {
    console.log(`Hey ${name}, your balance is ${balance}`);
  }
  function deposit(amount) {
    balance += amount;
    showBalance();
  }
  function withdraw(amount) {
    if (amount > balance) {
      console.log(`Hey, ${name}, sorry not enough funds`);
      return;
    }
    balance -= amount;
    showBalance();
  }
  return { showBalance: showBalance, deposit: deposit, withdraw: withdraw };
}
const john = newAccount('john', 1000);
john.showBalance();
john.deposit(400);
john.withdraw(400);
john.balance = 10000;
```

---

### Objects:

objects can have methods (functions) inside them so we 're going to need dot notation to use the method inside of object.

```JavaScript
const person = {
  name: "john",
  lastName: "peters",
  age: 25,
  education: false,
  married: true,
  siblings: ["anna", "susan", "peter"],
  greeting() {// should always use function expiration in objects
    console.log("Hello my name is JOHN");
  },
  greeting2: function () {console.log("Hello my name is JOHN");},
  'random-value': 'random',
};
console.log(person.name);
console.log(person.greetings); //usage of dot notations.
delete person.siblings;// delete property
console.log(person['random-value']); //usage of bracket notation.
```

### Rest Operator:

gathers/collects the items

```JavaScript
//arrays
const fruit = ['apple', 'orange', 'lemon', 'banana', 'pear'];
const [first, second, ...fruits] = fruit;
// ...fruits gives us the rest of items
//objects
const person = { name: 'john', lastName: 'smith', job: 'developer' };
const { job, ...rest } = person;
//functions
const testScores = [78, 90, 56, 43, 99, 65];

const getAverage = (name, ...scores) => {
  console.log(name);
  console.log(scores);
  let total = 0;
  for (const score of scores) {
    total += score;
  }
  console.log(`${name}'s average score is ${total / scores.length}`);
};

getAverage(person.name, 78, 90, 56, 43);
getAverage(person.name, ...testScores);
```

### Objects Part 2:

we are do nesting in objects that means we can make object in another object.

> if we have problem that we have same variable name in our project as in object we can use: `const{first: firstName};` to change name of our variable. or object in object : `const{first: firstName, sibling: {sister: favoriteSibling};`
> similar way that we used Destructure array we can do it to objects too. `const {first, last, city} = bob; `
> Spread Operator `...objectName`

````JavaScript
const person = { name: 'john', job: 'developer' };
const newPerson = { ...person, city: 'chicago', name: 'peter' };
console.log(person);
---
#### This - Keyword

In Reg Functions (not arrow) "this" determined by "HOW"!!! a function is invoked (left of .).this always point it's defaults to globals - like window if there is nothing left of dot.

#### Factory Functions and Constructor Functions

Factory Functions are functions that return's a object based of the given parameters.
for Constructor Functions we use capital letter for first alphabet.

```JavaScript
function createPerson(firstName, lastName) {
  //have 2 parameter passed to values
  return {
    // has return about both parameters too
    firstName: firstName,
    lastName: lastName,
    fullName: function () {
      console.log(
        `My full name is ${this.firstName} ${this.lastName} and I love JS`
      );
    },
  };
}
const john = createPerson('john', 'anderson');]
john.fullName();
````

```JavaScript
function Person(firstName, lastName) {
  this.firstName = firstName;
  this.lastName = lastName;
  this.fullName = function () {
    console.log(
      `My full name is ${this.firstName} ${this.lastName} and I love React`
    );
  };
  console.log(this);
}
const john = new Person('john', 'anderson');
// new - creates new object, points to it and we don't use return
john.fullName();
```

> arrays and functions are objects in javascript
> All Objects in Javascript have access to constructor property that returns a constructor function that created it.
> in order to instantly run a method from an object, we use call like this (arguments are list of items): `greet.call(john, 'iran', 'esf');` john as the pointed object and the rest are the arguments.
> same thing can be happens in apply but the arguments are array of items. `greet.apply(john, ['iran', 'esf']);`
> in bind we can assign it and use it later + arguments - list of items `const susanGreat = greet.bind(susan, 'toronto', 'ca'); susanGreat();` we use susanGreat() to invoke it when we want it to.

```JavaScript
//usage in DOM
const counter = {
  count: 0,
  increment() {
    console.log(this);
    this.count++;
    console.log(this.count);
  },
};
const btn = document.querySelector('.increment');
const increment = counter.increment.bind(counter);
btn.addEventListener('click', increment);
btn.removeEventListener('click', increment);
```

#### Prototypal Inheritance Model

storing some properties and methods on constructor instead of making new copy every single time. (prototype property returns a object)
`Account.prototype.bank = 'CHASE';`

> the way that lookup property works here is when you add new property to object lookup will check to see is it in the object it self! if it was not there then it will check the parent (here it will check prototype)

```JavaScript
function Account(name, initialBalance) {
  this.name = name;
  this.balance = initialBalance;
}
// the reason that we don't add bank name and deposit to the object is that we don't want to repeat our selfs and use memory to have exact same data for every person
const john = new Account('john', 200);
const bob = new Account('bob', 0);

Account.prototype.bank = 'CHASE';
// adds new property
Account.prototype.deposit = function (amount) {
  // adds news method called deposit
  this.balance += amount;
  console.log(`Hello ${this.name}, your balance is ${this.balance}`);
};
console.log(john.bank);
console.log(bob);

john.deposit(300);
```

##### ES6 Classes:

in order to make a class, we need to declare class before naming our class, if we want to use constructor we declare it too. but we don't need declaration in method. fun fact is that ==we use property that we need in the class==. here it will not be a problem in memory or repeating.

```JavaScript
class Account {
  constructor(name, initialBalance) {
    this.name = name;
    this.balance = initialBalance;
  }
  bank = 'Chase';
  deposit(amount) {
    this.balance += amount;
    console.log(`Hello ${this.name}, your balance is ${this.balance}`);
    //because we have used `` here the method that we used is template strings
  }
}
const john = new Account('john', 0);
john.deposit(500);
```

---

### Conditional Statements:

==we are going to skip if else, Switch cases, Loops, while, do while and for.==
unlike forEach that we can't jump out of the loop we can use break, continue to do so.

```JavaScript
>, <, >=, <=, ==, === `(equal and same as type)`,
!= `(Unequal)`, !=== `(mosavi bashe ama type na)`,
% `(indicating left over)`, --, ++, *=, /=, +=, -=

const longName = 'John Smith Pepper III';
let shortName = '';
for (const letter of longName) {
  // console.log(letter);
  if (letter === ' ') {
    continue;
  } else {
    shortName += letter;
  }
}
```

#### Logical Operators:

|| means or, && means and.

---

#### Condition operator:

```JavaScript
// condition ? (runs if true) : (runs if false)
value ? console.log('value is true') : console.log('value is false');
```

---

### Implicit Type Conversion:

converting string of number to number type and the other way.

```JavaScript
value = parseInt(value);
value = parseString(value);
```

---

### String Properties and Methods:

```JavaScript
console.log(text.length);
console.log(text.toLowerCase());
console.log(text.toUpperCase());
console.log(text.charAt(0));
console.log(text.charAt(text.length - 1));
console.log(text.indexOf('e'));
// counts a certain numbers of e
console.log(text);
console.log(text.trim());
// for the start and end of whole text will remove spaces
console.log(text.trim().toLowerCase().startsWith('peter'));
// multiple command styling called chain commands in the english typing order
console.log(text.includes('eter'));
console.log(text.slice(0, 2));
console.log(text.slice(-3));
```

---

### Template Literals:

here we use backtick in order to add interpolation value in text.
Backtick characters `` - in place of above tab (left from one on keyboard)
Interpolation ${} - insert expression(value)

```JavaScript
const value = `Hey it's ${name} and he is ${age} years old. And here is some simple math ${
  4 + 4
}`;
```

---

### Array Properties and Methods:

```JavaScript
//length
console.log(names.length);
console.log(names[names.length - 1]);
// concat: pushing to array
const lastNames = ['pepper', 'onion', 'banana'];
const allNames = names.concat(lastNames);
// reverse: removing from the end of array
console.log(allNames.reverse());
//unshift => adding to the start of array
allNames.unshift('suse');
allNames.unshift('anna');
//shift => removes form start of array
allNames.shift();
//push => adds to end
allNames.push('suse');
//pop => push to end of array
allNames.pop();
// splice - mutates original array => select from the index (counter) till the number after and keeps it then removes the rest from array if there are 2 parameters.
const specificNames = allNames.splice(0, 3);
const specificNames = allNames.splice(0, 3, alice, john);
// if there are more than 2 parameters add the third till end to the array.
```

---

### Powerful Array Methods:

forEach, map, filter, find, reduce are the true power of using arrays.

#### ForEach:

```JavaScript
const people = [
  { name: 'bob', age: 20, position: 'developer' },
  { name: 'peter', age: 25, position: 'designer' },
  { name: 'suse', age: 30, position: 'the boss' },
];
//in order to have access to all array values we use forEach
people.forEach(function (item) {
  console.log(item.position.toUpperCase());
});
```

#### Map:

the usage of Map: fo adding or removing properties from array or objects.it will ==always returns a new array== and ==does not change size of original array== and uses values from original array when making new one.

> somehow when you don't want too remove the original array and Maneuver over whole array we use Map command. off course if we use array directly it's going to change the original array.

```JavaScript
const people = [
  { name: 'bob', age: 20, position: 'developer' },
  { name: 'peter', age: 25, position: 'designer' },
  { name: 'suse', age: 30, position: 'the boss' },
  { name: 'anna', age: 35, position: 'the boss' },
];
const names = people.map(function (person) {
  return `<h1>${person.name}</h1>`;
});
document.body.innerHTML = names.join('');
```

#### Filter:

filter will be used as filter a data from other kind of data with certain conditions.

> does return a new array and can manipulate the size of new array (like increase or decrease index from original array) and ==returns based on given condition==.

```JavaScript
const people = [
  { name: 'bob', age: 20, position: 'developer' },
  { name: 'peter', age: 25, position: 'designer' },
  { name: 'suse', age: 30, position: 'the boss' },
  { name: 'anna', age: 35, position: 'the boss' },
];
const developers = people.filter(function (person) {
  return person.position === 'senior developer';
});
//this command has changed all of person positions to senior developer then saved it in developers.
```

#### Find:

returns single instance - (in this case object) and returns first match, ==if no match undefined== and it's great for getting unique value out of a array.

```JavaScript
const people = [
  { name: 'bob', age: 20, position: 'developer', id: 1 },
  { name: 'peter', age: 25, position: 'designer', id: 2 },
  { name: 'suse', age: 30, position: 'the boss', id: 3 },
  { name: 'anna', age: 35, position: 'the boss', id: 4 },
];
const person = people.find(function (person) {
  return person.id === 3;
});
```

#### Reduce:

we use reduce mostly with condition and counting at same time. if reduce have 2 parameters, first one is ('acc') as total of all calculations and second one parameter is ('curr') as- current iteration/value.

```JavaScript
const people = [
  { name: 'bob', age: 20, position: 'developer', id: 1, salary: 200 },
  { name: 'peter', age: 25, position: 'designer', id: 2, salary: 300 },
  { name: 'suse', age: 30, position: 'the boss', id: 3, salary: 500 },
  { name: 'anna', age: 35, position: 'the boss', id: 4, salary: 500 },
];
const total = people.reduce(function (acc, currItem) {
  console.log(`total ${acc}`);
  console.log(`current money : ${currItem.salary}`);
  acc += currItem.salary;
  return acc; // reduce always has a return
}, 500); //500 is the initial starting number for counter
```

---

### Math:

```JavaScript
const number = 4.56789;
const result = Math.floor(number);
const number = 4.12222;
const result = Math.ceil(number);
const number = 89;
const result = Math.sqrt(number);
const result = Math.PI;
const result = Math.min(4, 5, 6, 7, 9);
const result = Math.max(4, 5, 6, 7, 9, 100, 200, 1000);
const result = Math.floor(Math.random() * 10 + 1);
```

---

### Date:

```JavaScript
const months = [
  'January',
  'February',
  'March',
  'April',
  'May',
  'June',
  'July',
  'August',
  'September',
  'October',
  'November',
  'December',
];

const days = [
  'Sunday',
  'Monday',
  'Tuesday',
  'Wednesday',
  'Thursday',
  'Friday',
  'Saturday',
];

// const date = new Date();
const date = new Date('1/12/2004');
const month = date.getMonth();
console.log(months[month]);

const day = date.getDay();
console.log(days[day]);

console.log(date.getDate());
console.log(date.getFullYear());

const sentence = `${days[day]}, ${date.getDate()} ${
  months[month]
} ${date.getFullYear()}`;

document.body.innerHTML = sentence;
```

---

we have skipped ==Local Scope and Global Scope==.

---

## Part 2: javaScript DOM

ways to play around html and css in any page.

> Spread Operator example:

```JavaScript
const text = [...headings]
  .map(item => `<span>${item.textContent}</span>`)
  .join('');
result.innerHTML = text;
```

### Select the element:

there are many ways to do this so let's start:

#### getElementsByTagName:

`getElementsByTagName('tag name');`
always ==returns HTMLCollection== that is a array-like object. in order to use it as array of text (anything) we use foreach. ==in order to convert HTMLCollection to array==:
` const headings = document.getElementsByTagName('h2');headings[0].style.color = 'red'; const betterItems = [...headings];`
the better way to use multiple elements so we can skip converting we use `querySelectorAll(class or tag name);` it, will automatically returns NodeList (objects are collections of nodes that is array) and after we do foreach for easy changes.

```JavaScript
const headings = document.getElementsByTagName('h2');
headings[0].style.color = 'red';
const betterItems = [...headings]; // Converting to array
betterItems.forEach(function (item) {
  console.log(item);
});
```

#### getElementsByClassName:

Again the ==returns object is HTMLCollection== that needs to be converted to array in order to make multiple changes at once.

```JavaScript
const listItems = document.getElementsByClassName('special');
listItems[2].style.color = 'blue';
console.log(listItems);
```

#### querySelector and querySelectorAll:

we use querySelector for single select and will always returns first one that it finds and querySelectedAll for multiple selection of element as tag or class.
got to remember hashtag ==# is for selecting ids or tags== and dot ==. is for targeting a class==.

```JavaScript
const result = document.querySelector('#result');
result.style.backgroundColor = 'blue';
const item = document.querySelector('.special');
const lastItem = document.querySelector('li:last-child');
const list = document.querySelectorAll('.special');
// we can use it for foreach because it's already a array.
list.forEach(function(item) {
  console.log(item);
  item.style.color = 'yellow';
});
```

an example for playing around all get elements by their attribute:

```JavaScript
const link = document.querySelectorAll(".first");
console.log(link);
console.log(link.item(0).getAttribute("id"));
const link2 = document.getElementsByClassName("first");
console.log(link2);
console.log(link2[0].getAttribute("id"));
const link3 = document.querySelector(".first");
console.log(link3);
console.log(link3?.getAttribute("id"));
const link4 = document.getElementById("link");
console.log(link4);
console.log(link4?.getAttribute('href'));
```

---

### childNodes:

when we are playing around array of texts or ome sort, childNodes command will returns all childNodes ==including whitespace== which is treated as a text node (array). `previousSibling` and `nextSibling` also includes whitespace.
the better usage is to use `children, firstChild, lastChild` or for parent `.parentElement` and `previousElementSibling` and `nextElementSibling` instead, so it wont be including whitespace.

```JavaScript
const first = document.querySelector('.first');
const second = (first.nextSibling.nextSibling.style.color = 'red');
// as here we are using nextSibling twice because of whitespace,
// we could have used only one nextElementSibling
console.log(second);
```

#### TextContext:

we use textContext or nodeValue to get text inside of element.

##### GetAttribute:

`getAttribute(what we need);`will be used when we need to see the class or tag or href or any attribute of selected element, then we can use `setAttribute(to what we want);` to set change in attribute.

```JavaScript
const link = document.querySelectorAll(".first");
console.log(link.item(0).getAttribute("id"));
const link2 = document.getElementsByClassName("first");
console.log(link2[0].getAttribute("id"));
const link3 = document.querySelector(".first");
console.log(link3?.getAttribute("id"));
const link4 = document.getElementById("link");
console.log(link4?.getAttribute('href'));
```

---

### classList:

we can use classList to add multiple styles to element. (u can use it like `classList.` to see all changes possible).

```JavaScript
const second = document.getElementById('second');
const third = document.getElementById('third');
second.className = 'colors text';
third.classList.add('colors');
third.classList.remove('text');
```

---

### Element Creation in DOM:

`createElement('element')` can make the element like h2 or paragraph, then `createTextNode('text content')` will inputs some text in element, then `element.appendChild(childElement)` append other element's on it, as `insertBefore('element','location');` adds it before our element and `replaceChild('new','old');` will replace the child element with new one. other stuff:

- `remove` : removes element.
- `removeChild` : removes the child of it.

> "a brain storm here is that instead of using document all the time we can be more specific and use element like body or anything else"

```JavaScript
const bodyDiv = document.createElement('div');
// to make a div
const text = document.createTextNode('a simple body div');
// creates text node (array)
bodyDiv.appendChild(text);
// place the text in bodyDiv
document.body.appendChild(bodyDiv);
// adds bodyDiv at the end of body element
const heading = document.createElement('h2');
const headingText = document.createTextNode('dynamic heading');
heading.appendChild(headingText);
heading.classList.add('blue');
result.appendChild(heading);
console.log(result.children);
```

`prepend` is another way to append before last element and `innerText`is another way to add text.

```JavaScript
const heading = document.createElement('h2');
heading.innerText = `i am a dynamic heading`;
document.body.prepend(heading);
const result = document.querySelector("#result");
const heading =result.querySelector('h1')
result.removeChild(heading);
```

---

### Event Listeners:

event listeners are used in javaScript to wait for something like a event to happen so they active what ever function they have inside of themselves. something like this:
`addEventListener('what event', which func)`

```JavaScript
const btn = document.querySelector('.btn');
const heading = document.querySelector('h2');
btn.addEventListener('click', function() {
heading.classList.add('red');
});
```

another example:

```JavaScript
const btn = document.querySelector('.btn');
const heading = document.querySelector('h2');
function changeColors() {
  let hasClass = heading.classList.contains('red');
  if (hasClass) {
    heading.classList.remove('red');
  } else {
    heading.classList.add('red');
  }
}
btn.addEventListener('click', changeColors);
```

as we just saw in last example listener could be different like waiting for a click, as listed below:

1. click - fires after full action occurs
2. mousedown - button is pressed
3. mouseup - button is released
4. mouseenter - moved onto an element
5. mouseleave - moved out of an element
6. keypress - when key is pressed
7. keydown - when key is down
8. keyup - when key is released

### Events:

we use Events to make something happens after listeners get triggered. this so called event usually comes as `e` or `evt` or `event` and it has some sort of type each time that can be consol logged with `event.type`.

- currentTarget - always refers to the element to which the event handler has been attached to
- target - identifies the element on which the event occurred
- event propagation - order the events are fired `(always double check your orders in events)`
- event bubbling - clicked element first then bubbles up -- it's default is on `(there is change that our according event can be a reason to propagation in other events)`
- event capturing - fires at the root and fires until reaches target
- how to stop it from happening? we use `e.stopPropagation();`
- DOMContentLoaded - The DOMContentLoaded event fires when the initial HTML document has been completely loaded and parsed, without waiting for stylesheets, images, and sub frames to finish loading.
- load - The load event is fired when the whole page has loaded, including all dependent resources such as stylesheets and images. This is in contrast to DOMContentLoaded, which is fired as soon as the page DOM has been loaded, without waiting for resources to finish loading.
- Scroll Event - waits until you scroll on element or document

```JavaScript
window.addEventListener('scroll', function () {
  console.log(window.scrollY + 'px');
  console.log(window.scrollX + 'px');
  });
```

#### Working on Window View

- innerWidth - The read-only Window property the interior width of the window in pixels
- innerHeight - The read-only property of the Window interface returns the interior height of the window in pixels
- Element.getBoundingClientRect() - The Element.getBoundingClientRect() method returns a DOMRect object providing information about the size of an element and its position relative to the viewport.
- resize - The resize event fires when the document view (window) has been resized.

```JavaScript
console.log('height : ' + window.innerWidth);
console.log('width : ' + window.innerHeight);
const btn = document.querySelector('.btn');
const box = document.querySelector('.box');
btn.addEventListener('click', function () {
  const values = box.getBoundingClientRect();
  console.log(values);
});
window.addEventListener('resize', function () {
  console.log(window.innerWidth);
});
```

#### currentTarget:

in the event we can use `currentTarget` to not miss spell words and to directly target the happening event.

```JavaScript
const heading = document.querySelector('h1');
const btn = document.querySelector('.btn');
const link = document.getElementById('link');
heading.addEventListener('click', event => {
  // => in es6 makes a function.
  console.log(event.currentTarget);
  // here, event has targeted the click listener at the heading(so heading in being targeted)
});
```

```JavaScript
btn.addEventListener('click', function(event) {
event.currentTarget.classList.add('blue');
console.log(event.type);
//shows the type of event
});
```

```JavaScript
function someFunc(e) {
e.preventDefault();
// preventDefault() - prevents default behavior
// in order to prevent event to happens (useful in forms) like sending data to another page
// the action methods in form will get disabled
}
```

```JavaScript
const heading = document.querySelector('h1');
const btn = document.querySelector('.btn');
const link = document.getElementById('link');
function someFunc(e) {
e.preventDefault();
}
link.addEventListener('click', someFunc);

const form = document.getElementById("form");
const name = document.getElementById("name");
const password = document.getElementById("password");
form.addEventListener("submit", function (e) {
// submit means when the submit button is clicked.
e.preventDefault()
console.log("form submitted");
console.log(name.value);
//.value shows the inputted value
console.log(password.value);
});

```

---

### Web Storage API:

Web Storage API is provided by all browsers. there are two different storage.

1. session storage - connection in very second
2. local storage - connection in longer period of time

and in order to command these storages we use these commands:

- setItem - make a value
- getItem - read the value
- removeItem - remove the value
- clear - removes all storage

```JavaScript
localStorage.setItem('name','john');
sessionStorage.setItem('name','john');
const name = localStorage.getItem('name');
console.log(name);
localStorage.removeItem('name');
localStorage.clear();
```

#### Using Json

> we can use ==SON.stringify()== to unbox json and ==JSON.parse()== to make the json.

an example to see how to save array and see it:

```JavaScript
const friends = ['john', 'peter', 'bob'];
localStorage.setItem('friends', JSON.stringify(friends));
const values = JSON.parse(localStorage.getItem('friends'));
console.log(values[2]);
```

---

### setTimeout:

runs function once after specific time

```JavaScript
function sayHello() {
  console.log('hello john');
}
setTimeout(sayHello, 1000);
// makes a delay to make it happen

// another example
function showScore(name, score) {
  console.log(`hello ${name}, your score is ${score}`);
}
const firstID = setTimeout(showScore, 3000, 'john', 34);
const secondID = setTimeout(showScore, 3000, 'peter', 88);
```

### setInterval:

runs function repeatedly, at specific intervals

```JavaScript
function showScore(name, score) {
  console.log(`hello ${name}, your score is ${score}`);
}
const firstID = setInterval(showScore, 2000, 'ted', 45);
```

#### clearInterval:

clearInterval will clear the set interval

```JavaScript
function showScore(name, score) {
  console.log(`hello ${name}, your score is ${score}`);
}
const firstID = setInterval(showScore, 2000, 'ted', 45);
clearInterval(firstID);
```

### Template Literals in DOM

using `` in DOM or anywhere is called Template Literals.

```JavaScript
const person = {
  name: "kyle",
  job: "developer",
  hobbies: ["surfing", "baking", "bowling"],
};
const result = document.getElementById("result");
result.innerHTML = `
<h2>${person.name}</h2>
<p>${person.job}</p>
<ul>
${person.hobbies
  .map(item => {
    return `<li>${item}</li>`;
  })
  .join("")}
</ul>
`;
```

### Tagged Template Literals

first we are going to need a function like highlight for working with it ten we add highlight before `so all the data in` will be argument. `highlight(text, ...vars)` ...vars collect all of the data. then we map data, `text.map((item, index)` here we use index as counter to know where we are in the data.

```JavaScript
const author = "Some Author";
const statement = "Some Statement";

const quote = highlight`Here is the ${statement} by ${author} and it could not be more true`;
console.log(quote);

function highlight(text, ...vars) {
  let awesomeText = text.map((item, index) => {
    return `${item} <strong class="blue">${vars[index] || ""}</strong>`;
  });
  return awesomeText.join("");
}

const result = document.getElementById("result");
result.innerHTML = quote;

```

---

==By passed 09 - OOP Projects part for now==

## Part 3: javaScript rest of ES6 Stuff

we have already mixed some es6 in other parts(as part 2 or quotation).

### for in

`for in` loop - iterate over object properties

```JavaScript
const person = {
  name: 'john',
  age: 25,
  status: 'student',
};
for (const propertyName in person) {
  console.log(`${propertyName} : ${person[propertyName]}`);
}
```

---

### Objects into Arrays

Three methods to convert objects into arrays

- `Object.keys()` - converts property names into array
- `Object.values()` - converts property values into array
- `Object.entries()` - converts both

```JavaScript
const person = {
  name: 'john',
  age: 25,
  status: 'student',
};
//Object.keys()
const keys = Object.keys(person);
// same goes for Object.values()
// Object.entries()
const result = Object.entries(person);

// map method
const newResult = result.map((item) => {
  const [first, second] = item;
  // console.log(first, second);
  return first;
});

// for of
for (const [first, second] of result) {
  // const  [first, second]= item;
  console.log(first, second);
}
```

### Set Object:

Set object - stores a collection of unique values of any type

has these methods inside of Set:

- `new Set()` - makes empty array (accepts iterable objects)
- `add(value)` - add properties in array
- `delete(value)` - removes properties
- `clear()` - clears all properties
- `has(value)` - checks if our object has the value

```JavaScript
const unique = new Set();
const random = 'third';
unique.add('first');
unique.add('second');
unique.add(random);
const result = unique.delete('third'); // has all unique properties except third
const isValue = unique.has("first"); // returns true or false
unique.clear();

//new Set() example 2:
const products = [
  {
    title: 'high-back bench',
    company: 'ikea',
  },
  {
    title: 'albany table',
    company: 'marcos',
  },
  {
    title: 'accent chair',
    company: 'microsoft',
  },
  {
    title: 'wooden table',
    company: 'ikea',
  },
];
const companies = products.map((item) => item.company); // stores all company names
const uniqueCompanies = new Set(companies); // stores all unique names of the already map companies
const finalCompanies = ['apple', ...uniqueCompanies]; // added apple to array with uniqueCompanies that has converted with rest operation to array
// all of 3 commands of top in 1 line
const result = ['all', ...new Set(products.map((item) => item.company))];
```

---

### String Include Method:

- String includes() - checks if a string contains another string.

```JavaScript
const products = [
  { title: 'Modern Poster' },
  { title: 'Bar Stool' },
  { title: 'Armchair' },
  { title: 'Leather Chair' },
];
const text = 'a';

const filteredProducts = products.filter((product) =>
  product.title.toLowerCase().includes(text)
);
```

- Array includes() - checks if the item is an array

```JavaScript
const groceries = ['milk', 'bread', 'meat'];
let randomItem = 'milk';
if (groceries.includes(randomItem, 1)) {
  console.log(`Yeah! it's on the list`);
}
```

## Part 4: javaScript Modules, Async, Ajax:

when we are talking about a module, we are talking about separate file in folder that contains an ability that has been written in javaScript and we can use it in any of our projects.
in code that we are doing our self we write `import {random, people} from "./utils/data.js"` the rest is in below codes:

in app.js:

```JavaScript
import { random, people } from './utils/data.js';
import showPeople from './utils/showPeople.js';
// because of default name doesn't mater here.
import get from './utils/getElement.js';

const container = get('.container');
const btn = get('.btn');

btn.addEventListener('click', () => {
  container.innerHTML = showPeople(people);
});
```

in data.js:

```JavaScript
export const random = 'random value';
export const people = [
  { name: 'john', job: 'developer' },
  { name: 'susan', job: 'designer' },
  { name: 'anna', job: 'the boss' },
];
```

in showPeople.js:

```JavaScript
export default (people) => {
  // because we have written default every time we import this file we mean this function.
  const newPeople = people
    .map((person) => {
      const { name, job } = person;
      return `<p>${name} <strong>${job}</strong></p>`;
    })
    .join('');
  return newPeople;
};
```

in getElement.js

```JavaScript
export default function (selection) {
  const element = document.querySelector(selection);
  if (element) {
    return element;
  } else {
    throw Error('you did not select element');
  }
}
```

---

### Synchronize:

JavaScript always reads 1 line at the time. General concept means that we can manipulate time for running a code after a period of time. it make sense to first boil water and at same time we cut onion, so we use `Fetch Data, Get GeoLocation, setTimeout and setTimer` and this tactic called asynchronous. here is simple example: (it's like doing thing in background)

```JavaScript
boilWater(10000);
console.log(`chop carrot`);

function boilWater(time) {
  console.log('boiling...');
  setTimeout(() => {
    console.log('done.');
  }, time);
}
```

this is going to make callback hell and it's not recommended.

#### Promises:

is the way to remove callback hell. it has 3 ways:

- Pending, Resolved, Rejected - After this : then, catch - pass another callback.

```JavaScript
const heading1 = document.querySelector('.one');
const heading2 = document.querySelector('.two');
const heading3 = document.querySelector('.three');
const btn = document.querySelector('.btn');
btn.addEventListener('click', () => {});

const promise = new Promise((resolve, reject) => {
  // this is how to write the code.
  let value = false;
  if (value) {
    resolve([1, 2, 4]);
  } else {
    reject(`there was a error, value is false`);
  }
});
promise
  .then((taco) => {
    // this is how to invoke it.
    console.log(taco);
  })
  .catch((err) => {
    //we need this too.
    console.log(err);
  });
```

Example for Reject:

```JavaScript
const heading1 = document.querySelector('.one');
const heading2 = document.querySelector('.two');
const heading3 = document.querySelector('.three');
const btn = document.querySelector('.btn');
const container = document.querySelector('.img-container');
const url = 'https://source.unsplash.com/random';
btn.addEventListener('click', () => {
  loadImage(url)
    .then((taco) => container.appendChild(taco))
    .catch((err) => console.log(err));
});

function loadImage(url) {
  return new Promise((resolve, reject) => {
    let img = new Image();
    // making a new image value to load
    img.addEventListener('load', () => {
      resolve(img);
    });
    img.addEventListener('error', () => {
      reject(new Error(`Failed to load image from the source : ${url}`));
    });
    img.src = url;
  });
}
```

Another example but with DOM:

```JavaScript
const heading1 = document.querySelector('.one');
const heading2 = document.querySelector('.four');
const heading3 = document.querySelector('.three');
const btn = document.querySelector('.btn');
btn.addEventListener('click', () => {
  addColor(1000, heading1, 'red')
    .then(() => addColor(2000, heading2, 'green')) // can be chained afterward
    .then(() => addColor(1000, heading3, 'blue'))
    .catch((err) => console.log(err));
});

function addColor(time, element, color) {
  return new Promise((resolve, reject) => {
    if (element) {
      setTimeout(() => {
        element.style.color = color;
        resolve(); // we can always resolve without doing anything
      }, time); // in whatever time like 2 seconds
    } else {
      reject(new Error(`There is no such element ${element}`));
    }
  });
}
```

#### An Even Better Way: AsyncAwait

Await always wait to resolve happen.
How to code it?

```JavaScript
async function someFunction (){
  await
}
const otherFunction = async() =>{
  await
}
```

Promise example to async:

```JavaScript
btn.addEventListener('click', async () => {
  const result = await displayColor();
  console.log(result);
});

async function displayColor() {
  try {
    const first = await addColor(1000, heading1, 'red');
    await addColor(1000, heading2, 'green');
    await addColor(1000, heading3, 'blue');
    console.log(first);
  } catch (error) {
    console.log(error);
  }
  return 'hello'; //async always have a return and we can, not use it.
}

function addColor(time, element, color) {
  return new Promise((resolve, reject) => {
    if (element) {
      setTimeout(() => {
        element.style.color = color;
        resolve();
      }, time);
    } else {
      reject(new Error(`There is no such element ${element}`));
    }
  });
}
```
