
// Part 1: Predict and Explain

// console.log(a); // undefined
// console.log(b); // ReferenceError (TDZ)
// console.log(c); // ReferenceError (TDZ)

var a = 10;
let b = 20;
const c = 30;

// Part 2

// var can be re-declared
var a2 = 99;

// let and const cannot be re-declared in same scope
let b2 = 88;
const c2 = 77;

// Part 3

const user = { name: "Asad" };

user.name = "Ali"; // Allowed
console.log(user);

// user = {}; // TypeError

// Corrected Version

let num1 = 10;
let num2 = 20;
const num3 = 30;

console.log(num1);
console.log(num2);
console.log(num3);
[Screenshot](<img width="376" height="145" alt="Screenshot 2026-06-15 182647" src="https://github.com/user-attachments/assets/173ecfa5-ceee-429f-982a-5a561d5837e5" />
)
