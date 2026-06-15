###b1 code###

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


<img width="376" height="145" alt="Screenshot 2026-06-15 182647" src="https://github.com/user-attachments/assets/ee4db131-595c-4627-9824-a070b69b7dc1" />



b2.js

function typeAnalyser(value) {
  return {
    input: value,
    typeofResult: typeof value,
    isArray: Array.isArray(value),
    isNull: value === null,
    toNumber: Number(value),
    toBoolean: Boolean(value),
    toString: String(value)
  };
}

console.log(typeAnalyser(42));
console.log(typeAnalyser("hello"));
console.log(typeAnalyser(null));
console.log(typeAnalyser([]));
console.log(typeAnalyser(undefined));
console.log(typeAnalyser(true));
console.log(typeAnalyser(0));
console.log(typeAnalyser(""));



<img width="419" height="449" alt="Screenshot 2026-06-15 184141" src="https://github.com/user-attachments/assets/a7d4ab55-abf9-4b1e-b00b-173da4c6243d" />


<img width="296" height="450" alt="Screenshot 2026-06-15 184231" src="https://github.com/user-attachments/assets/6da96732-a29f-4cab-8bd3-a306f936ec94" />

<img width="243" height="232" alt="Screenshot 2026-06-15 184304" src="https://github.com/user-attachments/assets/c6ce453f-6f34-4dc7-a40b-afacb992f739" />


b3 code 

function calculateDiscount(price, userType, isMember) {

  if (typeof price !== "number" || price <= 0) {
    return "Invalid price";
  }

  let finalPrice = price;

  if (userType === "admin") {
    finalPrice *= 0.5;
  } else if (price > 1000) {
    finalPrice *= 0.8;
  } else if (price > 500) {
    finalPrice *= 0.9;
  }

  if (isMember) {
    finalPrice *= 0.95;
  }

  finalPrice = Math.max(finalPrice, 1);

  return finalPrice.toFixed(2);
}

console.log(calculateDiscount(1200, "user", false));
console.log(calculateDiscount(1200, "user", true));
console.log(calculateDiscount(600, "admin", true));
console.log(calculateDiscount(-50, "user", false));
console.log(calculateDiscount("abc", "user", false));

<img width="416" height="259" alt="Screenshot 2026-06-15 184458" src="https://github.com/user-attachments/assets/65e1b2df-bb65-4d0f-994f-4326fca9b522" />


b4 code


// ====================
// Bug 1
// ====================

const cart1 = {
  items: ["JS Book", "React Book"],
  total: 150
};

const cart2 = structuredClone(cart1);

cart2.items.push("Node Book");

console.log("cart1:", cart1.items);
console.log("cart2:", cart2.items);

// ====================
// Bug 2
// ====================

function applyTax(order) {
  return {
    ...order,
    total: order.total * 1.17
  };
}

const myOrder = {
  id: 1,
  total: 100
};

const taxedOrder = applyTax(myOrder);

console.log("Original:", myOrder.total);
console.log("Taxed:", taxedOrder.total);

// ====================
// Bug 3
// ====================

const defaultConfig = {
  theme: "dark",
  lang: "en",
  nested: {
    fontSize: 14
  }
};

function resetConfig() {
  return structuredClone(defaultConfig);
}

let appConfig = {
  theme: "light",
  lang: "ur",
  nested: {
    fontSize: 20
  }
};

appConfig = resetConfig();

console.log(appConfig.theme);
console.log(appConfig.nested.fontSize);

<img width="307" height="165" alt="Screenshot 2026-06-15 184743" src="https://github.com/user-attachments/assets/71bf2425-9ce3-4e37-89d6-e133175a719f" />





b5 code




// 1

function addToCart(cart, item) {
  return [...cart, item];
}

const cart = ["milk", "eggs"];
const newCart = addToCart(cart, "bread");

console.log(newCart);
console.log(cart);

// 2

function updateUserAge(user, newAge) {
  return {
    ...user,
    age: newAge
  };
}

const user = {
  name: "Ali",
  age: 25
};

const updatedUser = updateUserAge(user, 26);

console.log(updatedUser);
console.log(user);

// 3

function incrementScore(scores, playerName) {
  return {
    ...scores,
    [playerName]: (scores[playerName] || 0) + 1
  };
}

const scores = {
  Ali: 5,
  Sara: 3
};

const updatedScores = incrementScore(scores, "Ali");

console.log(updatedScores);
console.log(scores);

// 4

function reverseString(str) {
  return str.split("").reverse().join("");
}

console.log(reverseString("hello"));

// 5

function removeItem(arr, index) {
  return arr.filter((_, i) => i !== index);
}

const numbers = [1, 2, 3, 4];

const newNumbers = removeItem(numbers, 1);

console.log(newNumbers);
console.log(numbers);


<img width="308" height="226" alt="Screenshot 2026-06-15 185203" src="https://github.com/user-attachments/assets/af2e11eb-1265-48a7-9cc0-3e54a4eae737" />

