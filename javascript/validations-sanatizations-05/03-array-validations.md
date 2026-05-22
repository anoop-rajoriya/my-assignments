# Module 3: Group Orders & Collection Checks (Array Validations)

## Q1: Is it really an Array?

**Scenario:** Function array list mangta hai, par backend ne string `"Ravi, Aman"` bhej diya. Crash hone se bachana hai.

**Requirements:** `Array.isArray()` method ka use karein. Agar array hai toh wahi array return karein, warna empty array `[]` return karein.

**Starter Code:**

```javascript
function ensureArray(data) {
  // TODO: Validate and fallback to empty array
}
```

**Test Cases:**

- `ensureArray(["Samose", "Kachori"])` -> Expected: `["Samose", "Kachori"]`
- `ensureArray("Samose, Kachori")` -> Expected: `[]`
- `ensureArray(null)` -> Expected: `[]`

## Q2: Empty Array Check

**Scenario:** Panipuri stall pe doston ka group aaya par khaya kisi ne kuch nahi. Array valid hai par khali hai `[]`.

**Requirements:** Array ki `length` check karein. Agar `0` hai toh `"No items eaten"` return karein, warna `"Generate Bill"`.

**Starter Code:**

```javascript
function checkConsumption(platesArray) {
  // TODO: Check array length
}
```

**Test Cases:**

- `checkConsumption([])` -> Expected: `"No items eaten"`
- `checkConsumption(["Puri1"])` -> Expected: `"Generate Bill"`
- `checkConsumption(["Puri1", "Puri2"])` -> Expected: `"Generate Bill"`

## Q3: Maximum Items Limit (Slice)

**Scenario:** Free coupon code par ek baar mein maximum 3 items hi mangwa sakte hain. User ne array mein 5 items daal diye.

**Requirements:** Agar array `length > 3` hai, toh array ko `.slice(0, 3)` karke trim kar dein aur return karein.

**Starter Code:**

```javascript
function enforceCouponLimit(items) {
  // TODO: Sanitize array length to max 3 items
}
```

**Test Cases:**

- `enforceCouponLimit(["Chai", "Coffee", "Biscuit", "Rusk"])` -> Expected: `["Chai", "Coffee", "Biscuit"]`
- `enforceCouponLimit(["Chai", "Coffee"])` -> Expected: `["Chai", "Coffee"]`
- `enforceCouponLimit([1, 2, 3, 4, 5])` -> Expected: `[1, 2, 3]`

## Q4: Safety Check Before Index Access

**Scenario:** Samosa dadi ki queue mein pehle (first) insaan ka naam nikalna hai. Agar queue khali hui aur aapne `queue[0]` nikala toh `undefined` aayega.

**Requirements:** Check karein array ki length > 0 hai toh `queue[0]` return karein, warna `"Queue Khali Hai"`.

**Starter Code:**

```javascript
function getFirstInQueue(queue) {
  // TODO: Safe array index access
}
```

**Test Cases:**

- `getFirstInQueue(["Ravi", "Aman"])` -> Expected: `"Ravi"`
- `getFirstInQueue([])` -> Expected: `"Queue Khali Hai"`
- `getFirstInQueue(["Neha"])` -> Expected: `"Neha"`

## Q5: Validating Array Inclusion

**Scenario:** Vada pav menu array `["Classic", "Cheese", "Schezwan"]` hai. Customer ne "Butter" manga.

**Requirements:** `.includes()` method se check karein agar ordered item menu mein hai toh `"Preparing"`, warna `"Not in Menu"` return karein.

**Starter Code:**

```javascript
const menu = ["Classic", "Cheese", "Schezwan"];
function validateOrder(item) {
  // TODO: Check if item exists in menu array
}
```

**Test Cases:**

- `validateOrder("Cheese")` -> Expected: `"Preparing"`
- `validateOrder("Butter")` -> Expected: `"Not in Menu"`
- `validateOrder("Classic")` -> Expected: `"Preparing"`

## Q6: Fallback for Undefined Arrays in Objects

**Scenario:** Zomato order object mein kabhi-kabhi `addons` property missing (undefined) hoti hai.

**Requirements:** Object destructuring ya simple access check karein. Agar `orderObj.addons` undefined/falsy hai, toh usko explicitly khali array `[]` set kar dein. Object return karein.

**Starter Code:**

```javascript
function sanitizeAddons(orderObj) {
  // TODO: Set addons to [] if it doesn't exist
}
```

**Test Cases:**

- `sanitizeAddons({ item: "Pizza" })` -> Expected: `{ item: "Pizza", addons: [] }`
- `sanitizeAddons({ item: "Burger", addons: ["Cheese"] })` -> Expected: `{ item: "Burger", addons: ["Cheese"] }`
- `sanitizeAddons({ addons: null })` -> Expected: `{ addons: [] }`

## Q7: Validating Array Data Types

**Scenario:** Ek function ko prices ki list mili hai `[10, 20, 30]`. Humein bas itna ensure karna hai ki list ka pehla item string na ho, Number ho.

**Requirements:** Array valid hai mankar, bas `typeof array[0]` check karein. Agar "number" hai toh true, warna false return karein.

**Starter Code:**

```javascript
function isFirstItemNumber(priceList) {
  // TODO: Check typeof the first array element
}
```

**Test Cases:**

- `isFirstItemNumber([100, 200])` -> Expected: `true`
- `isFirstItemNumber(["100", 200])` -> Expected: `false`
- `isFirstItemNumber([])` -> Expected: `false` (typeof undefined is not 'number')

## Q8: The Splice Sanitizer (Removing Junk)

**Scenario:** Kisi hacker ne chat list ke start mein "SPAM" word add kar diya hai array me.

**Requirements:** Check karein agar array ka 0th index `"SPAM"` hai, toh use `shift()` ya `splice()` use karke delete karein aur cleaned array return karein.

**Starter Code:**

```javascript
function removeSpam(chatArray) {
  // TODO: Check first element and remove if it is "SPAM"
}
```

**Test Cases:**

- `removeSpam(["SPAM", "Hello", "Hi"])` -> Expected: `["Hello", "Hi"]`
- `removeSpam(["Good", "Morning"])` -> Expected: `["Good", "Morning"]`
- `removeSpam(["SPAM"])` -> Expected: `[]`

## Q9: Array Merging Safely

**Scenario:** Do bills (arrays of prices) merge karne hain. Par kabhi-kabhi doosra bill API se nahi aata (null hota hai).

**Requirements:** Agar `bill2` ek valid array hai tabhi `bill1.concat(bill2)` karein, warna sirf `bill1` return karein.

**Starter Code:**

```javascript
function safeMerge(bill1, bill2) {
  // TODO: Merge safely only if bill2 is an array
}
```

**Test Cases:**

- `safeMerge([10, 20], [30])` -> Expected: `[10, 20, 30]`
- `safeMerge([10], null)` -> Expected: `[10]`
- `safeMerge([5], "error")` -> Expected: `[5]`

## Q10: Extracting Index via Validation (indexOf)

**Scenario:** Kirana store ki item list se hume "Rice" hatana hai. Pehle find karna hoga.

**Requirements:** `.indexOf()` method se "Rice" ka index dhundein. Agar index `-1` nahi hai (yani exist karta hai), toh string "Found at X" return karein, warna "Not Found".

**Starter Code:**

```javascript
function findRice(inventory) {
  // TODO: Use indexOf and conditional return
}
```

**Test Cases:**

- `findRice(["Dal", "Rice", "Aata"])` -> Expected: `"Found at 1"`
- `findRice(["Sugar", "Salt"])` -> Expected: `"Not Found"`
- `findRice(["Rice"])` -> Expected: `"Found at 0"`
