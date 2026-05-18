# Module 4: Variable Hoisting

## Q1: The `var` Hoisting Illusion

**Scenario (Problem):** JavaScript `var` declarations ko code ke top par hoist (move) kar deta hai, par initialization wahi rehti hai. Developer ne declare karne se pehle console.log likh diya hai aur output `undefined` aa raha hai.

**Requirements:** Hoisting ke rule ko samajhte hue code ko is tarah re-arrange karein ki output `"Rohan"` aaye, na ki `undefined`.

**Starter Code:**

```javascript
function showName() {
  // Fix the order to resolve the undefined output
  console.log(studentName);
  var studentName = "Rohan";
  return studentName;
}
```

**Test Cases:**

- `showName()` -> Console should log `"Rohan"`, returns `"Rohan"`

## Q2: Temporal Dead Zone (TDZ) Rescue

**Scenario (Problem):** `let` aur `const` bhi hoist hote hain, par jab tak wo initialize na ho jayein, unhe access karne par `ReferenceError` aata hai (is period ko TDZ bolte hain).

**Requirements:** Neeche diye gaye code mein error aa raha hai. Isko theek karein taaki TDZ avoid ho sake.

**Starter Code:**

```javascript
function getCity() {
  // Fix this code to avoid ReferenceError
  let message = `I live in ${city}`;
  let city = "Mumbai";
  return message;
}
```

**Test Cases:**

- `getCity()` -> Expected Output: `"I live in Mumbai"` (without throwing errors)

## Q3: Hoisted Functions vs Function Expressions

**Scenario (Problem):** Normal functions hoist hote hain aur unhe declaration se pehle call kiya ja sakta hai. Lekin variables mein store kiye gaye functions (expressions/arrow functions) ke saath aisa nahi hota.

**Requirements:** Code me error aa raha hai kyunki `greet()` variable initialization se pehle call ho raha hai. Code ko fix karein taaki yeh successfully run ho.

**Starter Code:**

```javascript
// TODO: Fix the order so greet can be called safely
let result = greet("Alice");

const greet = function (name) {
  return `Welcome, ${name}!`;
};
```

**Test Cases:**

- The script should run without `ReferenceError`.
- Value of `result` -> Expected Output: `"Welcome, Alice!"`

## Q4: Hoisting Inside a Function Trap

**Scenario (Problem):** Ek function ke andar hoisting hone ki wajah se, if-block ke andar wala `var` declaration function ke top par hoist ho gaya hai, jisse output badal gaya hai.

**Requirements:** `var` keyword ko hta kar ES6 block-scoped keyword lagayein taaki if-block ke baahar wala `msg` override na ho.

**Starter Code:**

```javascript
function displayMessage(condition) {
  var msg = "Global Hello";
  if (condition) {
    // TODO: Fix this declaration so it doesn't hoist and override the outer msg
    var msg = "Block Hello";
    return msg;
  }
  return msg;
}
```

**Test Cases:**

- `displayMessage(true)` -> Expected Output: `"Block Hello"`
- `displayMessage(false)` -> Expected Output: `"Global Hello"` (Using `var` in the starter code would overwrite this even during parsing due to hoisting in some tricky scopes, switching to `let` makes it predictable).

## Q5: The Strict Initialization Pattern

**Scenario (Problem):** Ek game start hone se pehle zaroori hai ki `playerReady` set ho. Developer ne declare neeche kiya hai aur use upar kar liya hai.

**Requirements:** Is bug ko fix karein. Code structure theek karein taaki variable declare aur initialize pehle ho aur function baad me use call kare.

**Starter Code:**

```javascript
function checkGameStatus() {
  // Fix the order to prevent hoisting bugs
  if (isReady === true) {
    return "Start Game";
  } else {
    return "Wait";
  }
}

var isReady = true;
// call checkGameStatus() here
```

**Test Cases:**

- `checkGameStatus()` must return `"Start Game"` and `isReady` must be defined _before_ the function is executed in the final code layout.
