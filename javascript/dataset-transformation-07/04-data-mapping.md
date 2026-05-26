# Module 4: Relational Data Mapping (Basic Joins)

## Q1: The Basic Join (Merging User & Address)

**Scenario:** API ne do arrays diye. Ek me Users hain, ek me unki IDs ke saath Address. Inhe combine karke ek array banana hai.
**Requirements:** Nested loop lagayein. User ID se Address ID match karein aur address key add karke naya array return karein.
**Starter Code:**

```javascript
function joinUserAddress(users, addresses) {
  // TODO: Merge address into user object based on matching ID
}
```

**Test Cases:**

- `joinUserAddress([{id: 1, name: "A"}], [{userId: 1, city: "Delhi"}])` -> Expected: `[{id: 1, name: "A", address: {userId: 1, city: "Delhi"}}]`
- `joinUserAddress([{id: 2, name: "B"}], [])` -> Expected: `[{id: 2, name: "B"}]`
- `joinUserAddress([], [{userId: 1, city: "Pune"}])` -> Expected: `[]`

## Q2: Replacing IDs with Names (Category Lookup)

**Scenario:** Product object me `categoryId: 101` aata hai. Frontend ko ID nahi, category ka string naam chahiye jo doosre object (Lookup table) me hai.
**Requirements:** Loop chalayein. Product ki `categoryId` ko dictionary object se look up karein aur usko `categoryName` se replace kar dein (delete categoryId).
**Starter Code:**

```javascript
function mapCategoryNames(products, categoryDict) {
  // categoryDict is like { 101: "Electronics", 102: "Books" }
  // TODO: Replace categoryId with categoryName
}
```

**Test Cases:**

- `mapCategoryNames([{name: "TV", categoryId: 101}], {101: "Electronics"})` -> Expected: `[{name: "TV", categoryName: "Electronics"}]`
- `mapCategoryNames([{name: "Novel", categoryId: 102}], {102: "Books"})` -> Expected: `[{name: "Novel", categoryName: "Books"}]`
- `mapCategoryNames([], {101: "Tech"})` -> Expected: `[]`

## Q3: Syncing Inventories (Updating Old with New)

**Scenario:** Dukan par subah ka stock (array) aur shaam ka delivery stock (array) aaya hai. Dono ko milana hai. Agar item purane me hai toh quantity add hogi, naya hai toh list me jud jayega.
**Requirements:** Pehle purane array ko object map mein badle (item id ke basis pe), usme naya add karein, fir object ki values nikal kar wapas array return karein.
**Starter Code:**

```javascript
function syncStock(oldStock, newStock) {
  // TODO: Merge stocks combining quantities for matching IDs
}
```

**Test Cases:**

- `syncStock([{id: 1, qty: 10}], [{id: 1, qty: 5}])` -> Expected: `[{id: 1, qty: 15}]`
- `syncStock([{id: 1, qty: 10}], [{id: 2, qty: 5}])` -> Expected: `[{id: 1, qty: 10}, {id: 2, qty: 5}]`
- `syncStock([], [{id: 1, qty: 2}])` -> Expected: `[{id: 1, qty: 2}]`

## Q4: Applying Specific Coupon Config

**Scenario:** User ne coupon `DIWALI` daala hai. Humare paas active coupons ka ek array of objects hai. Dhoondna hai ki coupon valid hai ya nahi aur kitna discount hai.
**Requirements:** Loop se search karein. Agar match ho toh `{ isValid: true, discount: X }` return karein. Na mile to `{ isValid: false, discount: 0 }`.
**Starter Code:**

```javascript
function applyCoupon(inputCode, availableCoupons) {
  // availableCoupons = [{code: "HOLI", discount: 10}, {code: "DIWALI", discount: 20}]
  // TODO: Find the matching coupon and return status
}
```

**Test Cases:**

- `applyCoupon("DIWALI", [{code: "DIWALI", discount: 20}])` -> Expected: `{ isValid: true, discount: 20 }`
- `applyCoupon("NEW", [{code: "OLD", discount: 10}])` -> Expected: `{ isValid: false, discount: 0 }`
- `applyCoupon("TEST", [])` -> Expected: `{ isValid: false, discount: 0 }`

## Q5: Delivery Boy Assignment (Round Robin)

**Scenario:** 3 delivery boys hain `["Ravi", "Aman", "Suresh"]` aur 5 orders hain array mein. Unhe ek ke baad ek assign karna hai. (Order 1 -> Ravi, Order 2 -> Aman, Order 3 -> Suresh, Order 4 -> Ravi...).
**Requirements:** Orders pe loop lagayein. Index number ko delivery boys ki array ki length se modulo (`%`) karein aur assignee set karein.
**Starter Code:**

```javascript
function assignDeliveries(orders, boysArray) {
  // TODO: Distribute orders evenly using modulo operator
}
```

**Test Cases:**

- `assignDeliveries([{id: 1}, {id: 2}, {id: 3}], ["Ravi", "Aman"])` -> Expected: `[{id: 1, boy: "Ravi"}, {id: 2, boy: "Aman"}, {id: 3, boy: "Ravi"}]`
- `assignDeliveries([{id: 1}], ["Suresh"])` -> Expected: `[{id: 1, boy: "Suresh"}]`
- `assignDeliveries([], ["Aman"])` -> Expected: `[]`

## Q6: Cross-Referencing Banned Users

**Scenario:** Comment list aayi hai. Kuch users banned ho chuke hain jinki IDs ek array `[101, 105]` mein hain. Banned users ke comments filter karne hain.
**Requirements:** Loop lagakar comments check karein. Agar comment ka `userId` banned array mein exist karta hai, usko skip karein.
**Starter Code:**

```javascript
function filterBannedComments(comments, bannedIds) {
  // TODO: Use includes() in loop to skip banned IDs
}
```

**Test Cases:**

- `filterBannedComments([{userId: 101, text: "A"}, {userId: 102, text: "B"}], [101])` -> Expected: `[{userId: 102, text: "B"}]`
- `filterBannedComments([{userId: 5, text: "Hi"}], [1, 2, 3])` -> Expected: `[{userId: 5, text: "Hi"}]`
- `filterBannedComments([], [101])` -> Expected: `[]`

## Q7: Appending Reviews to Products

**Scenario:** Ek array products ka hai, ek array sabhi mixed reviews ka hai. Har product object mein uske relevant reviews array form mein judne chahiye.
**Requirements:** Pehle products par loop, fir andar reviews par loop. ID match karke review ko product ke naye property `reviews = []` mein push karein.
**Starter Code:**

```javascript
function populateReviews(products, allReviews) {
  // TODO: Attach matching reviews to the product object
}
```

**Test Cases:**

- `populateReviews([{id: 1, name: "Pen"}], [{productId: 1, text: "Good"}, {productId: 2, text: "Bad"}])` -> Expected: `[{id: 1, name: "Pen", reviews: [{productId: 1, text: "Good"}]}]`
- `populateReviews([{id: 2, name: "Book"}], [])` -> Expected: `[{id: 2, name: "Book", reviews: []}]`
- `populateReviews([], [{productId: 1, text: "OK"}])` -> Expected: `[]`

## Q8: The Price Drop Alert (Diffing)

**Scenario:** Aapke pas purani price list aur nayi price list arrays mein hai. Pata lagana hai kin products ka price pehle se sasta hua hai (Drop alert).
**Requirements:** Naye array pe loop lagakar purane array mein same ID dhundein. Agar new price < old price hai, toh usko `alerts` array mein daalein.
**Starter Code:**

```javascript
function getPriceDrops(oldPrices, newPrices) {
  // TODO: Compare arrays by ID and return dropped items
}
```

**Test Cases:**

- `getPriceDrops([{id: 1, price: 100}], [{id: 1, price: 80}])` -> Expected: `[{id: 1, price: 80}]`
- `getPriceDrops([{id: 2, price: 50}], [{id: 2, price: 60}])` -> Expected: `[]`
- `getPriceDrops([], [])` -> Expected: `[]`

## Q9: Batch Updating Properties

**Scenario:** Admin ne bulk edit kiya hai. `{id: 1, status: "Shipped"}`. Ek `updates` array of objects bheja gaya hai. Original orders modify karne hain.
**Requirements:** Original array par loop chalayein, updates array mein ID dhundein. Agar update mile, toh properties override karein.
**Starter Code:**

```javascript
function applyUpdates(orders, updates) {
  // TODO: Match ID and update the original order
}
```

**Test Cases:**

- `applyUpdates([{id: 1, status: "Pending"}], [{id: 1, status: "Shipped"}])` -> Expected: `[{id: 1, status: "Shipped"}]`
- `applyUpdates([{id: 1, name: "A"}], [{id: 2, name: "B"}])` -> Expected: `[{id: 1, name: "A"}]`
- `applyUpdates([], [{id: 1, status: "Done"}])` -> Expected: `[]`

## Q10: Joining Payments with Orders

**Scenario:** Order summary page pe `Order Data` aur `Payment Data` ko Transaction ID par map karke dikhana hai. Dono arrays hain.
**Requirements:** Nested loop. `order.txnId === payment.txnId`. Matching hone par dono ki data mila kar ek consolidated array return karein.
**Starter Code:**

```javascript
function consolidateLedger(orders, payments) {
  // TODO: Join data where txnIds match
}
```

**Test Cases:**

- `consolidateLedger([{id: 1, txnId: "TX12"}], [{txnId: "TX12", mode: "UPI"}])` -> Expected: `[{id: 1, txnId: "TX12", mode: "UPI"}]`
- `consolidateLedger([{id: 1, txnId: "TX99"}], [{txnId: "TX88", mode: "Cash"}])` -> Expected: `[]` (If it behaves like an INNER JOIN, return only matches. Let's assume inner join).
- `consolidateLedger([], [])` -> Expected: `[]`
