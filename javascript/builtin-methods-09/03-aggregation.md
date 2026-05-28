# Module 3: Aggregation (`Array.reduce`)

**Storyline:** Aap E-commerce (Amazon/Flipkart) ka Cart and Checkout system bana rahe hain. `reduce()` bohot array items ko sikud (accumulate) kar ek single value bana deta hai.

## Q1: The Grand Total (Basic Sum)

**Scenario:** Cart array me sirf numbers (prices) aaye hain `[500, 200, 100]`. Final bill amount nikalna hai.
**Requirements:** `.reduce()` ka use karein. Accumulator me current value add karke total bill return karein.
**Starter Code:**

```javascript
function getGrandTotal(prices) {
  // TODO: Use reduce to sum all numbers
}
```

**Test Cases:**

- `getGrandTotal([500, 200, 100])` -> Expected: `800`
- `getGrandTotal([99])` -> Expected: `99`
- `getGrandTotal([0, 0, 50])` -> Expected: `50`
- `getGrandTotal([])` -> Expected: `0` (Make sure to provide initial value 0!)

## Q2: Object Array Sum (Total Quantity)

**Scenario:** Cart me items objects form me hain `[{item: "Shirt", qty: 2}]`. Pata lagana hai total kitne items kharide ja rahe hain.
**Requirements:** `.reduce()` me initial value `0` dein aur har object ka `qty` accumulator me jodein.
**Starter Code:**

```javascript
function getTotalItems(cart) {
  // TODO: Accumulate the 'qty' of all objects
}
```

**Test Cases:**

- `getTotalItems([{qty: 2}, {qty: 3}, {qty: 1}])` -> Expected: `6`
- `getTotalItems([{qty: 5}])` -> Expected: `5`
- `getTotalItems([{qty: 0}, {qty: 0}])` -> Expected: `0`
- `getTotalItems([])` -> Expected: `0`

## Q3: Finding Maximum with Reduce

**Scenario:** User puchta hai "Mera sabse mahenga (most expensive) item kaunsa hai?". Hum `.reduce()` ko comparison tool ki tarah use karenge.
**Requirements:** `.reduce()` lagayein. Agar current value accumulator se badi hai, toh current return karein, warna accumulator. Initial value `0` lein.
**Starter Code:**

```javascript
function getMaxPrice(prices) {
  // TODO: Use reduce to simulate Math.max
}
```

**Test Cases:**

- `getMaxPrice([100, 500, 250])` -> Expected: `500`
- `getMaxPrice([50, 50])` -> Expected: `50`
- `getMaxPrice([10])` -> Expected: `10`
- `getMaxPrice([])` -> Expected: `0`

## Q4: Creating a Bill Summary String

**Scenario:** WhatsApp par bill bhejna hai comma separated. `["Shirt", "Pant"]` ko reduce se `"Shirt, Pant"` banana hai ( simulating `.join()`).
**Requirements:** `.reduce()` use karein. Accumulator aur current item ke beech `", "` jodein. Be careful not to add comma before the first item.
**Starter Code:**

```javascript
function createSummary(items) {
  // TODO: Use reduce to concatenate strings properly
}
```

**Test Cases:**

- `createSummary(["Shoes", "Watch"])` -> Expected: `"Shoes, Watch"`
- `createSummary(["Bag"])` -> Expected: `"Bag"`
- `createSummary(["A", "B", "C"])` -> Expected: `"A, B, C"`
- `createSummary([])` -> Expected: `""`

## Q5: Grouping by Category (Tallying)

**Scenario:** Admin chart par dikhana hai ki kis category ke kitne items bike (sold).
**Requirements:** `.reduce()` ka use karke ek Object `{}` banayein. Agar item category object me nahi hai to 1 set karein, hai toh +1 karein.
**Starter Code:**

```javascript
function tallyCategories(categories) {
  // TODO: Return an object mapping category to count
}
```

**Test Cases:**

- `tallyCategories(["Tech", "Tech", "Food"])` -> Expected: `{ Tech: 2, Food: 1 }`
- `tallyCategories(["Books"])` -> Expected: `{ Books: 1 }`
- `tallyCategories(["A", "B", "A", "B"])` -> Expected: `{ A: 2, B: 2 }`
- `tallyCategories([])` -> Expected: `{}`

## Q6: Total Tax Calculation (Conditional Reduce)

**Scenario:** Sirf un items par 10% tax lagega jinki `isTaxable` property `true` ho.
**Requirements:** `.reduce()` ke andar `if` lagayein. Agar `isTaxable` true hai toh accumulator me `price * 0.10` add karein, else sirf accumulator aage badhayein.
**Starter Code:**

```javascript
function calculateTaxes(cart) {
  // TODO: Conditionally accumulate 10% tax
}
```

**Test Cases:**

- `calculateTaxes([{price: 200, isTaxable: true}, {price: 100, isTaxable: false}])` -> Expected: `20`
- `calculateTaxes([{price: 500, isTaxable: true}])` -> Expected: `50`
- `calculateTaxes([{price: 100, isTaxable: false}])` -> Expected: `0`
- `calculateTaxes([])` -> Expected: `0`

## Q7: Flattening a 2D Array

**Scenario:** Bundled products array ke andar array (2D) bankar aaye hain: `[["Shirt", "Tie"], ["Shoes"]]`. Ek single array chahiye.
**Requirements:** `.reduce()` ke accumulator (initial value `[]`) me `.concat()` use karke inner arrays merge karein.
**Starter Code:**

```javascript
function flattenBundles(bundles) {
  // TODO: Reduce the 2D array into a 1D array
}
```

**Test Cases:**

- `flattenBundles([["A", "B"], ["C"]])` -> Expected: `["A", "B", "C"]`
- `flattenBundles([["X"], ["Y"], ["Z"]])` -> Expected: `["X", "Y", "Z"]`
- `flattenBundles([[], ["A"]])` -> Expected: `["A"]`
- `flattenBundles([])` -> Expected: `[]`

## Q8: Chaining Reduce with Map

**Scenario:** User ke cart me quantities badh gayi hain. UI ko ek statement chahiye "Total Cost: ₹ X/-".
**Requirements:** Pehle array `.map()` karke har item ka subtotal (`price * qty`) banayein. Phir use `.reduce()` karke sum karein aur String return karein.
**Starter Code:**

```javascript
function getFinalStatement(cart) {
  // TODO: Chain map and reduce to return "Total Cost: ₹ [Sum]/-"
}
```

**Test Cases:**

- `getFinalStatement([{price: 10, qty: 2}, {price: 20, qty: 1}])` -> Expected: `"Total Cost: ₹ 40/-"`
- `getFinalStatement([{price: 100, qty: 3}])` -> Expected: `"Total Cost: ₹ 300/-"`
- `getFinalStatement([{price: 50, qty: 0}])` -> Expected: `"Total Cost: ₹ 0/-"`
- `getFinalStatement([])` -> Expected: `"Total Cost: ₹ 0/-"`
