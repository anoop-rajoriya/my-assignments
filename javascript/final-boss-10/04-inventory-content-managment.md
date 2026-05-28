# Module 4: Inventory & Content Management

**Starter Story:** B2B Warehouse management system 'StockPilot' pe apka swagat hai. Yahan daily thousands of products add, update aur categorize hote hain. Aapko bulk data arrays aur complex mutations handle karne hain, jisme filtering aur aggregation loops ka major use hoga. Errors allow nahi hain kyunki inventory mismatches se business ko huge losses ho sakte hain.

## Q1: Filter Low Stock Items

**Problem story:** Warehouse manager ko un sabhi items ki list dekhni hai jinki quantity ek danger threshold (jaise 10 units) se niche aa gayi hai.
**Problem to solve:** Array of inventory objects aur ek `threshold` number lo. Jo items us threshold se kam quantity rakhte hain unki nayi array return karo.
**Starter code snippet:**

```javascript
const getLowStockItems = (inventory, threshold) => {
  // Your code here
};
```

**Test cases:**

1. `getLowStockItems([{id: 1, qty: 5}, {id: 2, qty: 15}], 10)` ➞ `[{id: 1, qty: 5}]`
2. `getLowStockItems([{id: 1, qty: 20}], 10)` ➞ `[]`
3. `getLowStockItems([], 5)` ➞ `[]`
4. `getLowStockItems([{id: 1, qty: 1}], 2)` ➞ `[{id: 1, qty: 1}]`

## Q2: Extract Product SKUs

**Problem story:** Barcode generator script ko backend se sirf SKUs (Stock Keeping Units) ka array chahiye, pura product data nahi.
**Problem to solve:** Array of objects se loop chalakar sirf `sku` strings ka ek naya flat array banao.
**Starter code snippet:**

```javascript
const extractSKUs = (products) => {
  // Your code here
};
```

**Test cases:**

1. `extractSKUs([{sku: "A123", name: "Pen"}, {sku: "B456", name: "Book"}])` ➞ `["A123", "B456"]`
2. `extractSKUs([{sku: "X999"}])` ➞ `["X999"]`
3. `extractSKUs([])` ➞ `[]`
4. `extractSKUs([{name: "NoSKU"}])` ➞ `[undefined]` // Or handle missing if you prefer

## Q3: Update Product Price Bulk

**Problem story:** Festival season aaraha hai aur category "Electronics" ke sabhi items par 10% price increase karni hai system mein.
**Problem to solve:** Inventory array lo. Agar item ki `category` "Electronics" hai, toh uski `price` ko 1.1 se multiply karke update karo (modify in place ya new array).
**Starter code snippet:**

```javascript
const hikeElectronicsPrice = (inventory) => {
  // Your code here
};
```

**Test cases:**

1. `hikeElectronicsPrice([{category: "Electronics", price: 100}, {category: "Toys", price: 50}])` ➞ `[{category: "Electronics", price: 110}, {category: "Toys", price: 50}]`
2. `hikeElectronicsPrice([{category: "Toys", price: 10}])` ➞ `[{category: "Toys", price: 10}]`
3. `hikeElectronicsPrice([])` ➞ `[]`
4. `hikeElectronicsPrice([{category: "Electronics", price: 200}])` ➞ `[{category: "Electronics", price: 220}]`

## Q4: Search Product by Name

**Problem story:** Search bar me user keyword type karta hai. Hume locally array me case-insensitive search lagana hai taaki matching items dikhein.
**Problem to solve:** Array of objects aur ek keyword string lo. Jin objects ke `name` me wo keyword (kisi bhi case me) aata hai, unhe filter karke return karo.
**Starter code snippet:**

```javascript
const searchProducts = (products, keyword) => {
  // Your code here
};
```

**Test cases:**

1. `searchProducts([{name: "Red Apple"}, {name: "Banana"}], "apple")` ➞ `[{name: "Red Apple"}]`
2. `searchProducts([{name: "Phone"}, {name: "Tablet"}], "LAPTOP")` ➞ `[]`
3. `searchProducts([], "a")` ➞ `[]`
4. `searchProducts([{name: "Bat"}, {name: "Batman"}], "bat")` ➞ `[{name: "Bat"}, {name: "Batman"}]`

## Q5: Total Inventory Value

**Problem story:** Auditor ko warehouse me padhe total maal (goods) ki rupee value nikalni hai (quantity \* price of every item).
**Problem to solve:** Loop chala kar total inventory ki cumulative cost calculate karo aur ek single number return karo.
**Starter code snippet:**

```javascript
const calculateTotalInventoryValue = (inventory) => {
  // Your code here
};
```

**Test cases:**

1. `calculateTotalInventoryValue([{qty: 10, price: 5}, {qty: 2, price: 100}])` ➞ `250`
2. `calculateTotalInventoryValue([{qty: 1, price: 50}])` ➞ `50`
3. `calculateTotalInventoryValue([])` ➞ `0`
4. `calculateTotalInventoryValue([{qty: 0, price: 10}])` ➞ `0`

## Q6: Mark Item as Defective

**Problem story:** QA team ne scanning me ek product ko toota hua paaya. Hume array me us specific ID wale item ko update karke `isDefective: true` set karna hai.
**Problem to solve:** Array aur ek target ID lo. Object find karo, update karo, aur modified array return karo.
**Starter code snippet:**

```javascript
const markDefective = (inventory, idToMark) => {
  // Your code here
};
```

**Test cases:**

1. `markDefective([{id: 1}, {id: 2}], 2)` ➞ `[{id: 1}, {id: 2, isDefective: true}]`
2. `markDefective([{id: 1}], 3)` ➞ `[{id: 1}]` // no change
3. `markDefective([], 1)` ➞ `[]`
4. `markDefective([{id: 5, isDefective: false}], 5)` ➞ `[{id: 5, isDefective: true}]`

## Q7: Sort Items by Quantity (Mock)

**Problem story:** Dashboard par items dikhane hain sorted by sabse kam quantity pehle, taaki restocking ka order diya ja sake.
**Problem to solve:** Array of objects ko `quantity` ke ascending order me sort karo bina array `.sort()` function ko overwrite kiye simple array methods se (ya bubble sort loop se agar allowed ho, par `.sort` chalega).
**Starter code snippet:**

```javascript
const sortByQuantityAsc = (inventory) => {
  // Your code here
};
```

**Test cases:**

1. `sortByQuantityAsc([{qty: 50}, {qty: 10}])` ➞ `[{qty: 10}, {qty: 50}]`
2. `sortByQuantityAsc([{qty: 5}, {qty: 5}])` ➞ `[{qty: 5}, {qty: 5}]`
3. `sortByQuantityAsc([])` ➞ `[]`
4. `sortByQuantityAsc([{qty: 2}, {qty: 1}, {qty: 3}])` ➞ `[{qty: 1}, {qty: 2}, {qty: 3}]`

## Q8: Find Unique Categories

**Problem story:** Sidebar filter menu me dikhane ke liye inventory me maujud saari alag-alag categories (unique names) nikalni hain.
**Problem to solve:** Array se loop chalakar sirf unique `category` strings ko ek nayi array me jama (collect) karo.
**Starter code snippet:**

```javascript
const getUniqueCategories = (inventory) => {
  // Your code here
};
```

**Test cases:**

1. `getUniqueCategories([{category: "A"}, {category: "B"}, {category: "A"}])` ➞ `["A", "B"]`
2. `getUniqueCategories([{category: "X"}])` ➞ `["X"]`
3. `getUniqueCategories([])` ➞ `[]`
4. `getUniqueCategories([{category: "A"}, {category: "A"}, {category: "A"}])` ➞ `["A"]`

## Q9: Apply Restock Caps

**Problem story:** Warehouse space limited hai. Agar kisi item ki quantity 100 se upar hai, toh usko 100 pe cap kardo taaki data realistic rahe system error se bachne ke liye.
**Problem to solve:** Loop run karo, jahan `quantity > 100`, usko `100` set kardo aur wapas array return karo.
**Starter code snippet:**

```javascript
const capInventoryQuantities = (inventory) => {
  // Your code here
};
```

**Test cases:**

1. `capInventoryQuantities([{qty: 150}, {qty: 50}])` ➞ `[{qty: 100}, {qty: 50}]`
2. `capInventoryQuantities([{qty: 90}])` ➞ `[{qty: 90}]`
3. `capInventoryQuantities([])` ➞ `[]`
4. `capInventoryQuantities([{qty: 100}, {qty: 101}])` ➞ `[{qty: 100}, {qty: 100}]`

## Q10: Check if Product Exists

**Problem story:** Naya item add karne se pehle frontend check karega ki wo same ID se already list me toh nahi hai, taaki duplicates prevent hon.
**Problem to solve:** Array aur ID input lo. Agar ID array of objects me milti hai toh `true` return karo, nahi toh `false`.
**Starter code snippet:**

```javascript
const productExists = (inventory, id) => {
  // Your code here
};
```

**Test cases:**

1. `productExists([{id: "p1"}, {id: "p2"}], "p2")` ➞ `true`
2. `productExists([{id: "p1"}], "p3")` ➞ `false`
3. `productExists([], "p1")` ➞ `false`
4. `productExists([{id: 1}], 1)` ➞ `true`

## Q11: Add Custom Tag

**Problem story:** Sale event par specific items pe ek string tag "SALE2026" lagana hai.
**Problem to solve:** Array me har object ke andar ek nayi property `tag` add karo jiska value "SALE2026" ho.
**Starter code snippet:**

```javascript
const addSaleTag = (inventory) => {
  // Your code here
};
```

**Test cases:**

1. `addSaleTag([{name: "A"}])` ➞ `[{name: "A", tag: "SALE2026"}]`
2. `addSaleTag([{id: 1, tag: "OLD"}])` ➞ `[{id: 1, tag: "SALE2026"}]` // Overwrite existing
3. `addSaleTag([])` ➞ `[]`
4. `addSaleTag([{a: 1}, {b: 2}])` ➞ `[{a: 1, tag: "SALE2026"}, {b: 2, tag: "SALE2026"}]`

## Q12: Split into Batches (Pagination Mock)

**Problem story:** API response me 100 items aaye hain par screen par ek baar me max 5 items hi dikhane hain loop lagakar arrays ko todna hoga.
**Problem to solve:** Ek flat array aur ek size number (e.g. 2) lo, aur arrays of arrays banao (Chunks).
**Starter code snippet:**

```javascript
const chunkInventory = (inventory, size) => {
  // Your code here
};
```

**Test cases:**

1. `chunkInventory([1,2,3,4], 2)` ➞ `[[1,2], [3,4]]`
2. `chunkInventory([1,2,3], 2)` ➞ `[[1,2], [3]]`
3. `chunkInventory([1], 5)` ➞ `[[1]]`
4. `chunkInventory([], 2)` ➞ `[]`
