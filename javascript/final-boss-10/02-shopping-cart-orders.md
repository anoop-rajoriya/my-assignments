# Module 2: Shopping Cart & Order Processing

**Starter Story:** ZomaSwiggy Food App ke cart module pe aap assign hue ho. Yahan users items add/remove karte hain, discounts lagate hain aur final bill calculate hota hai. Aapko complex data arrays, price calculation aur loops handle karne hain taaki bill ekdum accurate bane.

## Q1: Total Cart Value

**Problem story:** User ne cart me kaafi items daal liye hain. Hume checkout button pe total amount dikhana hai.
**Problem to solve:** Array of objects (har object me `price` aur `quantity` hai) input lo. Ek loop lagao aur total cost calculate karo (price \* quantity).
**Starter code snippet:**

```javascript
const getCartTotal = (cartItems) => {
  // Your code here
};
```

**Test cases:**

1. `getCartTotal([{price: 10, quantity: 2}, {price: 5, quantity: 4}])` ➞ `40`
2. `getCartTotal([{price: 100, quantity: 1}])` ➞ `100`
3. `getCartTotal([])` ➞ `0`
4. `getCartTotal([{price: 50, quantity: 0}])` ➞ `0`

## Q2: Extract Item Names

**Problem story:** Order receipt backend me bhejni hai jisme sirf dish ke naam comma-separated string me chahiye (e.g. "Pizza, Burger").
**Problem to solve:** Cart array se sirf `name` property nikaalo aur unko comma se join karke ek single string return karo.
**Starter code snippet:**

```javascript
const getOrderSummary = (cart) => {
  // Your code here
};
```

**Test cases:**

1. `getOrderSummary([{name: "Pizza"}, {name: "Pasta"}])` ➞ `"Pizza, Pasta"`
2. `getOrderSummary([{name: "Burger"}])` ➞ `"Burger"`
3. `getOrderSummary([])` ➞ `""`
4. `getOrderSummary([{name: "Coke"}, {name: "Fries"}, {name: "Wrap"}])` ➞ `"Coke, Fries, Wrap"`

## Q3: Apply Coupon Code

**Problem story:** User ne "FLAT50" coupon apply kiya hai. Hume total bill me se 50 rupees discount dena hai, par bill 0 se kam nahi hona chahiye.
**Problem to solve:** Ek function jo current total aur discount amount le, aur new total return kare. Agar final amount negative hota hai, toh 0 return kare.
**Starter code snippet:**

```javascript
const applyDiscount = (total, discount) => {
  // Your code here
};
```

**Test cases:**

1. `applyDiscount(200, 50)` ➞ `150`
2. `applyDiscount(30, 50)` ➞ `0`
3. `applyDiscount(100, 0)` ➞ `100`
4. `applyDiscount(0, 20)` ➞ `0`

## Q4: Find Expensive Item

**Problem story:** Hume data analytics ke liye track karna hai ki cart me sabse mehenga item kaunsa hai.
**Problem to solve:** Cart array me loop chala kar wo item object find karo jiski `price` sabse zyada ho, aur us object ko return karo.
**Starter code snippet:**

```javascript
const findMostExpensive = (cart) => {
  // Your code here
};
```

**Test cases:**

1. `findMostExpensive([{price: 10}, {price: 50}, {price: 20}])` ➞ `{price: 50}`
2. `findMostExpensive([{price: 100}])` ➞ `{price: 100}`
3. `findMostExpensive([])` ➞ `null`
4. `findMostExpensive([{price: 5}, {price: 5}])` ➞ `{price: 5}` // return first match

## Q5: Remove Out of Stock Items

**Problem story:** Kuch items stock se khatam ho gaye hain. Checkout se pehle cart ko filter karke unhe hatana hoga warna error aayega.
**Problem to solve:** Ek nayi array return karo jisme wahi items hon jinka `inStock` property `true` ho.
**Starter code snippet:**

```javascript
const filterInStock = (cart) => {
  // Your code here
};
```

**Test cases:**

1. `filterInStock([{id: 1, inStock: true}, {id: 2, inStock: false}])` ➞ `[{id: 1, inStock: true}]`
2. `filterInStock([{id: 1, inStock: false}])` ➞ `[]`
3. `filterInStock([{id: 1, inStock: true}])` ➞ `[{id: 1, inStock: true}]`
4. `filterInStock([])` ➞ `[]`

## Q6: Update Item Quantity

**Problem story:** User ne '+' ya '-' button daba ke quantity change ki hai. Hume cart state array me us specific item ko dhoondh ke update karna hai.
**Problem to solve:** Array of objects, ek `itemId`, aur ek `newQuantity` input lo. Jis object ka id match kare, uski quantity update karke puri array wapas bhejo.
**Starter code snippet:**

```javascript
const updateQuantity = (cart, itemId, newQuantity) => {
  // Your code here
};
```

**Test cases:**

1. `updateQuantity([{id: 1, qty: 2}], 1, 3)` ➞ `[{id: 1, qty: 3}]`
2. `updateQuantity([{id: 2, qty: 1}], 1, 5)` ➞ `[{id: 2, qty: 1}]` // no change
3. `updateQuantity([{id: 1, qty: 2}], 1, 0)` ➞ `[{id: 1, qty: 0}]`
4. `updateQuantity([], 1, 2)` ➞ `[]`

## Q7: Count Total Items (All Quantities)

**Problem story:** Navbar pe cart icon ke upar ek chhota sa badge hota hai jo total items dikhata hai (e.g. 2 pizza + 1 coke = 3 items).
**Problem to solve:** Array me har object ki `quantity` ko sum karke total number of items nikaalo.
**Starter code snippet:**

```javascript
const countCartItems = (cart) => {
  // Your code here
};
```

**Test cases:**

1. `countCartItems([{qty: 2}, {qty: 3}])` ➞ `5`
2. `countCartItems([{qty: 1}])` ➞ `1`
3. `countCartItems([{qty: 0}, {qty: 0}])` ➞ `0`
4. `countCartItems([])` ➞ `0`

## Q8: Tax Calculation (Nested logic)

**Problem story:** Har item pe GST alag hoti hai. Food pe 5%, drinks pe 18%. Hume item ki category dekh ke total tax amount nikaalna hai.
**Problem to solve:** Cart pe loop karo. Agar item ki `type` "food" hai, toh `price * 0.05` tax add karo, agar "drink" hai toh `price * 0.18`. Total tax return karo.
**Starter code snippet:**

```javascript
const calculateTax = (cart) => {
  // Your code here
};
```

**Test cases:**

1. `calculateTax([{type: "food", price: 100}, {type: "drink", price: 100}])` ➞ `23` (5 + 18)
2. `calculateTax([{type: "food", price: 200}])` ➞ `10`
3. `calculateTax([{type: "other", price: 100}])` ➞ `0`
4. `calculateTax([])` ➞ `0`

## Q9: Add Delivery Fee conditionally

**Problem story:** Agar order 500 rupees se kam ka hai, toh 50 rupees delivery charge lagega, warna delivery free (0).
**Problem to solve:** Ek subtotal value input lo. Condition lagakar check karo aur total amount (subtotal + delivery) return karo.
**Starter code snippet:**

```javascript
const addDeliveryFee = (subtotal) => {
  // Your code here
};
```

**Test cases:**

1. `addDeliveryFee(300)` ➞ `350`
2. `addDeliveryFee(500)` ➞ `500`
3. `addDeliveryFee(600)` ➞ `600`
4. `addDeliveryFee(0)` ➞ `0` (Wait, if subtotal is 0, cart is empty. Return 0)

## Q10: Format Currency

**Problem story:** Bill show karte waqt numbers plain dikhte hain. Unhe properly Indian currency symbol ke saath dikhana zaroori hai.
**Problem to solve:** Ek number input lo aur use string me convert karke aage "₹ " lagao. Agar decimals hain, toh 2 decimal places tak limit karo.
**Starter code snippet:**

```javascript
const formatCurrency = (amount) => {
  // Your code here
};
```

**Test cases:**

1. `formatCurrency(500)` ➞ `"₹ 500.00"`
2. `formatCurrency(250.5)` ➞ `"₹ 250.50"`
3. `formatCurrency(10.123)` ➞ `"₹ 10.12"`
4. `formatCurrency(0)` ➞ `"₹ 0.00"`

## Q11: Verify All Items Available

**Problem story:** Jab user place order dabaye, ek final check lagta hai. Agar ek bhi item cart me aisa hai jiski `isAvailable` false hai, toh order block hoga.
**Problem to solve:** Loop ya condition use karke check karo ki kya SARE items available hain. Agar han toh `true`, ek bhi `false` hai toh `false`.
**Starter code snippet:**

```javascript
const checkAvailability = (cart) => {
  // Your code here
};
```

**Test cases:**

1. `checkAvailability([{isAvailable: true}, {isAvailable: true}])` ➞ `true`
2. `checkAvailability([{isAvailable: true}, {isAvailable: false}])` ➞ `false`
3. `checkAvailability([{isAvailable: false}])` ➞ `false`
4. `checkAvailability([])` ➞ `true` (Empty cart technically has no unavailable items)

## Q12: Group Cart Items by Type

**Problem story:** KOT (Kitchen Order Ticket) generate karne ke liye food items aur drink items ko alag-alag categorize karna hota hai backend me bhejne se pehle.
**Problem to solve:** Ek cart array lo aur ek object return karo jisme do arrays hon: `{ foods: [], drinks: [] }`. Items unki `type` ke hisaab se distribute karo.
**Starter code snippet:**

```javascript
const groupItems = (cart) => {
  // Your code here
};
```

**Test cases:**

1. `groupItems([{name: "A", type: "food"}, {name: "B", type: "drink"}])` ➞ `{foods: [{name: "A", type: "food"}], drinks: [{name: "B", type: "drink"}]}`
2. `groupItems([{name: "A", type: "food"}])` ➞ `{foods: [{name: "A", type: "food"}], drinks: []}`
3. `groupItems([])` ➞ `{foods: [], drinks: []}`
4. `groupItems([{name: "X", type: "unknown"}])` ➞ `{foods: [], drinks: []}` // ignore others
