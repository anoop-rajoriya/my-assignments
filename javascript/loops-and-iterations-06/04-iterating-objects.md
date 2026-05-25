# Module 4: Iterating Objects (for...in Loop)

## Q1: Student Report Card Sum

**Scenario:** Report card ek object mein aata hai: { math: 80, science: 90, english: 70 }. Humein total marks nikalne hain.
**Requirements:** for...in loop ka use karke object ke andar iterate karein, saari values ko add karein aur return karein.
**Starter Code:**

```javascript
function getTotalMarks(reportCard) {
  // TODO: Use for...in to sum up object values
}
```

**Test Cases:**

- getTotalMarks({ math: 80, science: 90 }) -> Expected: 170
- getTotalMarks({ hindi: 50 }) -> Expected: 50
- getTotalMarks({}) -> Expected: 0

## Q2: Counting Object Properties (Laptop Specs)

**Scenario:** E-commerce site pe laptop specs object me aate hain (e.g. { ram: "8GB", storage: "1TB" }). Humein batana hai ki total kitne specs mention kiye gaye hain.
**Requirements:** for...in loop se object ki total keys (properties) count karein.
**Starter Code:**

```javascript
function countSpecs(laptopObj) {
  // TODO: Count total keys using for...in
}
```

**Test Cases:**

- countSpecs({ ram: "16GB", cpu: "i7", os: "Windows" }) -> Expected: 3
- countSpecs({ brand: "Apple" }) -> Expected: 1
- countSpecs({}) -> Expected: 0

## Q3: Applying the Diwali Flat Discount

**Scenario:** Dukan ka cart ek object hai jahan keys item ka naam aur values unka price hain. Diwali par sabhi items par 50 Rs ka flat discount dena hai.
**Requirements:** for...in lagakar har value mein se 50 minus karein aur modified object return karein. (Maan lijiye sabhi prices >= 50 hain).
**Starter Code:**

```javascript
function applyDiwaliDiscount(cartObj) {
  // TODO: Reduce each value by 50
}
```

**Test Cases:**

- applyDiwaliDiscount({ shirt: 500, pant: 800 }) -> Expected: { shirt: 450, pant: 750 }
- applyDiwaliDiscount({ cap: 100 }) -> Expected: { cap: 50 }
- applyDiwaliDiscount({}) -> Expected: {}

## Q4: Check for Fail Grades (< 33)

**Scenario:** Object me subjects aur unke marks hain. Agar ek bhi subject me fail (< 33) hai toh result "Fail" warna "Pass".
**Requirements:** for...in se traverse karein. Agar koi bhi value < 33 milti hai toh turant "Fail" return karein.
**Starter Code:**

```javascript
function checkPassFail(marksObj) {
  // TODO: Return "Fail" if any mark < 33, else "Pass"
}
```

**Test Cases:**

- checkPassFail({ math: 40, science: 30 }) -> Expected: "Fail"
- checkPassFail({ math: 80, english: 70 }) -> Expected: "Pass"
- checkPassFail({}) -> Expected: "Pass"

## Q5: Finding the Most Expensive Item

**Scenario:** Object me alag-alag items ke prices hain. Pata lagana hai sabse mahenga item kitne ka hai?
**Requirements:** for...in loop se har property ki value check karein aur maximum value find karke return karein. Agar object empty ho toh 0.
**Starter Code:**

```javascript
function getMaxPrice(pricesObj) {
  // TODO: Find the maximum number in object values
}
```

**Test Cases:**

- getMaxPrice({ tv: 20000, fridge: 15000, AC: 25000 }) -> Expected: 25000
- getMaxPrice({ bulb: 100 }) -> Expected: 100
- getMaxPrice({}) -> Expected: 0

## Q6: Formatting the Order Summary

**Scenario:** Swiggy cart object { pizza: 2, burger: 1 } ko display string banani hai: "pizza: 2, burger: 1".
**Requirements:** for...in se key-value nikalkar string format banayein. (Hints: Array me push karke .join(", ") karna easy hota hai).
**Starter Code:**

```javascript
function getOrderSummary(orderObj) {
  // TODO: Return formatted string
}
```

**Test Cases:**

- getOrderSummary({ tea: 3, bun: 2 }) -> Expected: "tea: 3, bun: 2"
- getOrderSummary({ thali: 1 }) -> Expected: "thali: 1"
- getOrderSummary({}) -> Expected: ""

## Q7: Extracting all "Keys" manually

**Scenario:** Object.keys() method toh hota hi hai, but humein seekhna hai ise internally kaise banaya gaya hai.
**Requirements:** for...in loop lagayein, object ki saari keys ek naye array mein push karein aur return karein.
**Starter Code:**

```javascript
function getCustomKeys(obj) {
  // TODO: Replicate Object.keys() functionality using for...in
}
```

**Test Cases:**

- getCustomKeys({ a: 1, b: 2 }) -> Expected: ["a", "b"]
- getCustomKeys({ name: "Raj" }) -> Expected: ["name"]
- getCustomKeys({}) -> Expected: []

## Q8: Filtering out the Junk (Strings only)

**Scenario:** Form submisison me object me number, boolean, aur string sab mix aata hai. Humein ek naya object return karna hai jisme sirf Strings bache hon.
**Requirements:** for...in use karein. typeof operator se check karein ki value string hai ya nahi. Agar hai, toh use naye object mein daalein.
**Starter Code:**

```javascript
function extractStrings(mixedObj) {
  // TODO: Return a new object keeping only string values
}
```

**Test Cases:**

- extractStrings({ age: 25, name: "Aman", isActive: true }) -> Expected: { name: "Aman" }
- extractStrings({ city: "Delhi", pin: 110001 }) -> Expected: { city: "Delhi" }
- extractStrings({ count: 10 }) -> Expected: {}

## Q9: The Simple Object Merge

**Scenario:** User ne purani setting object ko nayi setting ke saath update kiya hai. Agar koi key Object 2 mein hai, toh wo Object 1 mein jod do / update kar do.
**Requirements:** Object 1 ko base mankar, Object 2 par for...in chalayein aur Object 1 mein properties copy/overwrite karein. Modified Object 1 return karein.
**Starter Code:**

```javascript
function mergeSettings(obj1, obj2) {
  // TODO: Add properties of obj2 into obj1
}
```

**Test Cases:**

- mergeSettings({ theme: "light" }, { theme: "dark", volume: 50 }) -> Expected: { theme: "dark", volume: 50 }
- mergeSettings({ a: 1 }, { b: 2 }) -> Expected: { a: 1, b: 2 }
- mergeSettings({}, { x: 10 }) -> Expected: { x: 10 }

## Q10: Verifying Complete Forms

**Scenario:** KYC form object aayega. Agar ek bhi field ki value empty string "" ya null hai, toh form invalid hai.
**Requirements:** for...in lagakar check karein. Agar koi value invalid / falsy (except 0 or false) lage, ya safely just "" ya null lage, "Incomplete" return karein. Warna "Complete".
**Starter Code:**

```javascript
function verifyKYC(formObj) {
  // TODO: Check if any value is exactly "" or null
}
```

**Test Cases:**

- verifyKYC({ pan: "ABC", aadhar: "" }) -> Expected: "Incomplete"
- verifyKYC({ pan: "ABC", aadhar: "123" }) -> Expected: "Complete"
- verifyKYC({ name: null }) -> Expected: "Incomplete"
