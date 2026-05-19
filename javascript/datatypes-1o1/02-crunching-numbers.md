# Module 2: Crunching "Numbers"

## Q1: Shopping Cart Total

**Scenario:** Ek cart mein do items hain, unka total sum calculate karna hai.

**Requirements:** `price1` aur `price2` ko add karke total return karein.

**Starter Code:**

```javascript
function getTotal(price1, price2) {
  // TODO: Return sum of both prices
}
```

**Test Cases:**

- `getTotal(150, 50)` -> Expected: `200`

## Q2: Odd or Even Offer

**Scenario:** Ek game hai jahan sirf even (sam) number wale users ko prize milega. Number odd hai ya even, yeh Modulo (`%`) operator se pata chalta hai.

**Requirements:** Agar number even hai toh `true` return karein, warna `false`.

**Starter Code:**

```javascript
function isEvenNumber(num) {
  // TODO: Return true if even, false if odd
}
```

**Test Cases:**

- `isEvenNumber(4)` -> Expected: `true`
- `isEvenNumber(7)` -> Expected: `false`

## Q3: String to Number Conversion

**Scenario:** HTML input field se hamesha text string milti hai, bhale hi user number type kare (e.g., `"10"`). Maths karne se pehle ise number banana hoga.

**Requirements:** Diye gaye string input ko pure Number mein convert karke return karein.

**Starter Code:**

```javascript
function convertToNumber(strNum) {
  // TODO: Convert strNum to a number and return
}
```

**Test Cases:**

- `convertToNumber("45")` -> Expected: `45` (Type Number)

## Q4: Number to String

**Scenario:** App ke UI mein invoice number dikhana hai, aur uske aage zeroes pad karne ke liye usko string banana zaroori hai.

**Requirements:** Diye gaye number ko String data type mein convert karein.

**Starter Code:**

```javascript
function convertToString(num) {
  // TODO: Convert num to string and return
}
```

**Test Cases:**

- `convertToString(101)` -> Expected: `"101"` (Type String)

## Q5: Understanding NaN (Not a Number)

**Scenario:** Agar koi alphabets wale string ko number banane ki koshish kare ("abc" \* 5), toh JS `NaN` return karta hai.

**Requirements:** Ek function likhein jo check kare ki math operation fail toh nahi ho gaya. (Hint: use `isNaN()`). Return true agar wo NaN hai.

**Starter Code:**

```javascript
function isInvalidNumber(value) {
  // TODO: Return true if the value is NaN
}
```

**Test Cases:**

- `isInvalidNumber(NaN)` -> Expected: `true`
- `isInvalidNumber(15)` -> Expected: `false`

## Q6: Area of a Square

**Scenario:** Ek geometry app mein square ka area nikalna hai (side \* side). Aapko Exponentiation operator (``) use karna hai.

**Requirements:** `side` ka square calculate karein.

**Starter Code:**

```javascript
function calculateSquareArea(side) {
  // TODO: Return area using ** operator
}
```

**Test Cases:**

- `calculateSquareArea(4)` -> Expected: `16`
- `calculateSquareArea(5)` -> Expected: `25`

## Q7: Decimal Math

**Scenario:** Bill aane par GST add hua aur total `99.99` ban gaya. Par user ko round figure chahiye.

**Requirements:** `Math.round()` ka use karke decimal amount ko nearest whole number mein convert karein.

**Starter Code:**

```javascript
function roundOffBill(amount) {
  // TODO: Return rounded amount
}
```

**Test Cases:**

- `roundOffBill(99.4)` -> Expected: `99`
- `roundOffBill(99.6)` -> Expected: `100`

## Q8: The Number Type Check

**Scenario:** Ek function ko strictly number hi chahiye kaam karne ke liye.

**Requirements:** `typeof` check karein aur confirm karein ki input Number type ka hi hai. (True/False return karein).

**Starter Code:**

```javascript
function isStrictlyNumber(val) {
  // TODO: Return true if type is number
}
```

**Test Cases:**

- `isStrictlyNumber(50)` -> Expected: `true`
- `isStrictlyNumber("50")` -> Expected: `false`
