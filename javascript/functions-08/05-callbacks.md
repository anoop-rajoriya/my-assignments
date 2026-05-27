# Module 5: Callbacks, Higher-Order & Built-In Functions

## Q1: The Master Chef Callback

**Scenario:** Functions ko normal variables ki tarah ek dusre ke andar pass kiya ja sakta hai (First-Class Citizens). Samosa ready hone ke baad "cutting" function ko bulana hai.
**Requirements:** `prepareSamosa(callback)` likhein. Uske andar se callback ko string `"Aloo"` pass karein.
**Starter Code:**

```javascript
function prepareSamosa(callback) {
  // TODO: Execute the callback function passing "Aloo" to it
}
```

**Test Cases:**

- `prepareSamosa((filling) => "Samosa with " + filling)` -> Expected: `"Samosa with Aloo"`
- `prepareSamosa((data) => data.toUpperCase())` -> Expected: `"ALOO"`

## Q2: Payment Gateway (Success / Fail Callbacks)

**Scenario:** Payment processing me do raste hote hain: success aur failure.
**Requirements:** `processPayment(amount, onSuccess, onFail)` function. Agar `amount >= 100` toh `onSuccess()` warna `onFail()` call karein.
**Starter Code:**

```javascript
function processPayment(amt, onSuccess, onFail) {
  // TODO: Conditional callback execution
}
```

**Test Cases:**

- `processPayment(150, () => "Passed", () => "Failed")` -> Expected: `"Passed"`
- `processPayment(50, () => "Passed", () => "Failed")` -> Expected: `"Failed"`

## Q3: Kirana Calculator (The `eval` Danger)

**Scenario:** Customer ne ek lambi equation `"10 + 20 * 2"` de di. JS builtin `eval()` is string ka calculation automatically kar deta hai. _(Note: Real production me `eval` security risk hota hai, but basic language feature janne ke liye iska use karenge)._
**Requirements:** `eval()` built-in function ka use karke string ko mathematically evaluate karein.
**Starter Code:**

```javascript
function stringMath(equation) {
  // TODO: Use eval() safely for this learning exercise
}
```

**Test Cases:**

- `stringMath("10 + 20 * 2")` -> Expected: `50`
- `stringMath("100 / 25")` -> Expected: `4`
- `stringMath("5 - 5")` -> Expected: `0`

## Q4: Binary Data Reader (`parseInt` Radix)

**Scenario:** Embedded system (Jaise Washing Machine) se error code binary mein aaya `"1010"`. Hume decimal (number 10) chahiye.
**Requirements:** Built-in `parseInt(string, radix)` function ka use karein. Radix `2` set karein for binary.
**Starter Code:**

```javascript
function decodeBinary(binaryStr) {
  // TODO: Convert binary string to base 10 number
}
```

**Test Cases:**

- `decodeBinary("1010")` -> Expected: `10`
- `decodeBinary("1111")` -> Expected: `15`
- `decodeBinary("0")` -> Expected: `0`

## Q5: Robust URL Encode (`encodeURI`)

**Scenario:** Zomato search URL banana hai. Search query "Shahi Paneer" mein space hai. Browser ise error maanta hai agar ise safe URI components mein encode na kiya jaye.
**Requirements:** Built-in `encodeURIComponent()` ka use karke string ko safe URL format me badlein.
**Starter Code:**

```javascript
function formatSearchQuery(foodItem) {
  // TODO: Return encoded URI component
}
```

**Test Cases:**

- `formatSearchQuery("Shahi Paneer")` -> Expected: `"Shahi%20Paneer"`
- `formatSearchQuery("KFC&MCD")` -> Expected: `"KFC%26MCD"`
- `formatSearchQuery("Dosa")` -> Expected: `"Dosa"`

## Q6: Custom Array Map Implementation (Higher Order Function)

**Scenario:** Bina inbuilt `.map()` ke array items ko double karna. Map function khud kaise banate hain?
**Requirements:** `myMap(array, callback)` banayein. Ek `for` loop se array padhein, har item ko callback ke through pass karein, aur naye array me push karein.
**Starter Code:**

```javascript
function myMap(arr, callbackFunc) {
  let result = [];
  // TODO: Implement map logic using a loop and the callback function
  return result;
}
```

**Test Cases:**

- `myMap([1, 2, 3], (x) => x * 2)` -> Expected: `[2, 4, 6]`
- `myMap(["a", "b"], (x) => x.toUpperCase())` -> Expected: `["A", "B"]`
- `myMap([], (x) => x)` -> Expected: `[]`

## Q7: Custom Array Filter Implementation (Higher Order Function)

**Scenario:** Bina inbuilt `.filter()` ke adult filter banana.
**Requirements:** `myFilter(arr, testCallback)`. `for` loop lagayein, agar `testCallback(item) === true` ho, tabhi item naye array me push karein.
**Starter Code:**

```javascript
function myFilter(arr, testCallback) {
  let result = [];
  // TODO: Implement filter logic
  return result;
}
```

**Test Cases:**

- `myFilter([10, 20, 30], (x) => x >= 18)` -> Expected: `[20, 30]`
- `myFilter(["Samosa", "Jalebi"], (x) => x === "Samosa")` -> Expected: `["Samosa"]`
- `myFilter([1, 2], (x) => x > 5)` -> Expected: `[]`

## Q8: Operator Selector (Returning Functions)

**Scenario:** Ek function jo machine ki requirement ke hisaab se doosra function return kare (Jaise Add wali machine ya Multiply wali machine).
**Requirements:** `getOperation(type)` likhein. Agar type `"ADD"`, return a function that adds two params `(a, b) => a + b`. If `"SUB"`, subtracts.
**Starter Code:**

```javascript
function getOperation(type) {
  // TODO: Return different Arrow Functions based on string type
}
```

**Test Cases:**

- `const addFunc = getOperation("ADD"); addFunc(5, 5)` -> Expected: `10`
- `const subFunc = getOperation("SUB"); subFunc(10, 3)` -> Expected: `7`

## Q9: Built-in `setTimeout` Mock Logic (Callback Execution Wrapper)

**Scenario:** Jab hum `setTimeout` jaisi azeem API use karte hain to background mein kya hota hai?
**Requirements:** Ek `executeLater(callback)` function banayein jo ek string `"Executing: "` aur uske baad callback ka return value append karke final string return kare. (Synchronous simulation).
**Starter Code:**

```javascript
function executeLater(callback) {
  // TODO: Return "Executing: " + callback()
}
```

**Test Cases:**

- `executeLater(() => "Download")` -> Expected: `"Executing: Download"`
- `executeLater(() => "Payment")` -> Expected: `"Executing: Payment"`

## Q10: URL Parameter Decoding (`decodeURIComponent`)

**Scenario:** URL se parameter read kiya toh `"Masala%20Dosa"` padhne mein aaya. Human readable string chahiye.
**Requirements:** Built-in `decodeURIComponent()` use karein.
**Starter Code:**

```javascript
function getReadableParam(encodedStr) {
  // TODO: Decode and return
}
```

**Test Cases:**

- `getReadableParam("Masala%20Dosa")` -> Expected: `"Masala Dosa"`
- `getReadableParam("A%26B")` -> Expected: `"A&B"`

## Q11: Composition: Wrapping Built-ins in Pure Functions

**Scenario:** String ke pehle 3 characters extract karne ka ek reliable function jo kabhi crash na ho, chahe parameter kuch bhi ho.
**Requirements:** `getShortName(name)`. Agar input falsy ya string nahi hai to `"Unknown"` return kare. Warna `substring(0, 3)` aur `.toUpperCase()` apply karke return kare.
**Starter Code:**

```javascript
function getShortName(name) {
  // TODO: Validate and compose string built-in methods
}
```

**Test Cases:**

- `getShortName("Aman")` -> Expected: `"AMA"`
- `getShortName("Raj")` -> Expected: `"RAJ"`
- `getShortName(null)` -> Expected: `"Unknown"`

## Q12: Functions are Objects (Adding properties to Functions)

**Scenario:** Javascript mein Functions literally Objects hote hain! Hum function ke oopar attributes add kar sakte hain jaise `myFunc.count = 0` taaki count yaad rahe (bina Closure use kiye!).
**Requirements:** Ek function `trackingFunc()` di gayi hai. Uske andar property `trackingFunc.calls` ko increment karein. Initialize the property to 0 outside.
**Starter Code:**

```javascript
function trackingFunc() {
  // TODO: Increment trackingFunc.calls
  return trackingFunc.calls;
}
// TODO: Initialize trackingFunc.calls to 0 here
```

**Test Cases:**

- `trackingFunc()` -> Expected: `1`
- `trackingFunc()` -> Expected: `2`
- `typeof trackingFunc.calls` -> Expected: `"number"`
