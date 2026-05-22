# Module 1: The Daily Input Checks (Primitives, NaN, Null & Undefined)

## Q1: Pandit Ji ka Khata (Handling Null/Undefined)

**Scenario:** Pandit ji ke khata system mein kabhi-kabhi customer ka naam blank, `null`, ya `undefined` aata hai. Humein isko sanitize karke default naam dena hai.

**Requirements:** Agar `name` null, undefined, ya empty string (`""`) hai, toh "Unknown Grahak" return karein, warna original name. Logical OR (`||`) ka use karein.

**Starter Code:**

```javascript
function sanitizeCustomerName(name) {
  // TODO: Return name or default fallback
}
```

**Test Cases:**

- `sanitizeCustomerName("Ravi")` -> Expected: `"Ravi"`
- `sanitizeCustomerName(null)` -> Expected: `"Unknown Grahak"`
- `sanitizeCustomerName("")` -> Expected: `"Unknown Grahak"`

## Q2: Samosa Price Tracker (NaN Handling)

**Scenario:** Dadi se kisine samosa ka price text mein daal diya `"bees"` jiski wajah se math karte waqt wo `NaN` ho gaya.

**Requirements:** `Number.isNaN()` ya `isNaN()` use karein. Agar `price` NaN hai toh `0` return karein, warna original price return karein.

**Starter Code:**

```javascript
function validateSamosaPrice(price) {
  // TODO: Check for NaN and sanitize
}
```

**Test Cases:**

- `validateSamosaPrice(15)` -> Expected: `15`
- `validateSamosaPrice(NaN)` -> Expected: `0`
- `validateSamosaPrice(20)` -> Expected: `20`

## Q3: Auto Wale ka Phone Number (String Trimming)

**Scenario:** Auto bhaiya booking app mein users phone number ke aage-peeche spaces daal dete hain (e.g., `" 9876543210 "`).

**Requirements:** String built-in method `.trim()` use karke aage-peeche ke spaces hatayein aur string return karein.

**Starter Code:**

```javascript
function cleanPhoneNumber(phone) {
  // TODO: Trim the string and return
}
```

**Test Cases:**

- `cleanPhoneNumber(" 9988776655 ")` -> Expected: `"9988776655"`
- `cleanPhoneNumber("1234567890")` -> Expected: `"1234567890"`
- `cleanPhoneNumber("  98765   ")` -> Expected: `"98765"`

## Q4: Jalebi Weight (Prevent Negative Numbers)

**Scenario:** Kisine galti se jalebi ka order `-2 kg` daal diya hai. Real world mein weight negative nahi ho sakta.

**Requirements:** Agar `weight` 0 se kam (negative) hai, toh use sanitize karke `1` (minimum order) set karein aur return karein.

**Starter Code:**

```javascript
function validateWeight(weight) {
  // TODO: Sanitize negative weights
}
```

**Test Cases:**

- `validateWeight(2)` -> Expected: `2`
- `validateWeight(-5)` -> Expected: `1`
- `validateWeight(0)` -> Expected: `0`

## Q5: Chai Tapri ka Default Sugar (Undefined Fallback)

**Scenario:** Agar customer ne chini ka amount nahi bataya (wo exactly `undefined` hai), toh bhaiya default 2 chammach daalte hain.

**Requirements:** Agar `sugar` strictly `undefined` hai, toh 2 return karein. Agar 0 (bina chini) ya koi aur number hai toh wahi return karein.

**Starter Code:**

```javascript
function getSugarAmount(sugar) {
  // TODO: Check strictly for undefined
}
```

**Test Cases:**

- `getSugarAmount(undefined)` -> Expected: `2`
- `getSugarAmount(0)` -> Expected: `0`
- `getSugarAmount(4)` -> Expected: `4`

## Q6: String Data Type Assurance

**Scenario:** Menu category ka naam hamesha string hona chahiye. API error ki wajah se kabhi number aa jata hai.

**Requirements:** Check karein if `typeof category` string nahi hai, toh false return karein. Agar string hai toh true.

**Starter Code:**

```javascript
function isCategoryValidString(category) {
  // TODO: Validate string type
}
```

**Test Cases:**

- `isCategoryValidString("Snacks")` -> Expected: `true`
- `isCategoryValidString(123)` -> Expected: `false`
- `isCategoryValidString(true)` -> Expected: `false`

## Q7: Type Casting the Bill (String to Number)

**Scenario:** HTML Input field hamesha bill amount ko text (`"250"`) banakar bhejta hai. Ise strictly number mein convert karna zaroori hai.

**Requirements:** `Number()` ya `parseFloat()` use karke string ko number mein badlein.

**Starter Code:**

```javascript
function parseBillAmount(amountStr) {
  // TODO: Sanitize string to actual number
}
```

**Test Cases:**

- `parseBillAmount("100")` -> Expected: `100` (Type Number)
- `parseBillAmount("50.5")` -> Expected: `50.5` (Type Number)
- `parseBillAmount("0")` -> Expected: `0` (Type Number)

## Q8: Strict Boolean Validator (Udhaar Access)

**Scenario:** `isUdhaarAllowed` flag backend se aata hai. Humein validate karna hai ki wo strictly boolean (`true` ya `false`) hi ho, `1` ya `"true"` (string) nahi.

**Requirements:** `typeof` check karein. Agar strict boolean hai toh value return karein, warna safety ke liye hamesha `false` return karein.

**Starter Code:**

```javascript
function sanitizeUdhaarFlag(flag) {
  // TODO: Return flag only if it's a boolean, else false
}
```

**Test Cases:**

- `sanitizeUdhaarFlag(true)` -> Expected: `true`
- `sanitizeUdhaarFlag("true")` -> Expected: `false`
- `sanitizeUdhaarFlag(1)` -> Expected: `false`

## Q9: Blank String Validation (Pincode Check)

**Scenario:** User ne pincode field mein space `"   "` daal diya. Length check se pass ho jayega par yeh invalid hai.

**Requirements:** Pehle string ko trim karein, fir check karein. Agar length 0 hai toh `"Invalid Pincode"` return karein, warna trimmed string return karein.

**Starter Code:**

```javascript
function validatePincode(pincode) {
  // TODO: Trim and check for empty string
}
```

**Test Cases:**

- `validatePincode("400001")` -> Expected: `"400001"`
- `validatePincode("   ")` -> Expected: `"Invalid Pincode"`
- `validatePincode("")` -> Expected: `"Invalid Pincode"`

## Q10: Infinity Math Sanitization

**Scenario:** Ek discount logic mein kisi ne bill ko 0 se divide kar diya aur result `Infinity` ban gaya!

**Requirements:** Built-in `isFinite()` ka use karein. Agar value finite hai toh value return karein, warna `0` return karein.

**Starter Code:**

```javascript
function sanitizeDiscountMath(result) {
  // TODO: Check if result is finite
}
```

**Test Cases:**

- `sanitizeDiscountMath(50)` -> Expected: `50`
- `sanitizeDiscountMath(100 / 0)` -> Expected: `0`
- `sanitizeDiscountMath(Infinity)` -> Expected: `0`
