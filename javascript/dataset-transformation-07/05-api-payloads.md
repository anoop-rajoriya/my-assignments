# Module 5: Complex Real-World API Payloads (Master Level)

## Q1: Extracting from Deep API Wrappers

**Scenario:** Ek API data is form mein bhejti hai: `{ success: true, payload: { users: [{name: "A"}] } }`. Humein directly users ka array nikalna hai. Par bich mein koi object missing hua toh app crash (TypeError) hogi.
**Requirements:** Safely check karein `response`, `response.payload`, aur `response.payload.users`. Agar sab valid hain to array return karein, else `[]`.
**Starter Code:**

```javascript
function extractUsersSafely(apiResponse) {
  // TODO: Safely navigate deeply nested properties
}
```

**Test Cases:**

- `extractUsersSafely({payload: {users: [{name: "Raj"}]}})` -> Expected: `[{name: "Raj"}]`
- `extractUsersSafely({payload: null})` -> Expected: `[]`
- `extractUsersSafely({})` -> Expected: `[]`

## Q2: Creating a Lookup Dictionary (Array to Map)

**Scenario:** Bar-bar array search `O(n)` time leta hai. Array ko Object Map (Dictionary) mein badalna hai jisme Keys IDs hongi, fast lookup ke liye.
**Requirements:** Loop array. Har item ko object mein uski id property ke under set karein.
**Starter Code:**

```javascript
function arrayToMap(itemsArray) {
  // TODO: Convert [{id: 101, name: "A"}] to {101: {id: 101, name: "A"}}
}
```

**Test Cases:**

- `arrayToMap([{id: 5, name: "Pen"}])` -> Expected: `{ 5: {id: 5, name: "Pen"} }`
- `arrayToMap([{id: 10, name: "Book"}, {id: 11, name: "Bag"}])` -> Expected: `{ 10: {id: 10, name: "Book"}, 11: {id: 11, name: "Bag"} }`
- `arrayToMap([])` -> Expected: `{}`

## Q3: Unrolling the Dictionary (Map to Array)

**Scenario:** Humne backend me Object Map banaya tha (upar wale question ki tarah). Par React UI mein `.map()` (in jsx) chalane ke liye isko wapas Array banana padega.
**Requirements:** `for...in` chalakar Object ki saari values ko ek array mein push karke return karein.
**Starter Code:**

```javascript
function mapToArray(itemsMap) {
  // TODO: Convert Object map back into an array
}
```

**Test Cases:**

- `mapToArray({ 5: {id: 5, name: "Pen"} })` -> Expected: `[{id: 5, name: "Pen"}]`
- `mapToArray({})` -> Expected: `[]`
- `mapToArray({ 1: {a: 1}, 2: {b: 2} })` -> Expected: `[{a: 1}, {b: 2}]`

## Q4: Deep Flattening Categories (Sub-menus)

**Scenario:** Navbar menu mein `categories` hain aur unke andar `subCategories` ka array hai. Search bar ke liye humein sabhi names ek single 1D string array mein chahiye.
**Requirements:** Outer array par loop, fir andar `subCategories` par loop. Saare naam string form mein extract karein.
**Starter Code:**

```javascript
function extractAllMenuNames(menuData) {
  // menuData = [{name: "Men", subCategories: [{name: "Shirts"}]}]
  // TODO: Extract names from both levels into one flat array
}
```

**Test Cases:**

- `extractAllMenuNames([{name: "Men", subCategories: [{name: "Shirts"}]}])` -> Expected: `["Men", "Shirts"]`
- `extractAllMenuNames([{name: "Electronics", subCategories: []}])` -> Expected: `["Electronics"]`
- `extractAllMenuNames([])` -> Expected: `[]`

## Q5: Simultaneous Filter and Map (Performance Optimization)

**Scenario:** Ek array se active users nikalne hain (filter), AUR unka sirf naam chahiye (map). Do alag loop lagane se app slow hogi. Humein ek hi loop mein karna hai.
**Requirements:** Single loop. Condition check `isActive === true`. Agar yes, toh result array mein directly sirf `name` push karein.
**Starter Code:**

```javascript
function getActiveUserNames(users) {
  // TODO: Filter and map in a single loop
}
```

**Test Cases:**

- `getActiveUserNames([{name: "Raj", isActive: true}, {name: "Aman", isActive: false}])` -> Expected: `["Raj"]`
- `getActiveUserNames([{name: "Neha", isActive: false}])` -> Expected: `[]`
- `getActiveUserNames([])` -> Expected: `[]`

## Q6: Paginated Data Extraction

**Scenario:** API ne data array mein nahi diya. Object mein `data.page1`, `data.page2` keys banakar diya hai. Humein saari pages ka data ek master array mein dalna hai.
**Requirements:** `for...in` use karke keys (`page1`, `page2`) padhein, har array ko master array mein concat/push karein.
**Starter Code:**

```javascript
function extractPaginatedData(apiData) {
  // apiData = { page1: [1, 2], page2: [3, 4] }
  // TODO: Combine all page arrays into one
}
```

**Test Cases:**

- `extractPaginatedData({ page1: ["A", "B"], page2: ["C"] })` -> Expected: `["A", "B", "C"]`
- `extractPaginatedData({ page1: [100] })` -> Expected: `[100]`
- `extractPaginatedData({})` -> Expected: `[]`

## Q7: Grand Total with Nested Item Taxes

**Scenario:** Cart array me objects hain. Har object mein `price` hai, aur ek `taxes` array hai `[{type: "GST", amt: 10}]`. Grand total = saare prices + saare ander ke taxes.
**Requirements:** Outer loop over cart. Inner loop over taxes array of that item. Sum everything manually.
**Starter Code:**

```javascript
function calculateGrandTotal(cart) {
  // TODO: Sum up item prices and their nested taxes
}
```

**Test Cases:**

- `calculateGrandTotal([{price: 100, taxes: [{amt: 10}, {amt: 5}]}])` -> Expected: `115`
- `calculateGrandTotal([{price: 200, taxes: []}])` -> Expected: `200`
- `calculateGrandTotal([])` -> Expected: `0`

## Q8: The Flat API to Hierarchical Tree (Parent-Child)

**Scenario:** File explorer me folders API se flat array me aate hain: `[{id: 1, name: "Root", parentId: null}, {id: 2, name: "Docs", parentId: 1}]`. Inhe nested object banana hai.
**Requirements:** Loop over array. Agar `parentId` null hai to wo root hai. Agar parentId hai to us parent object me `children` array banakar push karein. (Basic 2 level nesting is enough for this logic, assume parent is always before child in array for simplicity).
**Starter Code:**

```javascript
function buildFolderTree(flatFolders) {
  // TODO: Assign children to their respective parents
}
```

**Test Cases:**

- `buildFolderTree([{id: 1, name: "Root", parentId: null}, {id: 2, name: "Sub", parentId: 1}])` -> Expected: `[{id: 1, name: "Root", parentId: null, children: [{id: 2, name: "Sub", parentId: 1}]}]`
- `buildFolderTree([{id: 5, name: "Base", parentId: null}])` -> Expected: `[{id: 5, name: "Base", parentId: null}]`
- `buildFolderTree([])` -> Expected: `[]`

## Q9: Dynamic Table Row Generator (Data Plucking)

**Scenario:** API ne data object bheja `[{a: 1, b: 2, c: 3}]`. UI par table columns dynamically aayenge `["a", "c"]`. Humein array me se sirf wo columns extract karke UI ko dene hain.
**Requirements:** Loop over array. Har item par loop over `columns` array. Naya object banayein jisme sirf maange gaye columns hon.
**Starter Code:**

```javascript
function pluckColumns(dataList, columnsReq) {
  // TODO: Extract only requested properties for the table rows
}
```

**Test Cases:**

- `pluckColumns([{name: "Raj", age: 25, city: "Delhi"}], ["name", "city"])` -> Expected: `[{name: "Raj", city: "Delhi"}]`
- `pluckColumns([{id: 1, price: 10}], ["id"])` -> Expected: `[{id: 1}]`
- `pluckColumns([], ["name"])` -> Expected: `[]`

## Q10: Complex Search Query Matcher (Multi-field filtering)

**Scenario:** Amazon search bar me user type karta hai "Shirt". Humein search karna hai title mein, description mein, YA brand name mein (3 alag fields). Aur result wahi hone chahiye jo `inStock` bhi hon.
**Requirements:** Loop lagayein. String check karein `includes(query)` in `title`, `desc`, or `brand`. Sath me `inStock` true hona lazmi hai. (Case insensitive search banayein `toLowerCase` se).
**Starter Code:**

```javascript
function searchProducts(products, query) {
  // TODO: Match query against multiple text fields, keeping only inStock items
}
```

**Test Cases:**

- `searchProducts([{title: "Red Shirt", brand: "X", inStock: true}], "shirt")` -> Expected: `[{title: "Red Shirt", brand: "X", inStock: true}]`
- `searchProducts([{desc: "Cotton shirt", inStock: false}], "shirt")` -> Expected: `[]`
- `searchProducts([{title: "Pant", brand: "Polo", inStock: true}], "polo")` -> Expected: `[{title: "Pant", brand: "Polo", inStock: true}]`
