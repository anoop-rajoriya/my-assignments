# Module 2: Arrow Functions & IIFEs

## Q1: Quick Samosa Bill (Implicit Return)

**Scenario:** Arrow functions ka sabse bada fayda hai ki ek line mein without `return` keyword data bheja ja sakta hai.
**Requirements:** Ek single-line arrow function likhein jo `qty` aur `price` ko multiply kare.
**Starter Code:**

```javascript
// TODO: Convert this to a single-line Arrow Function
const getSamosaBill = (qty, price) => /* one-liner */;

```

**Test Cases:**

- `getSamosaBill(5, 10)` -> Expected: `50`
- `getSamosaBill(2, 15)` -> Expected: `30`
- `getSamosaBill(0, 20)` -> Expected: `0`

## Q2: Toll Checker (Arrow Function)

**Scenario:** Agar gaadi ka number even hai toh Toll pass, odd hai toh wait.
**Requirements:** Arrow function jisme ternary operator ho, string return kare `"Pass"` ya `"Wait"`.
**Starter Code:**

```javascript
const checkToll = (vehicleNum) => /* TODO */;

```

**Test Cases:**

- `checkToll(1234)` -> Expected: `"Pass"`
- `checkToll(9999)` -> Expected: `"Wait"`
- `checkToll(0)` -> Expected: `"Pass"`

## Q3: Dollar to Rupee Converter

**Scenario:** Simple converter arrow function.
**Requirements:** Dollar ko 83 se multiply karein aur arrow function ka use karein.
**Starter Code:**

```javascript
const convertToRupee = (dollars) => /* TODO */;

```

**Test Cases:**

- `convertToRupee(10)` -> Expected: `830`
- `convertToRupee(2)` -> Expected: `166`
- `convertToRupee(0)` -> Expected: `0`

## Q4: The Object Return Trap

**Scenario:** Arrow function se agar seedha Object `{}` return karna ho, toh JS usko block scope samajh leta hai unless aap `()` brackets use karein.
**Requirements:** Naya player create karne ka object return karein using an arrow function implicitly.
**Starter Code:**

```javascript
// TODO: Fix the syntax to implicitly return an object { name: pName, score: 0 }
const createPlayer = (pName) => { name: pName, score: 0 };

```

**Test Cases:**

- `createPlayer("Virat")` -> Expected: `{ name: "Virat", score: 0 }`
- `createPlayer("Rohit")` -> Expected: `{ name: "Rohit", score: 0 }`
- `createPlayer("")` -> Expected: `{ name: "", score: 0 }`

## Q5: Greeting Formatter

**Scenario:** App load hone par "Hello, Name" print karna hai.
**Requirements:** Arrow function jo string template literals use kare.
**Starter Code:**

```javascript
const greet = (name) => /* TODO: Return "Hello, [name]" */;

```

**Test Cases:**

- `greet("Aman")` -> Expected: `"Hello, Aman"`
- `greet("Raj")` -> Expected: `"Hello, Raj"`
- `greet("")` -> Expected: `"Hello, "`

## Q6: App Config Initializer (Basic IIFE)

**Scenario:** IIFE (Immediately Invoked Function Expression) turant call ho jate hain. App start hote hi config load karni hai.
**Requirements:** Diye gaye IIFE ko modify karein taaki wo "App Initialized" return kare ek variable mein.
**Starter Code:**

```javascript
const configStatus = (function () {
  // TODO: Return the string
})();
```

**Test Cases:**

- `configStatus` -> Expected: `"App Initialized"` (Variable must hold the value)

## Q7: Secret Token Generator (Privacy with IIFE)

**Scenario:** IIFE ke andar declare kiye variables bahar se access nahi hote (Privacy!).
**Requirements:** IIFE banayein. Uske andar ek variable banayein `token = "XYZ"`. IIFE wo string `"Bearer XYZ"` format me return kare jise `authHeader` me save kiya jaye.
**Starter Code:**

```javascript
const authHeader = (function () {
  // TODO: Declare secret token and return formatted string
})();
```

**Test Cases:**

- `authHeader` -> Expected: `"Bearer XYZ"`

## Q8: Dynamic Traffic Light (IIFE Default)

**Scenario:** Server load hote hi ek light color set hona chahiye.
**Requirements:** IIFE ka use karke random calculation logic wrap karein. Agar `Math.random() > 0.5` toh "Green", warna "Red" return karein.
**Starter Code:**

```javascript
const initialLight = (function () {
  // TODO: Return "Green" or "Red"
})();
```

**Test Cases:**

- `typeof initialLight` -> Expected: `"string"`
- `["Green", "Red"].includes(initialLight)` -> Expected: `true`

## Q9: Immediate Discount Engine (IIFE with Params)

**Scenario:** IIFE ko arguments bhi pass kiye ja sakte hain! Ek IIFE jo bill 100 aur discount 10 le.
**Requirements:** `(function(price, discount){...})(100, 10)` format use karke net price nikalen aur variable mein save karein.
**Starter Code:**

```javascript
const finalBill = (function (price, discount) {
  // TODO: Calculate and return discounted price
})(100, 10);
```

**Test Cases:**

- `finalBill` -> Expected: `90`

## Q10: Vada Pav Spice (Arrow + Condition)

**Scenario:** Customer ne spice scale manga hai. Arrow function block ka use.
**Requirements:** Agar `level > 5` hai to "Teekha", else "Meetha" return karein. Arrow function syntax use karein.
**Starter Code:**

```javascript
const vadaPavSpice = (level) => {
  // TODO: Add condition block
};
```

**Test Cases:**

- `vadaPavSpice(8)` -> Expected: `"Teekha"`
- `vadaPavSpice(3)` -> Expected: `"Meetha"`
- `vadaPavSpice(5)` -> Expected: `"Meetha"`

## Q11: Find the Match (Arrow + Loops)

**Scenario:** Array of objects me ek ID dhundni hai. (No built in `.find`!).
**Requirements:** Arrow function aur `for` loop se object dhundhein, match na ho toh `null` return karein.
**Starter Code:**

```javascript
const findUserById = (usersArray, id) => {
  // TODO: Loop through and return matching object
};
```

**Test Cases:**

- `findUserById([{id: 1, name: "A"}], 1)` -> Expected: `{id: 1, name: "A"}`
- `findUserById([{id: 1, name: "A"}], 2)` -> Expected: `null`
- `findUserById([], 1)` -> Expected: `null`

## Q12: Global Namespace Protection (IIFE)

**Scenario:** Ek purani HTML file mein 2 scripts hain jo ek hi variable `version` define kar rahi hain. Collision rokne ke liye ek script ko IIFE mein wrap karna padega.
**Requirements:** Return ek function karein IIFE ke andar se jo private `version` de. Ise "Module Pattern" ki basic stage kehte hain.
**Starter Code:**

```javascript
const systemInfo = (function () {
  let version = "2.0";
  return function () {
    return `Version is ${version}`;
  };
})();
```

**Test Cases:**

- `systemInfo()` -> Expected: `"Version is 2.0"`
- `systemInfo.version` -> Expected: `undefined` (Shows privacy)
- `typeof systemInfo` -> Expected: `"function"`
