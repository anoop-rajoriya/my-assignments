# Module 3: Scopes, Lexical Scoping & Closures

## Q1: The Shop Name (Local vs Global Scope)

**Scenario:** Ek dukan ka naam global hai. Ek branch manager apne hisaab se local naam rakhta hai.
**Requirements:** Function ke andar ek local variable banayein jo global ko shadow kare.
**Starter Code:**

```javascript
let shopName = "Global Kirana";

function getLocalShopName() {
  // TODO: Create a local variable with the SAME NAME 'shopName' set to "Local Kirana"
  return shopName;
}
```

**Test Cases:**

- `getLocalShopName()` -> Expected: `"Local Kirana"`
- `shopName` (Global) -> Expected: `"Global Kirana"`

## Q2: Dada ji ka Sandook (Lexical Scoping)

**Scenario:** Inner function ko hamesha apne Outer function ke variables yaad rehte hain (Lexical Scope).
**Requirements:** `dadaJi` function mein `khazana = "Gold"` hai. Uske andar `pota` (grandson) function banayein jo `khazana` ko return kare.
**Starter Code:**

```javascript
function dadaJi() {
  let khazana = "Gold";
  function pota() {
    // TODO: Return khazana
  }
  return pota();
}
```

**Test Cases:**

- `dadaJi()` -> Expected: `"Gold"`

## Q3: Restaurant Menu Hierarchy

**Scenario:** Chain of scope execution. Function pehle apne block me variable dhoondhta hai, fir bahar, fir sabse bahar.
**Requirements:** Nested functions. Outer mein `dish = "Samosa"`. Inner mein `dish = "Kachori"`. Inner return kya karega? Code the logic.
**Starter Code:**

```javascript
function outerRestaurant() {
  let dish = "Samosa";
  function innerChef() {
    let dish = "Kachori";
    // TODO: Return dish
  }
  return innerChef();
}
```

**Test Cases:**

- `outerRestaurant()` -> Expected: `"Kachori"`

## Q4: Udhaar Khata (Closure Basic)

**Scenario:** Closure ka asali jaadu: Ek function execute hokar khatam ho jata hai, par uska return kiya hua inner function outer variables ko "Zinda" rakhta hai!
**Requirements:** Ek function `createKhata` banayein jo ek function return kare. Inner function jab call ho, tab balance 10 se badha de aur naya balance de.
**Starter Code:**

```javascript
function createKhata() {
  let balance = 0;
  return function () {
    // TODO: Increment balance by 10 and return it
  };
}
// Usage: const myKhata = createKhata();
```

**Test Cases:**

- `const k = createKhata(); k();` -> Expected: `10`
- `k();` -> Expected: `20`
- `const k2 = createKhata(); k2();` -> Expected: `10` (Separate instance)

## Q5: Token System at Bank (Closure)

**Scenario:** Bank me ticket machine button dabane par sequence me number deti hai (1, 2, 3...). Value state me maintain honi chahiye.
**Requirements:** `tokenMachine` likhein jo ek closure return kare jo next token number produce kare.
**Starter Code:**

```javascript
function tokenMachine() {
  let currentToken = 0;
  // TODO: Return a function that increments and returns currentToken
}
```

**Test Cases:**

- `const getTkn = tokenMachine(); getTkn();` -> Expected: `1`
- `getTkn();` -> Expected: `2`
- `getTkn();` -> Expected: `3`

## Q6: Secret VIP Pass (Data Hiding via Closure)

**Scenario:** Security pin kisi array/object me direct access nahi hona chahiye. Sirf ek function hona chahiye jo check karke True/False de.
**Requirements:** `createVIPPass(secretPin)` jo return karega ek inner function jisko `input` dene par True milega agar wo `secretPin` se match kare.
**Starter Code:**

```javascript
function createVIPPass(secretPin) {
  // TODO: Return a function that takes 'input' and compares it with 'secretPin'
}
```

**Test Cases:**

- `const check = createVIPPass(1234); check(1234)` -> Expected: `true`
- `check(9999)` -> Expected: `false`
- `check.secretPin` -> Expected: `undefined`

## Q7: The Discount Generator (Partial Application / Closure)

**Scenario:** Diwali ke liye dukan me 50% ki sale tag machine banani hai. Machine ek baar 50% ke liye set ho gayi, toh bas item ki original price daalo aur final rate nikal lo.
**Requirements:** `makeDiscount(percent)` jo return karega function `(price)`. Inner function final price calculate karega `(price - price*percent/100)`.
**Starter Code:**

```javascript
function makeDiscount(percent) {
  // TODO: Return a function that takes price and returns discounted price
}
```

**Test Cases:**

- `const halfOff = makeDiscount(50); halfOff(1000)` -> Expected: `500`
- `const tenOff = makeDiscount(10); tenOff(100)` -> Expected: `90`
- `halfOff(200)` -> Expected: `100`

## Q8: The Piggy Bank (Accumulating Strings/Arrays)

**Scenario:** Gullak (Piggy bank) mein baar-baar coins daalne hain.
**Requirements:** `createGullak()` ek array closure me rakhega. Inner function jab call ho with `coin`, wo array me push kare aur pura array return kare.
**Starter Code:**

```javascript
function createGullak() {
  let coins = [];
  // TODO: Return inner function taking 'coin' and updating array
}
```

**Test Cases:**

- `const gullak = createGullak(); gullak(5)` -> Expected: `[5]`
- `gullak(10)` -> Expected: `[5, 10]`
- `createGullak()(1)` -> Expected: `[1]`

## Q9: ATM Pin Retry Limit (Stateful Closure)

**Scenario:** User sirf 3 baar ATM PIN daal sakta hai.
**Requirements:** `atmTracker()` return kare ek function. Har call pe attempt 1 badhega. Agar attempts > 3 hon toh `"Blocked"`, warna `"Try Again"` return kare.
**Starter Code:**

```javascript
function atmTracker() {
  let attempts = 0;
  // TODO: Implement attempts logic
}
```

**Test Cases:**

- `const atm = atmTracker(); atm(); atm(); atm();` -> Expected: `"Try Again"` (for first 3)
- `atm();` (4th call) -> Expected: `"Blocked"`
- `atm();` (5th call) -> Expected: `"Blocked"`

## Q10: Closure Loop Trap `var` vs `let`

**Scenario:** Purani JS me `for(var i=0; i<3; i++)` se callbacks hamesha 3 return karte the! `let` ne ye theek kiya kyunki wo block scoped hai aur har iteration ke liye naya closure environment banata hai.
**Requirements:** 3 functions banakar ek array me return karne hain jo call hone par sequence me 0, 1, 2 dein. `let` ka use karke loop banayein aur closure ensure karein.
**Starter Code:**

```javascript
function buildFunctions() {
  let funcs = [];
  // TODO: Use let in a for loop from 0 to 2, push functions that return 'i'
  return funcs;
}
```

**Test Cases:**

- `const f = buildFunctions(); f[0]()` -> Expected: `0`
- `f[1]()` -> Expected: `1`
- `f[2]()` -> Expected: `2`

## Q11: Salary Increment Manager

**Scenario:** Corporate mein HR ke paas har employee ka specific increment manager hota hai jisme current base salary yaad rehti hai.
**Requirements:** `salaryManager(base)` function. Inner function `(increment)` return hoga jo base me increment jod de aur update kare taaki naya base permanently update ho jaye.
**Starter Code:**

```javascript
function salaryManager(base) {
  // TODO: Return function that adds increment to base and returns updated base
}
```

**Test Cases:**

- `const mySalary = salaryManager(10000); mySalary(2000)` -> Expected: `12000`
- `mySalary(3000)` -> Expected: `15000`
- `const hrSalary = salaryManager(50000); hrSalary(10000)` -> Expected: `60000`

## Q12: Bank Balance Protection (IIFE + Closure)

**Scenario:** Global variable banaye bina ek aisa balance counter jo strictly bahar se direct change na ho sake par get/set kiya ja sake.
**Requirements:** Ek object return karein jisme `deposit(amount)` aur `getBalance()` closure functions hon.
**Starter Code:**

```javascript
function createBankAccount() {
  let balance = 0;
  return {
    deposit: function (amt) {
      /* TODO */
    },
    getBalance: function () {
      /* TODO */
    },
  };
}
```

**Test Cases:**

- `const acc = createBankAccount(); acc.deposit(100); acc.getBalance()` -> Expected: `100`
- `acc.balance` -> Expected: `undefined`
- `acc.deposit(50); acc.getBalance()` -> Expected: `150`
