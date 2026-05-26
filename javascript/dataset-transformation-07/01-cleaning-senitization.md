# Module 1: Data Cleaning & Sanitization (Manual Filtering)

## Q1: Kirana Store Bill Cleaner (Removing Nulls)

**Scenario:** Pandit ji ke scanner ne kuch items scan nahi kiye aur array mein `null` aur `undefined` daal diye.
**Requirements:** `for...of` loop lagayein. Jo prices valid numbers hain, unhe ek naye array mein `push` karein aur return karein.
**Starter Code:**

```javascript
function cleanPrices(prices) {
  // TODO: Return an array with only valid numbers
}
```

**Test Cases:**

- `cleanPrices([10, null, 20, undefined, 30])` -> Expected: `[10, 20, 30]`
- `cleanPrices([null, undefined])` -> Expected: `[]`
- `cleanPrices([50, 60])` -> Expected: `[50, 60]`

## Q2: Zomato Out-of-Stock Remover

**Scenario:** Restaurant menu array of objects hai. Jo items `inStock: false` hain, unhe UI pe nahi dikhana.
**Requirements:** `for...of` use karein. Sirf un objects ko naye array mein daalein jinki `inStock` property `true` hai.
**Starter Code:**

```javascript
function getAvailableItems(menu) {
  // TODO: Filter out objects where inStock is false
}
```

**Test Cases:**

- `getAvailableItems([{name: "Dosa", inStock: true}, {name: "Idli", inStock: false}])` -> Expected: `[{name: "Dosa", inStock: true}]`
- `getAvailableItems([{name: "Tea", inStock: false}])` -> Expected: `[]`
- `getAvailableItems([{name: "Coffee", inStock: true}])` -> Expected: `[{name: "Coffee", inStock: true}]`

## Q3: Phone Number Standardizer

**Scenario:** Delivery app mein users ne phone numbers mein spaces aur country codes daal diye hain.
**Requirements:** Array of strings aayega. Har string par loop lagayein. `.replace(" ", "")` aur `.replace("+91", "")` use karke clean karein aur naye array me save karein.
**Starter Code:**

```javascript
function cleanPhoneNumbers(phones) {
  // TODO: Remove spaces and +91 from each string manually
}
```

**Test Cases:**

- `cleanPhoneNumbers(["+91 9876543210", "9998887776"])` -> Expected: `["9876543210", "9998887776"]`
- `cleanPhoneNumbers([" +919999999999 "])` -> Expected: `["9999999999"]` (Assume basic trim too)
- `cleanPhoneNumbers([])` -> Expected: `[]`

## Q4: Removing Inactive Users from Object Map

**Scenario:** Admin panel pe ek object hai jisme keys User IDs hain aur values user details. Inactive users ko list se hatana hai.
**Requirements:** `for...in` use karein. Agar `users[key].isActive` false hai, to us key ko ignore karein, baaki ko naye object me copy karein.
**Starter Code:**

```javascript
function filterActiveUsers(usersObj) {
  // TODO: Return a new object with only active users
}
```

**Test Cases:**

- `filterActiveUsers({ u1: {name: "Raj", isActive: true}, u2: {name: "Aman", isActive: false} })` -> Expected: `{ u1: {name: "Raj", isActive: true} }`
- `filterActiveUsers({ u1: {name: "A", isActive: false} })` -> Expected: `{}`
- `filterActiveUsers({ u1: {name: "B", isActive: true} })` -> Expected: `{ u1: {name: "B", isActive: true} }`

## Q5: Standardizing Text Cases (Lowercasing Emails)

**Scenario:** Login system case-sensitive hota hai. Users array of objects mein email fields ko clean karna hai.
**Requirements:** Loop lagakar har object ki `email` property ko `.toLowerCase()` karein aur modified array return karein.
**Starter Code:**

```javascript
function normalizeEmails(users) {
  // TODO: Lowercase the email property of each object
}
```

**Test Cases:**

- `normalizeEmails([{email: "A@B.COM"}])` -> Expected: `[{email: "a@b.com"}]`
- `normalizeEmails([{email: "test@test.com"}])` -> Expected: `[{email: "test@test.com"}]`
- `normalizeEmails([])` -> Expected: `[]`

## Q6: Age Restriction Checker (Adults Only)

**Scenario:** Movie ticket booking app pe ages ka array aaya hai. Sirf 18+ allow karna hai.
**Requirements:** Ek naya array banayein. `for` loop se check karein, agar `age >= 18` ho toh naye array mein push karein.
**Starter Code:**

```javascript
function filterAdults(ages) {
  // TODO: Manually filter ages >= 18
}
```

**Test Cases:**

- `filterAdults([12, 18, 25, 16])` -> Expected: `[18, 25]`
- `filterAdults([10, 15])` -> Expected: `[]`
- `filterAdults([20])` -> Expected: `[20]`

## Q7: Removing Duplicate IDs (Manual Set logic)

**Scenario:** Event registration mein ek hi user ne 2 baar submit kar diya. IDs array mein duplicates hain.
**Requirements:** `for` loop aur `.includes()` ka use karein. Agar naye array mein ID nahi hai tabhi push karein.
**Starter Code:**

```javascript
function removeDuplicates(ids) {
  // TODO: Create an array with unique IDs only
}
```

**Test Cases:**

- `removeDuplicates([101, 102, 101, 103])` -> Expected: `[101, 102, 103]`
- `removeDuplicates([1, 1, 1])` -> Expected: `[1]`
- `removeDuplicates([])` -> Expected: `[]`

## Q8: Discarding Invalid Objects (Form Data)

**Scenario:** Menu list update karni hai, par kuch objects mein `price` missing hai. System aage crash ho jayega!
**Requirements:** Loop lagayein. Sirf wo objects naye array mein lein jinki `price` property exist karti ho (falsy like undefined/null na ho).
**Starter Code:**

```javascript
function validateMenu(items) {
  // TODO: Filter out items missing a price
}
```

**Test Cases:**

- `validateMenu([{name: "Tea", price: 10}, {name: "Coffee"}])` -> Expected: `[{name: "Tea", price: 10}]`
- `validateMenu([{name: "Water", price: 0}])` -> Expected: `[{name: "Water", price: 0}]` (Handle 0 properly!)
- `validateMenu([{name: "Milk"}])` -> Expected: `[]`

## Q9: The Wedding Buffet Separator

**Scenario:** Shaadi ki catering list mein veg aur non-veg mix ho gaya hai. Inhe 2 alag arrays mein divide karna hai.
**Requirements:** Ek object return karein jisme 2 arrays hon: `{ veg: [], nonVeg: [] }`. Loop lagakar item check karein aur sahi array mein push karein.
**Starter Code:**

```javascript
function separateFood(dishes) {
  // TODO: Split the array based on the isVeg boolean
}
```

**Test Cases:**

- `separateFood([{name: "Paneer", isVeg: true}, {name: "Chicken", isVeg: false}])` -> Expected: `{ veg: [{name: "Paneer", isVeg: true}], nonVeg: [{name: "Chicken", isVeg: false}] }`
- `separateFood([{name: "Dal", isVeg: true}])` -> Expected: `{ veg: [{name: "Dal", isVeg: true}], nonVeg: [] }`
- `separateFood([])` -> Expected: `{ veg: [], nonVeg: [] }`

## Q10: Object Garbage Collector

**Scenario:** User profile update karte waqt, form ne empty strings `""` aur `null` bhej diye. Un properties ko object se hatana hai.
**Requirements:** Object par `for...in` chalayein. Agar value `""`, `null`, ya `undefined` hai, toh `delete obj[key]` karein. Clean object return karein.
**Starter Code:**

```javascript
function cleanProfile(profileObj) {
  // TODO: Delete keys with falsy junk values
}
```

**Test Cases:**

- `cleanProfile({ name: "Raj", age: null, city: "" })` -> Expected: `{ name: "Raj" }`
- `cleanProfile({ phone: "123", isActive: false })` -> Expected: `{ phone: "123", isActive: false }` (Don't delete valid booleans!)
- `cleanProfile({ bio: undefined })` -> Expected: `{}`
