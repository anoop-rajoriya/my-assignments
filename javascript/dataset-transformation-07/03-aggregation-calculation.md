# Module 3: Aggregations & Calculations (Manual Reduce)

## Q1: Shopping Cart Grand Total

**Scenario:** E-commerce checkout page par array of items hai `[{price: 100, qty: 2}]`. Grand total nikalna hai.
**Requirements:** Ek `total` variable maintain karein. Loop mein `price * qty` add karte jayein. Return `total`.
**Starter Code:**

```javascript
function calculateCartTotal(cartItems) {
  // TODO: Sum up (price * qty) manually
}
```

**Test Cases:**

- `calculateCartTotal([{price: 100, qty: 2}, {price: 50, qty: 1}])` -> Expected: `250`
- `calculateCartTotal([{price: 200, qty: 3}])` -> Expected: `600`
- `calculateCartTotal([])` -> Expected: `0`

## Q2: The Class Topper

**Scenario:** Students ke array mein marks diye hain. Sabse zyada marks kiske hain us student ka object return karna hai.
**Requirements:** Loop se traverse karein aur ek `topStudent` object track karein jiske marks sabse zyada hon.
**Starter Code:**

```javascript
function getTopper(students) {
  // TODO: Return the entire object of the student with highest marks
}
```

**Test Cases:**

- `getTopper([{name: "Raj", marks: 80}, {name: "Neha", marks: 95}])` -> Expected: `{name: "Neha", marks: 95}`
- `getTopper([{name: "Aman", marks: 60}])` -> Expected: `{name: "Aman", marks: 60}`
- `getTopper([])` -> Expected: `null`

## Q3: Tallying Categories (Frequency Map)

**Scenario:** Admin dashboard par chart banana hai ki kis category ke kitne products hain. Array aayega `[{cat: "Electronics"}, {cat: "Clothing"}, {cat: "Electronics"}]`.
**Requirements:** Loop lagakar ek empty object `{}` mein har category ka count store karein. Example return: `{ Electronics: 2, Clothing: 1 }`.
**Starter Code:**

```javascript
function tallyCategories(products) {
  // TODO: Count occurrences of each category key
}
```

**Test Cases:**

- `tallyCategories([{cat: "A"}, {cat: "B"}, {cat: "A"}])` -> Expected: `{ A: 2, B: 1 }`
- `tallyCategories([{cat: "Food"}])` -> Expected: `{ Food: 1 }`
- `tallyCategories([])` -> Expected: `{}`

## Q4: Calculating Average Rating

**Scenario:** Ek restaurant ke reviews hain (stars 1-5). UI par inka exact average decimal dikhana hai.
**Requirements:** Loop se saari ratings sum karein, fir array length se divide karein. Return the number. Handle division by zero.
**Starter Code:**

```javascript
function getAverageRating(reviews) {
  // TODO: Return average rating. Return 0 if array is empty.
}
```

**Test Cases:**

- `getAverageRating([{stars: 5}, {stars: 4}, {stars: 3}])` -> Expected: `4`
- `getAverageRating([{stars: 5}, {stars: 5}])` -> Expected: `5`
- `getAverageRating([])` -> Expected: `0`

## Q5: Grouping Orders by City

**Scenario:** Delivery logistics app ko route plan karne ke liye orders ko city ke hisaab se group karna hai.
**Requirements:** Ek object banayein jisme keys `city` hon aur unki values us city ke orders ka array hon.
**Starter Code:**

```javascript
function groupOrdersByCity(orders) {
  // TODO: Create a map like { Mumbai: [{order}], Delhi: [{order}] }
}
```

**Test Cases:**

- `groupOrdersByCity([{id: 1, city: "Pune"}, {id: 2, city: "Pune"}])` -> Expected: `{ Pune: [{id: 1, city: "Pune"}, {id: 2, city: "Pune"}] }`
- `groupOrdersByCity([{id: 1, city: "Delhi"}, {id: 2, city: "Agra"}])` -> Expected: `{ Delhi: [{id: 1, city: "Delhi"}], Agra: [{id: 2, city: "Agra"}] }`
- `groupOrdersByCity([])` -> Expected: `{}`

## Q6: Flattening and Summing Nested Bills

**Scenario:** Ek table pe multiple customers bethe hain. Unke bills 2D array mein hain: `[[10, 20], [30, 40]]`. Pura grand total chahiye.
**Requirements:** Nested loop lagayein (Array ke andar Array padhein) aur ek single total calculate karein.
**Starter Code:**

```javascript
function getGrandTotal(nestedBills) {
  // TODO: Sum all numbers in the 2D array
}
```

**Test Cases:**

- `getGrandTotal([[10, 20], [30, 40]])` -> Expected: `100`
- `getGrandTotal([[50], [50]])` -> Expected: `100`
- `getGrandTotal([])` -> Expected: `0`

## Q7: The "All Delivered" Boolean Check

**Scenario:** Order status UI par "Order Complete" tabhi dikhega jab array ke SABHI items ka `status === "Delivered"` ho.
**Requirements:** Loop chalayein. Agar ek bhi item pending dikhe toh turant `false` return karein. Agar loop khatam ho jaye bina ruke, toh `true`.
**Starter Code:**

```javascript
function isOrderComplete(items) {
  // TODO: Return true ONLY if all items are "Delivered"
}
```

**Test Cases:**

- `isOrderComplete([{status: "Delivered"}, {status: "Delivered"}])` -> Expected: `true`
- `isOrderComplete([{status: "Delivered"}, {status: "Pending"}])` -> Expected: `false`
- `isOrderComplete([])` -> Expected: `true` (Edge case: empty means nothing is pending!)

## Q8: The "Any Pending" Alert Check

**Scenario:** Admin panel me "Action Required" badge tabhi dikhega jab list mein KAM SE KAM EK order "Pending" ho.
**Requirements:** Loop chalayein. Agar ek bhi "Pending" mil jaye, turant `true` return karein. Warna `false`.
**Starter Code:**

```javascript
function hasPendingAction(orders) {
  // TODO: Check if AT LEAST ONE order is "Pending"
}
```

**Test Cases:**

- `hasPendingAction([{status: "Delivered"}, {status: "Pending"}])` -> Expected: `true`
- `hasPendingAction([{status: "Delivered"}])` -> Expected: `false`
- `hasPendingAction([])` -> Expected: `false`

## Q9: Merging Multiple Settings Objects

**Scenario:** User ke pas alag alag settings object hain array mein `[{theme: "dark"}, {notifications: true}]`. Unhe combine karke ek single config object banana hai.
**Requirements:** Ek empty base object `{}` lein. Array ke har object par `for...in` chalakar properties base object me copy karein (like `Object.assign` manually).
**Starter Code:**

```javascript
function mergeSettings(settingsArray) {
  // TODO: Combine all objects into a single master object
}
```

**Test Cases:**

- `mergeSettings([{volume: 50}, {theme: "light"}])` -> Expected: `{volume: 50, theme: "light"}`
- `mergeSettings([{a: 1}, {a: 2, b: 3}])` -> Expected: `{a: 2, b: 3}` (Later items overwrite earlier ones)
- `mergeSettings([])` -> Expected: `{}`

## Q10: Total Tax Calculator (Conditional Aggregation)

**Scenario:** Bill mein kuch items tax-free hote hain (jaise bread). Humein sirf un items par 5% tax calculate karna hai jinki `isTaxable` property `true` ho. Total tax amount nikalna hai.
**Requirements:** Loop lagakar check karein `isTaxable === true`. Agar hai toh `price * 0.05` totalTax me jodein. Return `totalTax`.
**Starter Code:**

```javascript
function calculateTotalTax(cart) {
  // TODO: Accumulate 5% tax only for taxable items
}
```

**Test Cases:**

- `calculateTotalTax([{price: 100, isTaxable: true}, {price: 50, isTaxable: false}])` -> Expected: `5`
- `calculateTotalTax([{price: 200, isTaxable: true}])` -> Expected: `10`
- `calculateTotalTax([{price: 100, isTaxable: false}])` -> Expected: `0`
