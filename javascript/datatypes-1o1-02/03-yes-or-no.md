# Module 3: True or False ("Boolean")

## Q1: The Toggle Switch

**Scenario:** App mein Dark Mode ka switch hai. Agar current state `true` hai toh naba state `false` hona chahiye aur vice-versa.

**Requirements:** Logical NOT (`!`) operator use karke boolean value ko invert karein.

**Starter Code:**

```javascript
function toggleTheme(isDarkMode) {
  // TODO: Return the opposite of isDarkMode
}
```

**Test Cases:**

- `toggleTheme(true)` -> Expected: `false`
- `toggleTheme(false)` -> Expected: `true`

## Q2: Age Restriction

**Scenario:** Ek adult content website par entry ke liye user ki age kam se kam 18 saal honi chahiye.

**Requirements:** Comparison operator (`>=`) use karein. Return `true` agar age 18 ya usse badi hai.

**Starter Code:**

```javascript
function isAdult(age) {
  // TODO: Check condition and return boolean
}
```

**Test Cases:**

- `isAdult(20)` -> Expected: `true`
- `isAdult(16)` -> Expected: `false`

## Q3: Strict Equality Trap

**Scenario:** Jab aap API se ID receive karte hain to wo string `"10"` hoti hai, par database mein number `10` hota hai. `===` check data type bhi compare karta hai.

**Requirements:** `a` aur `b` ko strictly compare karein (`===`) aur result return karein.

**Starter Code:**

```javascript
function isStrictlyEqual(a, b) {
  // TODO: Return true if strictly equal
}
```

**Test Cases:**

- `isStrictlyEqual(5, 5)` -> Expected: `true`
- `isStrictlyEqual(5, "5")` -> Expected: `false`

## Q4: Loose Equality (Double Equals)

**Scenario:** Purane codebase mein type conversion automatic karana hai (jaise `"10" == 10`).

**Requirements:** `a` aur `b` ko loosely compare karein (`==`) aur result return karein.

**Starter Code:**

```javascript
function isLooselyEqual(a, b) {
  // TODO: Return true if loosely equal
}
```

**Test Cases:**

- `isLooselyEqual(5, "5")` -> Expected: `true`

## Q5: Logical AND (&&) - Dual Verification

**Scenario:** Ek user ka account tabhi activate hota hai jab uska `emailVerified` bhi true ho aur `phoneVerified` bhi true ho.

**Requirements:** Logical AND (`&&`) use karke check karein ki dono strict true hain ya nahi.

**Starter Code:**

```javascript
function isAccountActive(emailVerified, phoneVerified) {
  // TODO: Return true ONLY if both are true
}
```

**Test Cases:**

- `isAccountActive(true, true)` -> Expected: `true`
- `isAccountActive(true, false)` -> Expected: `false`

## Q6: Logical OR (||) - Multiple Login Options

**Scenario:** User apne account mein login kar sakta hai agar usne Username dala ho YA Email dala ho. Ek bhi mil jaye toh theek hai.

**Requirements:** Logical OR (`||`) use karke check karein.

**Starter Code:**

```javascript
function canAttemptLogin(hasUsername, hasEmail) {
  // TODO: Return true if at least one is true
}
```

**Test Cases:**

- `canAttemptLogin(false, true)` -> Expected: `true`
- `canAttemptLogin(false, false)` -> Expected: `false`

## Q7: Typeof Boolean

**Scenario:** Validate karna hai ki ek configuration flag boolean type ka hi hai.

**Requirements:** `typeof` check karein ki data Boolean hai.

**Starter Code:**

```javascript
function isBoolean(val) {
  // TODO: Return true if val is boolean
}
```

**Test Cases:**

- `isBoolean(true)` -> Expected: `true`
- `isBoolean("true")` -> Expected: `false`

## Q8: The Not-Equal Operator

**Scenario:** Aapko check karna hai ki user ka role "banned" nahi hona chahiye.

**Requirements:** Strict Not Equal (`!==`) operator ka use karein. Return `true` agar role "banned" nahi hai.

**Starter Code:**

```javascript
function isAllowed(role) {
  // TODO: Return true if role is NOT exactly "banned"
}
```

**Test Cases:**

- `isAllowed("user")` -> Expected: `true`
- `isAllowed("banned")` -> Expected: `false`
