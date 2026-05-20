# Module 4: The Empty States ("Undefined" & "Null")

## Q1: The Unassigned Variable

**Scenario:** Jab aap koi variable banate hain par usme kuch dalte nahi, toh JavaScript khud use ek value de deta hai. Wo value kya hai?

**Requirements:** Ek variable `userLocation` declare karein (bina initialize kiye) aur use return karein.

**Starter Code:**

```javascript
function getEmptyVar() {
  // TODO: Declare userLocation without a value and return it
}
```

**Test Cases:**

- `getEmptyVar()` -> Expected: `undefined`

## Q2: Setting Intentionally to Null

**Scenario:** Jab user logout karta hai, toh humein uska session data explicitly khali (empty) dikhana hota hai. Uske liye hum ek specific keyword use karte hain jiska matlab hai "no value".

**Requirements:** `session` variable ko explicitly wo empty data type assign karein aur return karein.

**Starter Code:**

```javascript
function clearSession() {
  let session = "Active";
  // TODO: Change session to represent an intentional empty state
  return session;
}
```

**Test Cases:**

- `clearSession()` -> Expected: `null`

## Q3: Missing Function Arguments

**Scenario:** Jab kisi function ko call karte waqt argument nahi diya jata, to JS parameter ko default value kya assign karta hai?

**Requirements:** Function jisme `param` hai, bas us `param` ko return karein. Hum ise bina argument diye test karenge.

**Starter Code:**

```javascript
function checkMissingArg(param) {
  // TODO: Just return param
}
```

**Test Cases:**

- `checkMissingArg()` -> Expected: `undefined`

## Q4: The typeof Null Bug

**Scenario:** JavaScript mein ek purana bug hai. Jab aap `null` ka `typeof` check karte hain, toh wo "null" nahi balki kuch aur btata hai!

**Requirements:** `null` value ka type return karein.

**Starter Code:**

```javascript
function getNullType() {
  // TODO: Return the typeof null
}
```

**Test Cases:**

- `getNullType()` -> Expected: `"object"`

## Q5: Loose Equality of Emptiness

**Scenario:** `null` aur `undefined` alag-alag hain, par loose equality (`==`) mein JavaScript inhe bhai-bhai maanta hai.

**Requirements:** `null == undefined` ka logic check karein aur result return karein.

**Starter Code:**

```javascript
function areTheyLooselyEqual() {
  // TODO: Return the result of (null == undefined)
}
```

**Test Cases:**

- `areTheyLooselyEqual()` -> Expected: `true`

## Q6: Strict Equality of Emptiness

**Scenario:** Lekin strict equality (`===`) ke mamle mein ye dono strict apne data types ko follow karte hain.

**Requirements:** `null === undefined` ka comparison result return karein.

**Starter Code:**

```javascript
function areTheyStrictlyEqual() {
  // TODO: Return the result of (null === undefined)
}
```

**Test Cases:**

- `areTheyStrictlyEqual()` -> Expected: `false`

## Q7: Checking for Undefined Explicitly

**Scenario:** Ek API response mein humein confirm karna hai ki field missing hai ya nahi (yaani strictly `undefined` hai).

**Requirements:** Ek function likhein jo `true` return kare agar parameter completely `undefined` ho.

**Starter Code:**

```javascript
function isUndefined(val) {
  // TODO: Strictly check if val is undefined
}
```

**Test Cases:**

- `isUndefined(undefined)` -> Expected: `true`
- `isUndefined(null)` -> Expected: `false`

## Q8: Default Fallback (The OR trick)

**Scenario:** Ek user ne apna bio nahi daala (yani `undefined` hai). UI break na ho isliye humein default text "No bio available" dikhana hai.

**Requirements:** Logical OR (`||`) operator ka use karke default fallback pattern banayein. Agar bio falsy hai, to default text return karein.

**Starter Code:**

```javascript
function getBio(userBio) {
  // TODO: Return userBio, OR return "No bio available" if it is undefined
}
```

**Test Cases:**

- `getBio("I love coding")` -> Expected: `"I love coding"`
- `getBio(undefined)` -> Expected: `"No bio available"`
