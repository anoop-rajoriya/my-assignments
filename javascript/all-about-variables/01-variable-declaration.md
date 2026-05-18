# Module 1: Variable Declarations (`var`, `let`, and `const`)

## Q1: The Unchangeable GST Rate

**Scenario (Problem):** Ek e-commerce app mein humein bills calculate karne hain. India mein ek specific category ka GST rate 18% fix hota hai aur program ke beech mein change nahi hona chahiye.

**Requirements:** Ek variable `gstRate` declare karein jisko koi dobara reassign na kar sake. Ek function complete karein jo price mein GST add karke total return kare.

**Starter Code:**

```javascript
// TODO: Declare gstRate here with the correct keyword and set it to 0.18

function calculateTotal(price) {
  // TODO: Calculate and return price + (price * gstRate)
}
```

**Test Cases:**

- `calculateTotal(100)` -> Expected Output: `118`
- `gstRate = 0.20` -> Expected Output: Error (TypeError: Assignment to constant variable)

## Q2: Dynamic Score Tracker

**Scenario (Problem):** Ek cricket game app ban rahi hai jahan player ka score har ball ke baad update hota rehta hai.

**Requirements:** Ek variable `playerScore` banayein jo update ho sake. Shuru mein iski value 0 hogi. Ek function `addRuns(runs)` banayein jo is score mein runs add kare aur naya score return kare.

**Starter Code:**

```javascript
// TODO: Declare playerScore using the correct keyword and initialize to 0

function addRuns(runs) {
  // TODO: Add runs to playerScore and return it
}
```

**Test Cases:**

- `addRuns(4)` -> Expected Output: `4`
- `addRuns(6)` -> Expected Output: `10`

## Q3: Legacy Code Greeting

**Scenario (Problem):** Aap ek purane project par kaam kar rahe hain (legacy code) jahan ES6 features allowed nahi hain. Aapko purane tarike se variable declare karna hai.

**Requirements:** `var` keyword ka use karke ek variable `userName` banayein aur usme "Rahul" store karein. Ek function `greetUser()` banayein jo "Hello, Rahul!" return kare.

**Starter Code:**

```javascript
// TODO: Declare userName using var

function greetUser() {
  // TODO: Return greeting string
}
```

**Test Cases:**

- `greetUser()` -> Expected Output: `"Hello, Rahul!"`

## Q4: The Mutable Const

**Scenario (Problem):** Aapke paas shopping cart mein items ki ek list hai. Cart ka reference change nahi hona chahiye (isliye const use kiya hai), par humein usme naye items add karne aane chahiye.

**Requirements:** `cart` naam ka ek `const` array diya gaya hai. Ek function `addToCart(item)` banayein jo is array mein naya item `push` kare aur updated array return kare.

**Starter Code:**

```javascript
const cart = ["Shoes", "Watch"];

function addToCart(newItem) {
  // TODO: Add newItem to cart array and return cart
}
```

**Test Cases:**

- `addToCart("Bag")` -> Expected Output: `["Shoes", "Watch", "Bag"]`

## Q5: Delayed Initialization

**Scenario (Problem):** User registration form submit hone par humein `userId` milti hai. Shuru mein yeh empty hoti hai aur baad mein assign ki jati hai.

**Requirements:** Ek variable `userId` declare karein (bina value ke). Ek function `setUserId(id)` banayein jo is variable mein id set kare aur use return kare. Use the best ES6 keyword for this.

**Starter Code:**

```javascript
// TODO: Declare userId without initializing it

function setUserId(id) {
  // TODO: Assign id to userId and return it
}
```

**Test Cases:**

- Before calling function: `userId` is `undefined`.
- `setUserId(101)` -> Expected Output: `101`
