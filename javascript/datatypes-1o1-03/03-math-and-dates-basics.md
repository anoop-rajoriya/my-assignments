# Module 3: Basic Math & Date Objects

## Q1: The Fair Rounding (Math.round)

**Scenario:** App par kisi bhi product ki final price decimal mein nahi honi chahiye. Agar .5 ya usse zyada hai toh aage badha do, warna piche.

**Requirements:** `Math.round()` built-in method ka use karke decimal amount round off karein.

**Starter Code:**

```javascript
function roundPrice(price) {
  // TODO: Return rounded price
}
```

**Test Cases:**

- `roundPrice(99.6)` -> Expected: `100`
- `roundPrice(99.4)` -> Expected: `99`

## Q2: Pagination Math (Math.ceil)

**Scenario:** Aapke paas 21 items hain, aur ek page par 10 items aate hain. Aapko 3 pages lagenge (21/10 = 2.1). Ceiling humesha upar wali value leti hai.

**Requirements:** `Math.ceil()` ka use karke number ko upper integer par round karein.

**Starter Code:**

```javascript
function getRequiredPages(exactPages) {
  // TODO: Return the ceiling value
}
```

**Test Cases:**

- `getRequiredPages(2.1)` -> Expected: `3`
- `getRequiredPages(5.8)` -> Expected: `6`

## Q3: Dropping the Decimals (Math.floor)

**Scenario:** Ek game mein points hamesha kam wali side round off hote hain. (Example: 4.9 hai toh 4 hi milega).

**Requirements:** `Math.floor()` ka use karke lower integer value return karein.

**Starter Code:**

```javascript
function getGameScore(rawScore) {
  // TODO: Return the floored score
}
```

**Test Cases:**

- `getGameScore(4.9)` -> Expected: `4`
- `getGameScore(10.1)` -> Expected: `10`

## Q4: The Highest Bid (Math.max)

**Scenario:** Ek auction app mein teen (3) logon ne bid lagayi hai. Humein pata karna hai ki sabse badi bid kiski hai.

**Requirements:** `Math.max()` method me teeno numbers pass karein aur sabse bada number return karein.

**Starter Code:**

```javascript
function getHighestBid(bid1, bid2, bid3) {
  // TODO: Return the maximum of the three numbers
}
```

**Test Cases:**

- `getHighestBid(100, 500, 250)` -> Expected: `500`

## Q5: Finding the Cheapest (Math.min)

**Scenario:** User 3 alag-alag stores par ek hi item ka daam (price) compare kar raha hai.

**Requirements:** `Math.min()` use karke sabse sasta price return karein.

**Starter Code:**

```javascript
function getCheapestPrice(p1, p2, p3) {
  // TODO: Return the minimum of the three prices
}
```

**Test Cases:**

- `getCheapestPrice(120, 99, 150)` -> Expected: `99`

## Q6: Rolling the Dice (Math.random)

**Scenario:** Ludo game ke liye 0 se 1 ke beech ek random decimal number chahiye.

**Requirements:** `Math.random()` call karein aur jo bhi random value aaye usko 10 se multiply karke return karein.

**Starter Code:**

```javascript
function generateRandomMultiplier() {
  // TODO: Return Math.random() * 10
}
```

**Test Cases:**

- `generateRandomMultiplier()` -> Expected: A number greater than or equal to 0 and strictly less than 10 (e.g., `4.567`).

## Q7: Current Timeline (new Date)

**Scenario:** Bill generate karte waqt receipt par aaj ki date (system current date) chapni chahiye.

**Requirements:** `new Date()` object ka instance banayein aur usko return karein.

**Starter Code:**

```javascript
function getCurrentDateObject() {
  // TODO: Create a new Date object and return it
}
```

**Test Cases:**

- `typeof getCurrentDateObject()` -> Expected: `"object"` (It will be a valid Date instance).

## Q8: The Copyright Year

**Scenario:** Website ke footer mein "Copyright ©" ke sath hamesha current saal aana chahiye. Hardcode karne se har saal change karna padta hai.

**Requirements:** Date object aur uske method `getFullYear()` ka use karke current saal (e.g., 2024) return karein.

**Starter Code:**

```javascript
function getFooterYear() {
  // TODO: Return the current full year
}
```

**Test Cases:**

- `getFooterYear()` -> Expected: The current year (e.g., `2024` or `2026`).

## Q9: The 0-Indexed Month Illusion

**Scenario:** JavaScript Date object mein months 0 se start hote hain (Jan = 0, Dec = 11). Developer ko exact display month chahiye (1 to 12).

**Requirements:** `getMonth()` call karein aur usme 1 add karke return karein.

**Starter Code:**

```javascript
function getDisplayMonth() {
  let today = new Date();
  // TODO: Return today's month + 1
}
```

**Test Cases:**

- `getDisplayMonth()` -> Expected: A number between `1` and `12` based on the current month.

## Q10: Typeof built-ins

**Scenario:** JS mein Math aur Date dono Built-in objects hain, but inka behavior alag hai. `Math` global object hai, `Date` constructor hai.

**Requirements:** `Math` aur ek new `Date()` dono ka `typeof` ek array mein return karein.

**Starter Code:**

```javascript
function checkMathDateTypes() {
  let dateObj = new Date();
  // TODO: Return [typeof Math, typeof dateObj]
}
```

**Test Cases:**

- `checkMathDateTypes()` -> Expected: `["object", "object"]`
