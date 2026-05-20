# Module 1: All About "String"

## Q1: The Welcome Message

**Scenario:** Ek social media app par naye user ko welcome karna hai.

**Requirements:** `username` ko use karke ek greeting string banayein jo kahe "Welcome, [username]".

**Starter Code:**

```javascript
function welcomeUser(username) {
  // TODO: Return a welcome string
}
```

**Test Cases:**

- `welcomeUser("Aman")` -> Expected: `"Welcome, Aman"`

## Q2: Full Name Generator

**Scenario:** Registration form mein user `firstName` aur `lastName` alag-alag daalta hai, par profile par dono saath dikhne chahiye.

**Requirements:** Dono strings ko combine (concatenate) karein beech mein ek space ke saath.

**Starter Code:**

```javascript
function getFullName(firstName, lastName) {
  // TODO: Combine and return full name
}
```

**Test Cases:**

- `getFullName("Virat", "Kohli")` -> Expected: `"Virat Kohli"`

## Q3: Modern Template Literals

**Scenario:** Aapko ek email receipt generate karni hai. String concatenation `+` ka use thoda messy ho jata hai, isliye ES6 template literals (backticks) use karein.

**Requirements:** `item` aur `price` variables ko use karke exact format return karein: "You bought a [item] for $[price]".

**Starter Code:**

```javascript
function getReceipt(item, price) {
  // TODO: Use template literals to return the string
}
```

**Test Cases:**

- `getReceipt("Shirt", 20)` -> Expected: `"You bought a Shirt for $20"`

## Q4: Password Length Check

**Scenario:** Security reason se humein check karna hai ki user ka password kitne characters lamba hai.

**Requirements:** Diye gaye `password` string ki total length return karein.

**Starter Code:**

```javascript
function getPasswordLength(password) {
  // TODO: Return the length of the string
}
```

**Test Cases:**

- `getPasswordLength("secret123")` -> Expected: `9`

## Q5: Standardizing Coupon Codes

**Scenario:** Users coupon code lowercase ya uppercase kisi me bhi daal dete hain. Humare system ko sab capitals mein chahiye.

**Requirements:** Input string ko completely Uppercase mein convert karke return karein.

**Starter Code:**

```javascript
function formatCoupon(code) {
  // TODO: Return uppercase version of code
}
```

**Test Cases:**

- `formatCoupon("diwali50")` -> Expected: `"DIWALI50"`

## Q6: Normalizing Email Inputs

**Scenario:** Email addresses hamesha lowercase mein store hone chahiye taaki login mein issue na aaye.

**Requirements:** Input email ko completely Lowercase mein convert karein.

**Starter Code:**

```javascript
function normalizeEmail(email) {
  // TODO: Return lowercase email
}
```

**Test Cases:**

- `normalizeEmail("Hello@GMAIL.com")` -> Expected: `"hello@gmail.com"`

## Q7: Escaping Quotes

**Scenario:** Aapko ek famous quote screen par dikhana hai jisme pehle se double quotes `" "` aate hain.

**Requirements:** Ek valid string banayein jo exactly yeh text return kare: `Einstein said, "Imagination is everything."`

**Starter Code:**

```javascript
function getQuote() {
  // TODO: Return the string with proper escaping or quote usage
}
```

**Test Cases:**

- `getQuote()` -> Expected: `'Einstein said, "Imagination is everything."'`

## Q8: The Type Checker

**Scenario:** Kabhi kabhi form fields se galat data aa jata hai. Humein verify karna hai ki aane wala data sach mein ek text (string) hai ya nahi.

**Requirements:** `typeof` operator ka use karein. Agar input string hai toh `true` return karein, warna `false`.

**Starter Code:**

```javascript
function isString(input) {
  // TODO: Check if input is a string
}
```

**Test Cases:**

- `isString("Hello")` -> Expected: `true`
- `isString(123)` -> Expected: `false`
