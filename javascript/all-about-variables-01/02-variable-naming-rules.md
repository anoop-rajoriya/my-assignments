# Module 2: Variables Naming Rules

## Q1: Fixing the Illegal Names

**Scenario (Problem):** Ek junior developer ne variables banaye hain par JavaScript ke naming rules follow nahi kiye, isliye syntax errors aa rahe hain.

**Requirements:** Diye gaye variables ke names ko fix karein taaki code bina error ke run ho sake. (Hint: variables numbers se start nahi ho sakte aur special chars allowed nahi hain except `_` aur `$`).

**Starter Code:**

```javascript
// TODO: Fix the variable names below
let 1stPlayer = "Virat";
let user-name = "Rohit";
let @age = 35;

function getDetails() {
  return `${1stPlayer}, ${user-name}, ${@age}`;
}

```

**Test Cases:**

- `getDetails()` -> Expected Output: `"Virat, Rohit, 35"` (after fixing names).

## Q2: The camelCase Convention

**Scenario (Problem):** Corporate apps mein readability bahut important hai. JavaScript mein variables ka naam camelCase mein hona standard practice hai.

**Requirements:** Bank account details ke variables ko standard camelCase format mein re-write karein aur unhe ek array mein return karein.

**Starter Code:**

```javascript
// TODO: Convert these to camelCase
let Account_Number = "123456789";
let FIRSTNAME = "Aman";
let is_Active_user = true;

function getBankDetails() {
  // TODO: return array [accountNumber, firstName, isActiveUser]
}
```

**Test Cases:**

- Variables should strictly be `accountNumber`, `firstName`, `isActiveUser`.
- `getBankDetails()` -> Expected Output: `["123456789", "Aman", true]`

## Q3: Escaping Reserved Keywords

**Scenario (Problem):** JS mein kuch words reserved hain (jaise `class`, `return`, `function`). Aap inhe variable names ki tarah direct use nahi kar sakte. Ek school app banate waqt developer ne `class` variable bana diya.

**Requirements:** Code ko fix karein by renaming the variable. Aisa naam choose karein jo valid ho (e.g., `studentClass` ya `grade`).

**Starter Code:**

```javascript
// TODO: Fix the reserved keyword error
let class = 10;
let return = "passed";

function getResult() {
  return `Student is in grade ${class} and has ${return}`;
}

```

**Test Cases:**

- Code should compile without syntax errors.
- `getResult()` -> Expected Output: `"Student is in grade 10 and has passed"`

## Q4: Case Sensitivity Trap

**Scenario (Problem):** JavaScript case-sensitive language hai. `CouponCode` aur `couponCode` alag-alag variables maane jaate hain. Aapko ek discount validation system fix karna hai.

**Requirements:** Ek hi variable name (correct casing ke sath) use karke logic fix karein taaki if-condition sahi se kaam kare.

**Starter Code:**

```javascript
let couponCode = "DIWALI50";

function checkCoupon() {
  // TODO: Fix the variable casing below to match the declaration
  if (CouponCode === "DIWALI50") {
    return "Discount Applied";
  } else {
    return "Invalid Coupon";
  }
}
```

**Test Cases:**

- `checkCoupon()` -> Expected Output: `"Discount Applied"`

## Q5: Meaningful Names Refactoring

**Scenario (Problem):** Ek developer ne Simple Interest calculate karne ka formula likha hai par variables ke naam `a`, `b`, `c` rakh diye hain, jisse code samajh nahi aa raha.

**Requirements:** `a`, `b`, `c` ko rename karke unka sahi naam rakhein: `principal`, `rate`, aur `time`.

**Starter Code:**

```javascript
// Rename a, b, c to meaningful names
function calculateInterest(a, b, c) {
  let d = (a * b * c) / 100;
  return d;
}
```

**Test Cases:**

- `calculateInterest(10000, 5, 2)` -> Expected Output: `1000`
- Code must use variable names `principal`, `rate`, and `time`.
