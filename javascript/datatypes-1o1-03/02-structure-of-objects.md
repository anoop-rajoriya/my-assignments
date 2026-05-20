## Module 2: The Structure of Objects

### Q1: The User Profile

**Scenario:** Ek social media app ke liye user profile data ek jagah group karna hai. Object key-value pairs ke liye best hai.

**Requirements:** Ek object return karein jisme `name` (String), `age` (Number), aur `isActive` (Boolean) keys hon.

**Starter Code:**

```javascript
function createUserProfile(userName, userAge) {
  // TODO: Create an object with name, age, and isActive set to true. Return it.
}
```

**Test Cases:**

- `createUserProfile("Aman", 25)` -> Expected: `{ name: "Aman", age: 25, isActive: true }`

### Q2: Dot Notation Access

**Scenario:** Product detail page par product ki keemat (price) dikhani hai.

**Requirements:** Dot notation (`.`) ka use karke object se `price` key ki value nikal kar return karein.

**Starter Code:**

```javascript
function getProductPrice(product) {
  // TODO: Return the price property using dot notation
}
```

**Test Cases:**

- `getProductPrice({ title: "Phone", price: 500 })` -> Expected: `500`

### Q3: Bracket Notation Magic

**Scenario:** Kabhi-kabhi object ki "key" ka naam variable ke andar store hota hai. Wahan dot notation fail ho jata hai, tab Bracket `[]` notation kaam aata hai.

**Requirements:** Bracket notation ka use karke object me se `keyName` wali property return karein.

**Starter Code:**

```javascript
function getDynamicValue(obj, keyName) {
  // TODO: Return the value from obj using keyName variable
}
```

**Test Cases:**

- `getDynamicValue({ car: "Honda", color: "Red" }, "color")` -> Expected: `"Red"`

### Q4: Adding a New Trait

**Scenario:** Game mein player ko ek naya tag "VIP" mil gaya hai, jo pehle uske object mein nahi tha.

**Requirements:** Object mein ek nayi property `isVIP` add karein aur uski value `true` set karein. Object return karein.

**Starter Code:**

```javascript
function makeVIP(playerProfile) {
  // TODO: Add isVIP property and return playerProfile
}
```

**Test Cases:**

- `makeVIP({ username: "Gamer1" })` -> Expected: `{ username: "Gamer1", isVIP: true }`

### Q5: Updating the High Score

**Scenario:** Player ne apna purana record tod diya hai. Humein object mein maujood `score` ko update karna hai.

**Requirements:** `player` object ki `score` property ko `newScore` se replace karein.

**Starter Code:**

```javascript
function updateScore(player, newScore) {
  // TODO: Update score and return the object
}
```

**Test Cases:**

- `updateScore({ name: "Ravi", score: 10 }, 50)` -> Expected: `{ name: "Ravi", score: 50 }`

### Q6: Deleting Sensitive Data

**Scenario:** API mein user profile bhejne se pehle humein uski `password` property ko delete karna zaroori hai.

**Requirements:** `delete` keyword ka use karke object se `password` hata dein aur object return karein.

**Starter Code:**

```javascript
function sanitizeProfile(user) {
  // TODO: Delete the password property and return user
}
```

**Test Cases:**

- `sanitizeProfile({ email: "a@b.com", password: "123" })` -> Expected: `{ email: "a@b.com" }`

### Q7: Typeof Check for Objects

**Scenario:** Ek function array ya string nahi, sirf purely object expect kar raha hai.

**Requirements:** `typeof` operator ka use karein. Agar value object hai toh `true` return karein (Note: Null aur Array bhi object aate hain, par yahan sirf basic typeof check karna hai).

**Starter Code:**

```javascript
function isAnObject(val) {
  // TODO: Return true if typeof is "object"
}
```

**Test Cases:**

- `isAnObject({ a: 1 })` -> Expected: `true`
- `isAnObject("String")` -> Expected: `false`

### Q8: Nested Object Extraction

**Scenario:** Ek address object ke andar ek aur object `location` hai jisme `city` hai. Humein sirf `city` nikalna hai.

**Requirements:** Object-inside-object se `city` ki value access karein aur return karein.

**Starter Code:**

```javascript
function getCityName(userRecord) {
  // userRecord looks like: { name: "Raj", location: { city: "Delhi" } }
  // TODO: Return the city name
}
```

**Test Cases:**

- `getCityName({ name: "Raj", location: { city: "Delhi" } })` -> Expected: `"Delhi"`

### Q9: Extracting All Keys (Built-in Object Method)

**Scenario:** Humein dekhna hai ki ek object mein kaun-kaun si properties maujood hain. `Object.keys()` iska sabse simple tarika hai.

**Requirements:** Built-in `Object.keys()` method ka use karke object ki saari keys ki array return karein.

**Starter Code:**

```javascript
function getAllKeys(dataObject) {
  // TODO: Return an array of keys using Object.keys()
}
```

**Test Cases:**

- `getAllKeys({ a: 1, b: 2 })` -> Expected: `["a", "b"]`

### Q10: Extracting All Values (Built-in Object Method)

**Scenario:** Chart banane ke liye humein object mein se sirf values (numbers/data) nikal kar ek array mein chahiye, keys nahi.

**Requirements:** Built-in `Object.values()` method ka use karke object ki saari values return karein.

**Starter Code:**

```javascript
function getAllValues(dataObject) {
  // TODO: Return an array of values using Object.values()
}
```

**Test Cases:**

- `getAllValues({ apples: 10, oranges: 20 })` -> Expected: `[10, 20]`
