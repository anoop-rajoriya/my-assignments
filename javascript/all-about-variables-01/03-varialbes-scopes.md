# Module 3: Variable Scopes (Block, Function, and Global)

## Q1: The Global Config

**Scenario (Problem):** App ka API Base URL har jagah use hota hai—login function mein bhi aur data fetch karne wale function mein bhi. Ise aisi jagah declare karna hoga jahan se sab functions ise access kar sakein.

**Requirements:** Ek global variable `baseUrl` banayein aur use `"[https://api.mywebsite.com](https://api.mywebsite.com)"` set karein taaki dono functions ise return kar sakein.

**Starter Code:**

```javascript
// TODO: Declare baseUrl globally

function getLoginUrl() {
  return baseUrl + "/login";
}

function getProfileUrl() {
  return baseUrl + "/profile";
}
```

**Test Cases:**

- `getLoginUrl()` -> Expected Output: `"[https://api.mywebsite.com/login](https://api.mywebsite.com/login)"`
- `getProfileUrl()` -> Expected Output: `"[https://api.mywebsite.com/profile](https://api.mywebsite.com/profile)"`

## Q2: Function Scope Privacy

**Scenario (Problem):** Bank ATM code mein PIN check hota hai. Jo variable PIN check karne ke liye use hota hai, wo function ke bahar kisi bhi haal mein leak nahi hona chahiye.

**Requirements:** `verifyPin` function ke andar ek variable `secretCode` declare karein. Function true/false return karega.

**Starter Code:**

```javascript
function verifyPin(inputPin) {
  // TODO: Declare secretCode here and set it to 1234

  return inputPin === secretCode;
}

// secretCode should NOT be accessible here
```

**Test Cases:**

- `verifyPin(1234)` -> Expected Output: `true`
- `console.log(typeof secretCode)` outside function -> Expected Output: `"undefined"`

## Q3: Block Scope with `let`

**Scenario (Problem):** Ek shopping app mein discount tabhi lagta hai jab amount > 1000 ho. Discount calculate karne ke liye jo temporary variable banega, wo sirf `if` block tak hi seemit rehna chahiye.

**Requirements:** `if` block ke andar `let` ka use karke `discountAmount` banayein.

**Starter Code:**

```javascript
function calculateFinalPrice(amount) {
  if (amount > 1000) {
    // TODO: Create a block-scoped variable discountAmount = amount * 0.1
    amount = amount - discountAmount;
  }
  // discountAmount should not exist here
  return amount;
}
```

**Test Cases:**

- `calculateFinalPrice(1200)` -> Expected Output: `1080`
- `calculateFinalPrice(500)` -> Expected Output: `500`

## Q4: The `var` Leak Bug

**Scenario (Problem):** Purane JavaScript mein `for` loop mein `var` use karne se variable loop ke bahar bhi zinda rehta tha (leak ho jata tha).

**Requirements:** Diye gaye code mein bug hai, `var` ko aisi chiz se replace karein ki `i` loop ke bahar `ReferenceError` de par loop sahi se chale.

**Starter Code:**

```javascript
function printNumbers() {
  let arr = [];
  // TODO: Fix the loop variable declaration so it doesn't leak out of the block
  for (var i = 0; i < 3; i++) {
    arr.push(i);
  }
  // System will check if 'i' exists here. We want it to be undefined!
  return arr;
}
```

**Test Cases:**

- `printNumbers()` -> Expected Output: `[0, 1, 2]`
- Trying to access `i` outside the for-loop should throw an error.

## Q5: Variable Shadowing

**Scenario (Problem):** Aapki app ka global theme "dark" hai. Par jab user "Print" button dabata hai, toh print layout sirf local theme "light" use karni chahiye, bina global theme ko badle. Ise Shadowing kehte hain.

**Requirements:** Global variable `theme` create karein. Phir function ke andar same naam ka (`theme`) local variable declare karein using `let`.

**Starter Code:**

```javascript
let theme = "dark";

function getPrintLayout() {
  // TODO: Shadow the global 'theme' variable by declaring a new one here
  // and set it to "light"

  return `Printing in ${theme} mode`;
}
```

**Test Cases:**

- `getPrintLayout()` -> Expected Output: `"Printing in light mode"`
- Checking `theme` globally after function call -> Expected Output: `"dark"`
