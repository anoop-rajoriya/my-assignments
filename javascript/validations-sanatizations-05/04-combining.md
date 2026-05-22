# Module 4: Production Mixed Scenarios (Combining Concepts)

## Q1: The Master Form Validator

**Scenario:** Registration form validate karna hai. Name blank nahi hona chahiye, Age >= 18 honi chahiye.

**Requirements:** Ek object `user` aayega. Agar `user.name` falsy hai, return "Name required". Agar `user.age` undefined hai ya `< 18` hai, return "Underage". Warna return "Valid".

**Starter Code:**

```javascript
function validateRegistration(user) {
  // TODO: Implement compound validation logic
}
```

**Test Cases:**

- `validateRegistration({ name: "Raj", age: 20 })` -> Expected: `"Valid"`
- `validateRegistration({ name: "", age: 25 })` -> Expected: `"Name required"`
- `validateRegistration({ name: "Raj", age: 16 })` -> Expected: `"Underage"`

## Q2: Robust Currency Formatter

**Scenario:** E-commerce total calculate hone par decimal me lamba number aaya (e.g. `250.333333`).

**Requirements:** Data validate karein. Agar parameter valid Number nahi hai toh `0.00` (String) return karein. Agar number hai, toh `.toFixed(2)` karke return karein.

**Starter Code:**

```javascript
function sanitizeCurrency(amount) {
  // TODO: Check type, return formatted string or "0.00"
}
```

**Test Cases:**

- `sanitizeCurrency(25.678)` -> Expected: `"25.68"`
- `sanitizeCurrency("500")` -> Expected: `"0.00"`
- `sanitizeCurrency(10)` -> Expected: `"10.00"`

## Q3: Complete Address Sanitizer

**Scenario:** Zomato delivery address object ko sanitize karna hai. Agar `street` nahi hai, to usme "N/A" daalein. Agar `pincode` string hai, to Number me convert karein.

**Requirements:** Object modification apply karein as requested. Return updated object.

**Starter Code:**

```javascript
function sanitizeAddress(addressObj) {
  // TODO: Fix missing street and cast pincode to Number
}
```

**Test Cases:**

- `sanitizeAddress({ city: "Mumbai", pincode: "400001" })` -> Expected: `{ city: "Mumbai", pincode: 400001, street: "N/A" }`
- `sanitizeAddress({ street: "MG Road", pincode: 110001 })` -> Expected: `{ street: "MG Road", pincode: 110001 }`
- `sanitizeAddress({ pincode: "123" })` -> Expected: `{ pincode: 123, street: "N/A" }`

## Q4: Search Query Cleaner

**Scenario:** Database mein query bhejne se pehle search box string ko clean karna zaroori hai.

**Requirements:** Input string ko pehle `.trim()` karein, uske baad `.toLowerCase()` karein. Agar string khali ho jaye (falsy), toh `null` return karein.

**Starter Code:**

```javascript
function cleanSearchQuery(query) {
  // TODO: Chain string methods and validate empty state
}
```

**Test Cases:**

- `cleanSearchQuery("  Paneer TIkka  ")` -> Expected: `"paneer tikka"`
- `cleanSearchQuery("   ")` -> Expected: `null`
- `cleanSearchQuery("Samosa")` -> Expected: `"samosa"`

## Q5: Role-based Access Gate

**Scenario:** Ek API endpoint ko sirf "Admin" aur "Manager" access kar sakte hain. User object `{"role": "User"}` pass hoga.

**Requirements:** `allowedRoles = ["Admin", "Manager"]`. Check karein ki user.role array mein `.includes()` karta hai ya nahi. True/False return karein.

**Starter Code:**

```javascript
const allowedRoles = ["Admin", "Manager"];
function checkAccess(userObj) {
  // TODO: Validate user role against allowed list
}
```

**Test Cases:**

- `checkAccess({ role: "Admin" })` -> Expected: `true`
- `checkAccess({ role: "User" })` -> Expected: `false`
- `checkAccess({})` -> Expected: `false`

## Q6: Phone Number Digit Strict Checker

**Scenario:** India mein mobile number sirf 10 digits ka hota hai. String format mein number milega.

**Requirements:** Trim karne ke baad, length strictly `10` honi chahiye aur check karein ki andar NaN na ho (using `isNaN`). True/False return karein.

**Starter Code:**

```javascript
function isIndianNumber(phoneStr) {
  // TODO: Validate length == 10 AND must be numeric
}
```

**Test Cases:**

- `isIndianNumber("9876543210")` -> Expected: `true`
- `isIndianNumber("  9876543210  ")` -> Expected: `true`
- `isIndianNumber("98765ABCDE")` -> Expected: `false`

## Q7: Date Validity Check

**Scenario:** Delivery date API se string bankar aati hai. Humein pata karna hai ki kya ye ek valid Date object me convert ho sakti hai?

**Requirements:** `new Date(dateString).getTime()` use karein. Agar date invalid hai toh yeh `NaN` dega. Agar result `isNaN` hai toh `"Invalid Date"`, warna `"Valid Date"` return karein.

**Starter Code:**

```javascript
function validateDeliveryDate(dateStr) {
  // TODO: Parse date and check for NaN
}
```

**Test Cases:**

- `validateDeliveryDate("2026-05-21")` -> Expected: `"Valid Date"`
- `validateDeliveryDate("Hello World")` -> Expected: `"Invalid Date"`
- `validateDeliveryDate("2026/12/31")` -> Expected: `"Valid Date"`

## Q8: The Master Error Aggregator (Pushing Errors)

**Scenario:** Frontend par error messages ka array dikhana hai based on multiple checks.

**Requirements:** Ek array banayein `errors = []`.

- Agar `user.name` missing hai toh array mein `.push("Name missing")`.
- Agar `user.email` missing hai toh `.push("Email missing")`.
  Return `errors` array.
  **Starter Code:**

```javascript
function collectErrors(user) {
  // TODO: Validate individual fields and push error strings
}
```

**Test Cases:**

- `collectErrors({ name: "Aman", email: "a@a.com" })` -> Expected: `[]`
- `collectErrors({ name: "Aman" })` -> Expected: `["Email missing"]`
- `collectErrors({})` -> Expected: `["Name missing", "Email missing"]`

## Q9: Complex Ternary Discount Application

**Scenario:** Ek user VIP ho sakta hai ya naya ho sakta hai. Agar `isVIP` true hai toh 20% discount. Agar nahi hai, to check karo `isNewUser` true hai kya? Agar haan toh 10% discount. Warna 0.

**Requirements:** Nested Ternary Operator (`condition ? true : (condition2 ? true : false)`) ka use karke discount Number return karein.

**Starter Code:**

```javascript
function getDiscountRate(isVIP, isNewUser) {
  // TODO: Use chained ternary operators
}
```

**Test Cases:**

- `getDiscountRate(true, false)` -> Expected: `20`
- `getDiscountRate(false, true)` -> Expected: `10`
- `getDiscountRate(false, false)` -> Expected: `0`

## Q10: Final Sanitized API Payload

**Scenario:** Frontend se server ko data bhejna hai, but kachra (junk) clean karke.

**Requirements:** `payload` object aayega.

1. Agar usme `token` nahi hai, return `null` immediately.
2. Agar `metadata` array nahi hai, use `[]` set karein.
3. `status` ko lowercase string kardein (`payload.status.toLowerCase()`).
   Updated object return karein.
   **Starter Code:**

```javascript
function formatAPIRequest(payload) {
  // TODO: Return null if token missing. Sanitize metadata and status.
}
```

**Test Cases:**

- `formatAPIRequest({ token: "123", status: "ACTIVE" })` -> Expected: `{ token: "123", status: "active", metadata: [] }`
- `formatAPIRequest({ status: "ACTIVE" })` -> Expected: `null`
- `formatAPIRequest({ token: "abc", status: "Pending", metadata: ["Logs"] })` -> Expected: `{ token: "abc", status: "pending", metadata: ["Logs"] }`
