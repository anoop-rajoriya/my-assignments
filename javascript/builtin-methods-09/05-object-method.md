# Module 5: Object Methods Mastery

**Storyline:** Aap ek Banking & Profile Management app par kaam kar rahe hain. Data heavily Objects me stored hai aur aapko JS ke inbuilt `Object` utilities use karni hain.

## Q1: Extracting Account Features (`Object.keys`)

**Scenario:** User ki profile object me bohot saari keys hain (`name`, `balance`, `accType`). UI me dropdown options generate karne ke liye bas un sabhi keys (names) ka array chahiye.
**Requirements:** Inbuilt `Object.keys()` method ka use karein aur return karein.
**Starter Code:**

```javascript
function getProfileKeys(userObj) {
  // TODO: Return an array of the object's keys
}
```

**Test Cases:**

- `getProfileKeys({name: "Aman", balance: 100})` -> Expected: `["name", "balance"]`
- `getProfileKeys({accType: "Savings"})` -> Expected: `["accType"]`
- `getProfileKeys({a: 1, b: 2, c: 3})` -> Expected: `["a", "b", "c"]`
- `getProfileKeys({})` -> Expected: `[]`

## Q2: Calculating Total Funds (`Object.values`)

**Scenario:** Ek family account me sabhi members ke balance ek object me mapped hain: `{ father: 50000, mother: 40000, son: 1000 }`. Total family fund nikalna hai.
**Requirements:** Pehle `Object.values()` use karke sirf numbers ka array nikalein, fir `.reduce()` (ya loop) se sum karein.
**Starter Code:**

```javascript
function getFamilyTotal(balancesObj) {
  // TODO: Extract values and return their sum
}
```

**Test Cases:**

- `getFamilyTotal({father: 100, mother: 200})` -> Expected: `300`
- `getFamilyTotal({son: 50})` -> Expected: `50`
- `getFamilyTotal({a: 0, b: 0})` -> Expected: `0`
- `getFamilyTotal({})` -> Expected: `0`

## Q3: Transforming into a List (`Object.entries`)

**Scenario:** React Table ko list of arrays chahiye. Object data `{ "Aman": 500, "Raj": 200 }` ko 2D array me convert karna hai: `[["Aman", 500], ["Raj", 200]]`.
**Requirements:** `Object.entries()` method directly yehi kaam karta hai. Use karein aur return karein.
**Starter Code:**

```javascript
function convertToTableData(dataObj) {
  // TODO: Return an array of key-value pair arrays
}
```

**Test Cases:**

- `convertToTableData({a: 1, b: 2})` -> Expected: `[["a", 1], ["b", 2]]`
- `convertToTableData({name: "Raj"})` -> Expected: `[["name", "Raj"]]`
- `convertToTableData({x: true})` -> Expected: `[["x", true]]`
- `convertToTableData({})` -> Expected: `[]`

## Q4: Freezing the Bank Config (`Object.freeze`)

**Scenario:** Security configuration jese `interestRate: 6.5` ko pure program me koi aur modify na kar sake (accidentally bhi nahi).
**Requirements:** `Object.freeze()` apply karke wahi object return karein taaki wo immutable ho jaye.
**Starter Code:**

```javascript
function lockConfiguration(configObj) {
  // TODO: Freeze the object and return it
}
```

**Test Cases:**

- `const obj1 = lockConfiguration({rate: 5}); obj1.rate = 10; return obj1.rate;` -> Expected: `5`
- `const obj2 = lockConfiguration({fee: 0}); obj2.newKey = 1; return obj2.newKey;` -> Expected: `undefined`
- `const obj3 = lockConfiguration({name: "Bank"}); delete obj3.name; return obj3.name;` -> Expected: `"Bank"`
- `Object.isFrozen(lockConfiguration({}))` -> Expected: `true`

## Q5: Sealing the User Profile (`Object.seal`)

**Scenario:** User apni existing profile me details update kar sakta hai (e.g. `age` badalna), par nayi property (jaise `isAdmin`) add nahi kar sakta.
**Requirements:** `Object.seal()` ka use karein. Ye update allow karta hai but add/delete deny karta hai.
**Starter Code:**

```javascript
function secureProfile(userObj) {
  // TODO: Seal the object and return it
}
```

**Test Cases:**

- `const p1 = secureProfile({age: 20}); p1.age = 25; return p1.age;` -> Expected: `25` (Update works)
- `const p2 = secureProfile({name: "A"}); p2.role = "Admin"; return p2.role;` -> Expected: `undefined` (Add fails)
- `const p3 = secureProfile({name: "A"}); delete p3.name; return p3.name;` -> Expected: `"A"` (Delete fails)
- `Object.isSealed(secureProfile({}))` -> Expected: `true`

## Q6: Merging Bank Accounts (`Object.assign`)

**Scenario:** User ne apna Purana Bank Account aur Naya Bank Account ek sath link/merge karne ki request ki hai.
**Requirements:** `Object.assign()` ya spread syntax `{...obj1, ...obj2}` ka use karke dono objects ko combine karein aur naya object return karein.
**Starter Code:**

```javascript
function mergeAccounts(oldAcc, newAcc) {
  // TODO: Merge two objects together
}
```

**Test Cases:**

- `mergeAccounts({balance: 100}, {type: "Saving"})` -> Expected: `{balance: 100, type: "Saving"}`
- `mergeAccounts({a: 1}, {a: 2, b: 3})` -> Expected: `{a: 2, b: 3}` (New overrides old)
- `mergeAccounts({}, {x: 10})` -> Expected: `{x: 10}`
- `mergeAccounts({}, {})` -> Expected: `{}`

## Q7: Checking for Empty Objects

**Scenario:** API se user profile aayi hai. Hume check karna hai ki kya obj bilkul khali (Empty `{}`) to nahi hai?
**Requirements:** `Object.keys()` ki `.length` property check karein. Agar length 0 hai, toh `true` return karein warna `false`.
**Starter Code:**

```javascript
function isProfileEmpty(profile) {
  // TODO: Return boolean true if object has 0 keys
}
```

**Test Cases:**

- `isProfileEmpty({})` -> Expected: `true`
- `isProfileEmpty({name: "Aman"})` -> Expected: `false`
- `isProfileEmpty({age: 20, city: "Pune"})` -> Expected: `false`
- `isProfileEmpty({ length: 0 })` -> Expected: `false` (Has a key named 'length')

## Q8: Building Objects from Raw Matrix (`Object.fromEntries`)

**Scenario:** Data science team ne list of pairs bheje hain: `[["ACC123", 5000], ["ACC456", 2000]]`. Javascript isey Object structure me easy lookup ke liye read karna chahta hai.
**Requirements:** Arrays of array (Matrix) ko ek single key-value Object me badalne ke liye `Object.fromEntries()` ka seedha use karein.
**Starter Code:**

```javascript
function matrixToObject(entriesArray) {
  // TODO: Convert 2D array back to an Object
}
```

**Test Cases:**

- `matrixToObject([["a", 1], ["b", 2]])` -> Expected: `{a: 1, b: 2}`
- `matrixToObject([["name", "Raj"]])` -> Expected: `{name: "Raj"}`
- `matrixToObject([["x", true], ["y", false]])` -> Expected: `{x: true, y: false}`
- `matrixToObject([])` -> Expected: `{}`
