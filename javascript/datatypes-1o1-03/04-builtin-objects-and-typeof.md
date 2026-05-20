# Module 4: String, Number, Boolean Methods & `typeof` Mixed

## Q1: The String Object Property (Length)

**Scenario:** String basic text hota hai par JS uske saath object jaisa bartav karta hai taaki hum uski length nikal sakein.

**Requirements:** Input message string ki `length` property return karein.

**Starter Code:**

```javascript
function getTextLength(text) {
  // TODO: Return length of the text
}
```

**Test Cases:**

- `getTextLength("Hello World")` -> Expected: `11`

## Q2: Built-in String Transformation (toUpperCase)

**Scenario:** Database mein sabhi discount codes hamesha capital letters mein store hote hain.

**Requirements:** String built-in method `toUpperCase()` ka use karke word transform karein.

**Starter Code:**

```javascript
function capitalizeCode(code) {
  // TODO: Return the uppercase version
}
```

**Test Cases:**

- `capitalizeCode("free50")` -> Expected: `"FREE50"`

## Q3: Searching Inside Strings (includes)

**Scenario:** Humein check karna hai ki ek user comment ke andar koi spam word ("offer") shamil hai ya nahi.

**Requirements:** String method `includes()` ka use karein aur true/false return karein.

**Starter Code:**

```javascript
function hasSpamWord(comment) {
  // TODO: Return true if comment includes "offer"
}
```

**Test Cases:**

- `hasSpamWord("Get a special offer today")` -> Expected: `true`
- `hasSpamWord("Hello friend")` -> Expected: `false`

## Q4: The Number Parser (parseInt)

**Scenario:** User input field se age text form mein aati hai (e.g., `"25 years"`). JS ke built-in Number parser se isme se number nikalna hai.

**Requirements:** `Number.parseInt()` ka use karke string ko integer mein convert karein.

**Starter Code:**

```javascript
function parseUserAge(ageString) {
  // TODO: Use parseInt to return the integer value
}
```

**Test Cases:**

- `parseUserAge("25 years")` -> Expected: `25` (Type Number)

## Q5: Fixing Decimal Precision (toFixed)

**Scenario:** Price aayi hai `45.678912` lekin humein screen par sirf 2 decimal places (`45.68`) dikhane hain.

**Requirements:** Number method `toFixed(2)` use karein. (Note: Ye method wapas String return karta hai).

**Starter Code:**

```javascript
function formatCurrency(priceNumber) {
  // TODO: Return price fixed to 2 decimal places
}
```

**Test Cases:**

- `formatCurrency(10.1234)` -> Expected: `"10.12"`

## Q6: The Boolean Built-in Wrapper

**Scenario:** Humein guarantee chahiye ki ek value purely Boolean true ya false me convert ho jaye.

**Requirements:** Built-in `Boolean()` object/wrapper ka use karein. Jo bhi aayega, usko Boolean mein wrap karke return karein.

**Starter Code:**

```javascript
function forceBoolean(value) {
  // TODO: Wrap value in Boolean() and return
}
```

**Test Cases:**

- `forceBoolean(0)` -> Expected: `false`
- `forceBoolean("Hello")` -> Expected: `true`

## Q7: Primitives vs Objects Strings

**Scenario:** JS mein string do tarike se banti hai. Ek normal aur ek `new String()` se. Inka type alag-alag aata hai.

**Requirements:** Variable `a` primitive string hai, `b` object string hai. Dono ka `typeof` array mein return karein.

**Starter Code:**

```javascript
function stringTypes() {
  let a = "Hello";
  let b = new String("Hello");
  // TODO: Return [typeof a, typeof b]
}
```

**Test Cases:**

- `stringTypes()` -> Expected: `["string", "object"]`

## Q8: The Number and NaN Type

**Scenario:** JavaScript ek ajeeb language hai. Jab koi math operation fail hota hai toh `NaN` (Not a Number) banta hai. Par `NaN` ka data type kya hota hai?

**Requirements:** `typeof 50` aur `typeof NaN` dono ko ek array mein return karein.

**Starter Code:**

```javascript
function numberTypes() {
  // TODO: Return [typeof 50, typeof NaN]
}
```

**Test Cases:**

- `numberTypes()` -> Expected: `["number", "number"]`

## Q9: Basic Boolean Type Check

**Scenario:** App me configuration settings aa rahi hain. Pata lagana hai ki setting on/off form (boolean) mein hai ya nahi.

**Requirements:** `typeof` operator ka use karein. Value string "boolean" return karni chahiye agar actual boolean ho.

**Starter Code:**

```javascript
function checkBoolType(flag) {
  // TODO: Return the typeof flag
}
```

**Test Cases:**

- `checkBoolType(true)` -> Expected: `"boolean"`
- `checkBoolType("true")` -> Expected: `"string"`

## Q10: Comprehensive Type Identifier

**Scenario:** Ek master function banana hai jo aane wale data ka sahi data type naam string mein bata de (bas String, Number, Boolean, aur Object ke liye).

**Requirements:** `typeof` operator direct return karein. Agar array bhejein, object bhejein, string ya number bhejein, jo system bole wo direct de dein.

**Starter Code:**

```javascript
function identifyData(anyData) {
  // TODO: Directly return the typeof anyData
}
```

**Test Cases:**

- `identifyData(100)` -> Expected: `"number"`
- `identifyData({ a: 1 })` -> Expected: `"object"`
- `identifyData([1, 2])` -> Expected: `"object"` (Arrays are objects in typeof!)
