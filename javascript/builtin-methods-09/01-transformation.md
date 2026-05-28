# Module 1: Data Transformation (`Array.map`)

**Storyline:** Aap Zomato/Swiggy ka Restaurant Dashboard bana rahe hain. Backend se raw menu data aata hai jisko UI ke hisaab se transform karna hota hai. `map()` hamesha ek naya array return karta hai of the same length!

## Q1: The Menu Extractor (Extracting Strings)

**Scenario:** UI drop-down me sirf dishes ke naam dikhane hain, pura object nahi.
**Requirements:** `.map()` ka use karke array of objects se sirf `name` property nikal kar array of strings return karein.
**Starter Code:**

```javascript
function getDishNames(menuArray) {
  // TODO: Use .map() to return an array of names
}
```

**Test Cases:**

- `getDishNames([{name: "Dosa"}, {name: "Idli"}])` -> Expected: `["Dosa", "Idli"]`
- `getDishNames([{name: "Paneer Tikka"}])` -> Expected: `["Paneer Tikka"]`
- `getDishNames([{name: "Tea"}, {name: "Coffee"}, {name: "Milk"}])` -> Expected: `["Tea", "Coffee", "Milk"]`
- `getDishNames([])` -> Expected: `[]`

## Q2: GST Applicator (Mathematical Map)

**Scenario:** Menu ki purani prices par 5% GST lagakar nayi price list UI ko bhejni hai.
**Requirements:** `.map()` use karein. Har number ko `1.05` se multiply karein.
**Starter Code:**

```javascript
function applyGST(prices) {
  // TODO: Use .map() to add 5% to each price
}
```

**Test Cases:**

- `applyGST([100, 200])` -> Expected: `[105, 210]`
- `applyGST([50])` -> Expected: `[52.5]`
- `applyGST([0, 1000])` -> Expected: `[0, 1050]`
- `applyGST([])` -> Expected: `[]`

## Q3: The Veg/Non-Veg Tagger

**Scenario:** Dish object me `isVeg` boolean aata hai. UI par "🟢 Veg" ya "🔴 Non-Veg" text dikhana hai.
**Requirements:** `.map()` ke andar ternary operator lagayein aur updated objects ka array return karein jisme nayi key `tag` ho.
**Starter Code:**

```javascript
function addFoodTags(menu) {
  // TODO: Return new objects with the 'tag' property added
}
```

**Test Cases:**

- `addFoodTags([{item: "Dal", isVeg: true}])` -> Expected: `[{item: "Dal", isVeg: true, tag: "🟢 Veg"}]`
- `addFoodTags([{item: "Chicken", isVeg: false}])` -> Expected: `[{item: "Chicken", isVeg: false, tag: "🔴 Non-Veg"}]`
- `addFoodTags([{item: "Roti", isVeg: true}, {item: "Fish", isVeg: false}])` -> Expected: `[{item: "Roti", isVeg: true, tag: "🟢 Veg"}, {item: "Fish", isVeg: false, tag: "🔴 Non-Veg"}]`
- `addFoodTags([])` -> Expected: `[]`

## Q4: Formatted Pricing for UI

**Scenario:** App me price ko string format `"₹ 150/-"` me dikhana hai.
**Requirements:** `.map()` aur Template Literals (``) ka use karke numbers ke array ko formatted strings ke array me badlein.
**Starter Code:**

```javascript
function formatPrices(prices) {
  // TODO: Use .map() to format elements as "₹ [price]/-"
}
```

**Test Cases:**

- `formatPrices([150, 200])` -> Expected: `["₹ 150/-", "₹ 200/-"]`
- `formatPrices([99])` -> Expected: `["₹ 99/-"]`
- `formatPrices([0, 5])` -> Expected: `["₹ 0/-", "₹ 5/-"]`
- `formatPrices([])` -> Expected: `[]`

## Q5: Bestseller Appender (Index Usage)

**Scenario:** `map(item, index)` me doosra argument index hota hai. Menu array me pehli 2 dishes humesha bestseller hoti hain.
**Requirements:** Agar index `0` ya `1` hai, toh name ke aage `" (Bestseller)"` jod dein, warna same naam return karein.
**Starter Code:**

```javascript
function markBestsellers(dishNames) {
  // TODO: Append "(Bestseller)" to the first two items
}
```

**Test Cases:**

- `markBestsellers(["Dosa", "Idli", "Vada"])` -> Expected: `["Dosa (Bestseller)", "Idli (Bestseller)", "Vada"]`
- `markBestsellers(["Tea"])` -> Expected: `["Tea (Bestseller)"]`
- `markBestsellers(["A", "B", "C", "D"])` -> Expected: `["A (Bestseller)", "B (Bestseller)", "C", "D"]`
- `markBestsellers([])` -> Expected: `[]`

## Q6: String to ID Converter

**Scenario:** User naye menu items add kar raha hai (string array). Backend ko unhe object list banakar bhejna hai.
**Requirements:** Array of strings ko `.map()` karke array of objects banayein format: `{ id: index + 1, name: "Dish" }`.
**Starter Code:**

```javascript
function convertToObjects(dishNames) {
  // TODO: Use item and index in .map()
}
```

**Test Cases:**

- `convertToObjects(["Dosa", "Idli"])` -> Expected: `[{id: 1, name: "Dosa"}, {id: 2, name: "Idli"}]`
- `convertToObjects(["Tea"])` -> Expected: `[{id: 1, name: "Tea"}]`
- `convertToObjects(["A", "B", "C"])` -> Expected: `[{id: 1, name: "A"}, {id: 2, name: "B"}, {id: 3, name: "C"}]`
- `convertToObjects([])` -> Expected: `[]`

## Q7: Nested Rating Extractor

**Scenario:** API response bohot nested hai: `[{dish: "Tea", details: { rating: 4.5 }}]`.
**Requirements:** `.map()` lagakar sirf exact rating number nikal kar array me dalein.
**Starter Code:**

```javascript
function extractRatings(menuData) {
  // TODO: Safely map out the inner rating value
}
```

**Test Cases:**

- `extractRatings([{details: {rating: 4}}, {details: {rating: 5}}])` -> Expected: `[4, 5]`
- `extractRatings([{details: {rating: 3.5}}])` -> Expected: `[3.5]`
- `extractRatings([{details: {rating: 1}}, {details: {rating: 2}}, {details: {rating: 3}}])` -> Expected: `[1, 2, 3]`
- `extractRatings([])` -> Expected: `[]`

## Q8: URL Slug Generator

**Scenario:** Swiggy har dish ke liye alag web page banata hai. "Paneer Tikka" ko "paneer-tikka" slug me badalna hai.
**Requirements:** Array of names par `.map()` chalayein, har item ko `.toLowerCase()` karein aur `.split(" ").join("-")` karein.
**Starter Code:**

```javascript
function generateSlugs(names) {
  // TODO: Convert spaces to hyphens and lowercase everything
}
```

**Test Cases:**

- `generateSlugs(["Shahi Paneer", "Dal Makhani"])` -> Expected: `["shahi-paneer", "dal-makhani"]`
- `generateSlugs(["Tea"])` -> Expected: `["tea"]`
- `generateSlugs(["A B C", "X Y Z"])` -> Expected: `["a-b-c", "x-y-z"]`
- `generateSlugs([])` -> Expected: `[]`
