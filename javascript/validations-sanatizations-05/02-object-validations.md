# Module 2: The Structure Check (Object Validations)

## Q1: The "Real Object" Illusion

**Scenario:** JavaScript mein `typeof null` aur `typeof []` (arrays) dono `"object"` hote hain. Humein strictly check karna hai ki data ek asal (real) Object `{}` hi ho.

**Requirements:** Condition banayein: `data !== null` AND `typeof data === "object"` AND `!Array.isArray(data)`. True/false return karein.

**Starter Code:**

```javascript
function isStrictObject(data) {
  // TODO: Validate strict object type
}
```

**Test Cases:**

- `isStrictObject({ name: "Raju" })` -> Expected: `true`
- `isStrictObject(null)` -> Expected: `false`
- `isStrictObject([1, 2, 3])` -> Expected: `false`

## Q2: Missing Key Validator (Price Check)

**Scenario:** Pandit ji ki dukan mein item add karte waqt agar kisi object mein `price` key nahi hai, toh wo system crash kar dega.

**Requirements:** Check karein ki object mein `price` property maujood hai aur `undefined` nahi hai. True/False return karein.

**Starter Code:**

```javascript
function hasPriceKey(itemObj) {
  // TODO: Check if price exists in object
}
```

**Test Cases:**

- `hasPriceKey({ item: "Sugar", price: 40 })` -> Expected: `true`
- `hasPriceKey({ item: "Salt" })` -> Expected: `false`
- `hasPriceKey({ item: "Rice", price: undefined })` -> Expected: `false`

## Q3: Empty Object Validator (No Order Items)

**Scenario:** Customer ne check-out click kar diya par cart object puri tarah empty `{}` hai.

**Requirements:** `Object.keys()` ka use karke object ki keys nikalen. Agar length 0 hai toh `"Cart Empty"` return karein, warna `"Processing"`.

**Starter Code:**

```javascript
function validateCartObject(cartObj) {
  // TODO: Check if object has zero keys
}
```

**Test Cases:**

- `validateCartObject({})` -> Expected: `"Cart Empty"`
- `validateCartObject({ milk: 2 })` -> Expected: `"Processing"`
- `validateCartObject({ bread: 1, butter: 1 })` -> Expected: `"Processing"`

## Q4: Property Sanitization (Lowercase Emails)

**Scenario:** API mein bhejne se pehle user object ke `email` property ko sanitize (lowercase) karna zaroori hai.

**Requirements:** Agar object mein `email` hai, toh use `.toLowerCase()` karke update karein aur pura object return karein.

**Starter Code:**

```javascript
function sanitizeUserEmail(user) {
  // TODO: Lowercase email and return user object
}
```

**Test Cases:**

- `sanitizeUserEmail({ email: "Aman@GMAIL.com" })` -> Expected: `{ email: "aman@gmail.com" }`
- `sanitizeUserEmail({ email: "test@test.com" })` -> Expected: `{ email: "test@test.com" }`
- `sanitizeUserEmail({ name: "Raj" })` -> Expected: `{ name: "Raj" }` (Should not crash if no email)

## Q5: Nested Object Safety (Avoid "Cannot read property of undefined")

**Scenario:** Bill generate karte waqt hum `customer.address.city` nikal rahe hain. Par ho sakta hai `address` object banaya hi na gaya ho.

**Requirements:** Pehle check karein `customer.address` exist karta hai ya nahi. Agar karta hai toh `city` return karein, warna `"Pick up at store"` return karein.

**Starter Code:**

```javascript
function getDeliveryCity(customer) {
  // TODO: Safely access nested property
}
```

**Test Cases:**

- `getDeliveryCity({ address: { city: "Pune" } })` -> Expected: `"Pune"`
- `getDeliveryCity({ name: "Ravi" })` -> Expected: `"Pick up at store"`
- `getDeliveryCity({})` -> Expected: `"Pick up at store"`

## Q6: Data Type Verification inside Objects

**Scenario:** Sabji mandi inventory object mein `stockQty` aati hai. Kisi API ne usko string `"100"` bhej diya. Hume number chahiye.

**Requirements:** Check karein agar `inventory.stockQty` string hai, toh use Number() se convert karke wapas object me save karein. Pura object return karein.

**Starter Code:**

```javascript
function sanitizeInventory(inventory) {
  // TODO: Ensure stockQty is a number
}
```

**Test Cases:**

- `sanitizeInventory({ stockQty: "50" })` -> Expected: `{ stockQty: 50 }`
- `sanitizeInventory({ stockQty: 20 })` -> Expected: `{ stockQty: 20 }`
- `sanitizeInventory({ stockQty: "0" })` -> Expected: `{ stockQty: 0 }`

## Q7: Object Data Fallbacks

**Scenario:** Dosa order mein `spiceLevel` key missing ho sakti hai.

**Requirements:** Object create / update karte waqt check karein. Agar `order.spiceLevel` falsy / missing hai, toh default usko `"Medium"` set karein. Object return karein.

**Starter Code:**

```javascript
function applyDefaultSpice(order) {
  // TODO: Apply fallback value if missing
}
```

**Test Cases:**

- `applyDefaultSpice({ item: "Masala" })` -> Expected: `{ item: "Masala", spiceLevel: "Medium" }`
- `applyDefaultSpice({ spiceLevel: "High" })` -> Expected: `{ spiceLevel: "High" }`
- `applyDefaultSpice({})` -> Expected: `{ spiceLevel: "Medium" }`

## Q8: The Undefined Property Remover

**Scenario:** Database mein garbage values jane se rokne ke liye, agar koi property strictly `undefined` hai, toh use object se `delete` karna hai.

**Requirements:** `if (obj.discount === undefined)` check karein, aur us property ko `delete` keyword se hatayein. Update object return karein.

**Starter Code:**

```javascript
function cleanObject(billObj) {
  // TODO: Delete discount if it is undefined
}
```

**Test Cases:**

- `cleanObject({ total: 100, discount: undefined })` -> Expected: `{ total: 100 }`
- `cleanObject({ total: 100, discount: 10 })` -> Expected: `{ total: 100, discount: 10 }`
- `cleanObject({ total: 50 })` -> Expected: `{ total: 50 }`

## Q9: Checking for Unwanted Keys

**Scenario:** Admin API mein user apna role change karke "Admin" bhejne ki koshish kar sakta hai.

**Requirements:** Check karein if object mein `role` key hai. Agar hai, toh object se us key ko `delete` kar dein for safety. Return object.

**Starter Code:**

```javascript
function preventRoleHack(userPayload) {
  // TODO: Delete role property if it exists
}
```

**Test Cases:**

- `preventRoleHack({ name: "Aman", role: "Admin" })` -> Expected: `{ name: "Aman" }`
- `preventRoleHack({ name: "Ravi" })` -> Expected: `{ name: "Ravi" }`
- `preventRoleHack({ role: "User" })` -> Expected: `{}`

## Q10: Boolean Flag Sanitization in Objects

**Scenario:** Switch system me log galti se `isActive: "true"` (string) bhej dete hain jisse if-conditions break hoti hain.

**Requirements:** `user.isActive` ko sanitize karein. Agar string "true" (any case) ya boolean `true` hai, toh usko strict boolean `true` set karein, warna `false` set karein.

**Starter Code:**

```javascript
function sanitizeStatus(user) {
  // TODO: Convert loose truthy/falsy to strict boolean
}
```

**Test Cases:**

- `sanitizeStatus({ isActive: "true" })` -> Expected: `{ isActive: true }`
- `sanitizeStatus({ isActive: "false" })` -> Expected: `{ isActive: false }`
- `sanitizeStatus({ isActive: true })` -> Expected: `{ isActive: true }`
