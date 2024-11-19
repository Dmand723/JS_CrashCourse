# JS_CrashCourse

Crash course notes

//single equals sign is assiment
/_double quals sign checks for just value ex: const x = '10' if(x==10) will be true and if(x=='10') will also be true _/

/_triple equals sign checks for vale and data type ex: const x= '10' if(x==='10') will be true but if(x=== 10) will not _/

// or statement is represeted by ||
// and statement is represed by &&

// LOGGING OUTPUT
alert('Hello World'); // Do not use for debugging. Stops script and only strings
console.log('Hello World');
console.error('This is an error');
console.warn('This is a warning');

// VARIABLES - var, let, const
let age = 30;

// let can be re-assigned, const can not
age = 31;

// DATA TYPES - String, Number, Boolean, null, undefined
const name = 'Brad';
const age = 37;
const rating = 3.5;
const isCool = true;
const x = null;
const y = undefined;
let z; // undefined

// Check type
console.log(typeof z);

// STRINGS

// Concatenation
console.log('My name is ' + name + ' and I am ' + age);
// Template literal (better)
console.log(`My name is ${name} and I am ${age}`);

// String methods & properties
const s = 'Hello World';
let val;
// Get length
val = s.length;
// Change case
val = s.toUpperCase();
val = s.toLowerCase();
// Get sub string
val = s.substring(0, 5);
// Split into array
val = s.split('');

// Arrays - varables that hold multipe values

const numbers = ["1", "2", "3"];

numbers[3] = "4";

numbers.push("5");
numbers.unshift("0");
numbers.pop();

console.log(numbers);
console.log(Array.isArray(numbers));
console.log(numbers.indexOf());

const person = {
firstname: " dawson",
lastname: "simmons",
age: 18,
address: {
st: "dad",
city: "mom",
},
};

person.email = "Dad@mom";

const todos = [
{
id: 1,
text: "do dishes",
isCompleated: true,
},
{
id: 2,
text: "take out trash",
isCompleated: true,
},
{
id: 3,
text: "Homework",
isCompleated: false,
},
];

const todoJSON = JSON.stringify(todos);
console.log(todoJSON);

//for
for (let i = 0; i <= 10; i++) {
console.log(`HELLO ${i}`);
}

//while
let i = 0;
while (i <= 10) {
console.log(`dad ${i}`);
i++;
}

for (let i = 0; i < todos.length; i++) {
console.log(todos[i].text);
}

for (let todo of todos) {
console.log(todo.text);
}

//foreach, map, filter

todos.forEach(function (todo) {
console.log(todo.text);
});

const todoText = todos.map(function (todo) {
return todo.text;
});

console.log(todoText);

const todoCompleted = todos
.filter(function (todo) {
return todo.isCompleated === true;
})
.map(function (todo) {
return todo.text;
});

console.log(todoCompleted);

//conditonals
//if & else/else if
const x = 4;
const y = 5;

if (x > 5 || y > 10) {
console.log("x greater than 5 or y is greater than 10");
} else if (x < 10 && y < 10) {
console.log("x and y are less than 10");
} else if (x > 10) {
console.log("x is greater than 10");
} else {
console.log("x is less than 10");
}

//ternary operators and switches
//ternary operators ?=then :=else
const x = 10;

const color = x > 10 ? "red" : "blue";

console.log(color);

//switches

switch (color) {
case "red":
console.log("Color is red");
break;
case "blue":
console.log("color is blue");
break;
default:
console.log("color is not red or blue");
break;
}

//Functions
function addNums(num1 = 2, num2 = 1) {
return num1 + num2;
}
//arrow function
const addNums2 = (num1, num2) => num1 + num2;
const addNums3 = (num1) => num1 + 4;

console.log(addNums3(2));

//object-oriented programming (OOP)
//constructor funtion
function Person1(firstName, lastName, dob) {
this.firstName = firstName;
this.lastName = lastName;
this.dob = new Date(dob);
this.getFullName = function () {
return `${this.firstName} ${this.lastName};`;
}; //this is created with every object
}

Person1.prototype.getBirthYear = function () {
return this.dob.getFullYear();
}; //this puts it in the prototype of the object

//Class
class Person2 {
constructor(firstName, lastName, dob) {
this.firstName = firstName;
this.lastName = lastName;
this.dob = new Date(dob);
}

getBirthYear() {
return this.dob.getFullYear();
}
getFullName() {
return `${this.firstName} ${this.lastName};`;
}
}

//Instantiate object
const person1 = new Person1("Dawson", "Simmons", "7-23-2006");
const person2 = new Person2("Rhyn", "Jones", "11-11-2024 15:57:00");

console.log(person2.getBirthYear());
console.log(person1.getFullName());
console.log(person1);
console.log(person2);

//DOM basics
const form = document.getElementById("my-form"); //loging form
console.log(document.querySelector("h1"));

//Single elemet selectors

//Multiple elemet selectors
console.log(document.querySelectorAll(".item")); //gives nodelist
console.log(document.getElementsByClassName("item")); //gives html collection (cant use array methods)
console.log(document.getElementsByTagName("li")); //gives HTMLCollection

const items = document.querySelectorAll(".item");

items.forEach((item) => console.log(item));

const ul = document.querySelector(".items");

//ul.remove();//removes the items
//ul.lastElementChild.remove()//removes the last itme
ul.firstElementChild.textContent = "hello"; //changes text content of item
ul.children[1].innerText = "Brad"; //changes inner text
ul.children[2].innerHTML = "<h1>Hello</h1>"; //adds inner HTML to item

const btn = document.querySelector(".btn");
btn.style.background = "red";//changes style of item

const btn = document.querySelector(".btn");

btn.addEventListener("click", (e) => {
e.preventDefault();
//console.log("click");
//console.log(e.target.className);
document.querySelector("#my-form").style.background = "#ccc";
document.querySelector("body").classList.add("bg-dark"); //Adds a class to selector
document.querySelector(".items").lastElementChild.innerHTML =
"<h1>Hello</h1>";
}); //adds a event listener to item
