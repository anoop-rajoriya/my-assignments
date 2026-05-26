# Module 2: Data Extraction & Shaping (Manual Mapping)

## Q1: Extracting Names for UI Dropdown

**Scenario:** API ne pura user object bhej diya `{id: 1, name: "Aman", age: 25}`, par dropdown menu ko sirf `"Aman"` strings ka array chahiye.
**Requirements:** Loop se har object ki `name` property nikal kar naye array me push karein.
**Starter Code:**

```javascript
function extractNames(users) {
  // TODO: Return an array of just the names
}
```

**Test Cases:**

- `extractNames([{id: 1, name: "Raj"}, {id: 2, name: "Neha"}])` -> Expected: `["Raj", "Neha"]`
- `extractNames([{name: "Aman"}])` -> Expected: `["Aman"]`
- `extractNames([])` -> Expected: `[]`

## Q2: Adding Discount Property

**Scenario:** Diwali sale chal rahi hai. Har product object ke andar ek nayi property `salePrice` dalni hai jo original price se 10% kam ho.
**Requirements:** Array of objects par loop lagayein, naya property add karein, aur modified array return karein.
**Starter Code:**

```javascript
function addSalePrice(products) {
  // TODO: Add salePrice (price * 0.9) to each object
}
```

**Test Cases:**

- `addSalePrice([{name: "Shirt", price: 100}])` -> Expected: `[{name: "Shirt", price: 100, salePrice: 90}]`
- `addSalePrice([{name: "Bag", price: 50}])` -> Expected: `[{name: "Bag", price: 50, salePrice: 45}]`
- `addSalePrice([])` -> Expected: `[]`

## Q3: Strings to Objects Converter

**Scenario:** Frontend component ko array of objects chahiye `[{label: "Red"}, {label: "Blue"}]`, par backend ne array of strings diya `["Red", "Blue"]`.
**Requirements:** Strings ke array ko objects ke array mein map karein using loop.
**Starter Code:**

```javascript
function formatForSelect(stringArray) {
  // TODO: Convert ["A"] to [{label: "A"}]
}
```

**Test Cases:**

- `formatForSelect(["Apple", "Banana"])` -> Expected: `[{label: "Apple"}, {label: "Banana"}]`
- `formatForSelect(["Delhi"])` -> Expected: `[{label: "Delhi"}]`
- `formatForSelect([])` -> Expected: `[]`

## Q4: Flattening the Cinema Seats (2D to 1D)

**Scenario:** Cinema hall mein seats rows and cols mein hain: `[["A1", "A2"], ["B1", "B2"]]`. Bookings check karne ke liye isko ek single array (1D) banana hai.
**Requirements:** Nested `for` loop (loop ke andar loop) lagayein aur sabhi items ek naye flat array mein push karein.
**Starter Code:**

```javascript
function flattenSeats(rows) {
  // TODO: Manually flatten a 2D array into 1D
}
```

**Test Cases:**

- `flattenSeats([["A1", "A2"], ["B1", "B2"]])` -> Expected: `["A1", "A2", "B1", "B2"]`
- `flattenSeats([["VIP1"], ["VIP2"]])` -> Expected: `["VIP1", "VIP2"]`
- `flattenSeats([])` -> Expected: `[]`

## Q5: Legacy API Translation (Key Renaming)

**Scenario:** Ek purani Hindi API user data `{"naam": "Raj", "umar": 20}` bhejti hai. Hume naye UI ke liye keys `name` aur `age` karni hain.
**Requirements:** Loop se har object padhein. Ek naya object banayein with English keys aur usko naye array mein push karein.
**Starter Code:**

```javascript
function translateKeys(legacyUsers) {
  // TODO: Map 'naam' to 'name', and 'umar' to 'age'
}
```

**Test Cases:**

- `translateKeys([{naam: "Raj", umar: 20}])` -> Expected: `[{name: "Raj", age: 20}]`
- `translateKeys([{naam: "Neha", umar: 25}])` -> Expected: `[{name: "Neha", age: 25}]`
- `translateKeys([])` -> Expected: `[]`

## Q6: Generating Full Names

**Scenario:** Registration form mein `firstName` aur `lastName` alag the. Profile page par combined `fullName` dikhana hai.
**Requirements:** Loop lagayein aur ek naya property `fullName` add karein har object mein. Baki properties waise hi rehni chahiye.
**Starter Code:**

```javascript
function generateFullNames(users) {
  // TODO: Combine firstName and lastName
}
```

**Test Cases:**

- `generateFullNames([{firstName: "Virat", lastName: "Kohli"}])` -> Expected: `[{firstName: "Virat", lastName: "Kohli", fullName: "Virat Kohli"}]`
- `generateFullNames([{firstName: "Aman", lastName: "Gupta"}])` -> Expected: `[{firstName: "Aman", lastName: "Gupta", fullName: "Aman Gupta"}]`
- `generateFullNames([])` -> Expected: `[]`

## Q7: Comma-Separated URL Params

**Scenario:** Bulk delete API ko IDs comma-separated string format mein chahiye (`"101,102,103"`). Hamare paas array of objects hain jinki `id` key hai.
**Requirements:** Loop lagakar IDs nikalen aur manually string concatenate karein (bina `.join()` use kiye).
**Starter Code:**

```javascript
function getIdsString(items) {
  // TODO: Extract IDs and concatenate with commas
}
```

**Test Cases:**

- `getIdsString([{id: 1}, {id: 2}, {id: 3}])` -> Expected: `"1,2,3"`
- `getIdsString([{id: 99}])` -> Expected: `"99"`
- `getIdsString([])` -> Expected: `""`

## Q8: Basic Date Splitter

**Scenario:** API string bhej rahi hai `"2025-12-31"`. Frontend Calendar component ko object chahiye: `{ year: "2025", month: "12", day: "31" }`.
**Requirements:** Array of date strings aayega. `.split("-")` use karke unko object mein format karke naya array return karein.
**Starter Code:**

```javascript
function formatDates(dateStrings) {
  // TODO: Map date strings to structured objects
}
```

**Test Cases:**

- `formatDates(["2025-08-15"])` -> Expected: `[{ year: "2025", month: "08", day: "15" }]`
- `formatDates(["2026-01-26", "2027-11-01"])` -> Expected: `[{ year: "2026", month: "01", day: "26" }, { year: "2027", month: "11", day: "01" }]`
- `formatDates([])` -> Expected: `[]`

## Q9: Masking Sensitive Information

**Scenario:** UI par dikhane se pehle user ka password "**\*\***" se mask karna hai for security.
**Requirements:** Loop chalayein. Array ke har object mein `password` property ki value ko `"******"` se replace karein (chahe original length kuch bhi ho).
**Starter Code:**

```javascript
function maskPasswords(users) {
  // TODO: Replace password values with asterisks
}
```

**Test Cases:**

- `maskPasswords([{name: "A", password: "123"}])` -> Expected: `[{name: "A", password: "******"}]`
- `maskPasswords([{name: "B", password: "admin"}])` -> Expected: `[{name: "B", password: "******"}]`
- `maskPasswords([])` -> Expected: `[]`

## Q10: Swapping Keys and Values (Reverse Lookup)

**Scenario:** Ek translation dictionary object hai: `{ "hello": "namaste", "bye": "alvida" }`. Humein isko palatna hai taaki Hindi se English search kar sakein.
**Requirements:** `for...in` loop lagayein. Ek naya object banayein jisme purane values nayi keys ban jayein aur purani keys nayi values.
**Starter Code:**

```javascript
function swapDictionary(dict) {
  // TODO: Reverse keys and values
}
```

**Test Cases:**

- `swapDictionary({ "yes": "haan", "no": "nahi" })` -> Expected: `{ "haan": "yes", "nahi": "no" }`
- `swapDictionary({ "water": "pani" })` -> Expected: `{ "pani": "water" }`
- `swapDictionary({})` -> Expected: `{}`
