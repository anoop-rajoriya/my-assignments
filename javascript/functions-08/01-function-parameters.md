# Module 1: Function Parameters (Default, Rest) & `arguments` Object

## Q1: Chai ki Chini (Default Parameters)

**Scenario:** Tapri par chai order karte waqt agar customer chini (sugar) ki matra na bataye, toh bhaiya default 2 chammach dalte hain.
**Requirements:** `sugar` parameter ko default value `2` assign karein.
**Starter Code:**

```javascript
function makeChai(type, sugar = /* TODO */) {
  return `Making ${type} chai with ${sugar} spoons of sugar`;
}

```

**Test Cases:**

- `makeChai("Masala", 3)` -> Expected: `"Making Masala chai with 3 spoons of sugar"`
- `makeChai("Ginger")` -> Expected: `"Making Ginger chai with 2 spoons of sugar"`
- `makeChai("Black", 0)` -> Expected: `"Making Black chai with 0 spoons of sugar"`

## Q2: Auto Fare Calculator (Default Params)

**Scenario:** Auto bhaiya ka minimum base fare 50 Rs hota hai. Agar barish ho rahi ho toh surge lagta hai, warna nahi.
**Requirements:** `surge` ko default `0` rakhein aur `baseFare` (default 50) ke saath sum return karein.
**Starter Code:**

```javascript
function calculateAutoFare(baseFare = 50, surge = 0) {
  // TODO: Return total fare
}
```

**Test Cases:**

- `calculateAutoFare()` -> Expected: `50`
- `calculateAutoFare(50, 20)` -> Expected: `70`
- `calculateAutoFare(100)` -> Expected: `100`

## Q3: Samosa Party (Rest Parameters)

**Scenario:** Dadi se bahut log samose kharidte hain. Ek function mein multiple price values aayengi (kitni bhi ho sakti hain). Humein unka total chahiye.
**Requirements:** `...prices` (rest parameter) ka use karein. Array loop chalakar sum return karein.
**Starter Code:**

```javascript
function getSamosaPartyTotal(...prices) {
  // TODO: Loop through prices array and return sum
}
```

**Test Cases:**

- `getSamosaPartyTotal(10, 20, 30)` -> Expected: `60`
- `getSamosaPartyTotal(15, 15)` -> Expected: `30`
- `getSamosaPartyTotal()` -> Expected: `0`

## Q4: Sabji Mandi Items (Rest Params with normal params)

**Scenario:** Mandi mein ek main sabji aur baaki "extra" items aate hain.
**Requirements:** Pehla parameter `mainItem` ho aur baaki sab `...extras` mein jaayein. Ek string format karke return karein.
**Starter Code:**

```javascript
function getMandiList(mainItem, ...extras) {
  // TODO: Return "Main: [mainItem], Extras: [count of extras]"
}
```

**Test Cases:**

- `getMandiList("Aloo", "Pyaz", "Mirchi")` -> Expected: `"Main: Aloo, Extras: 2"`
- `getMandiList("Gobhi")` -> Expected: `"Main: Gobhi, Extras: 0"`
- `getMandiList("Bhindi", "Dhaniya")` -> Expected: `"Main: Bhindi, Extras: 1"`

## Q5: The Legacy Calculator (Arguments Object)

**Scenario:** ES6 ke Rest parameters se pehle, JS developers `arguments` object use karte the. Ye array nahi balki ek "Array-like" object hota hai.
**Requirements:** `arguments` object ki length tak loop chalakar saare arguments ko sum karein.
**Starter Code:**

```javascript
function legacySum() {
  // TODO: Use the 'arguments' keyword inside a loop to calculate total
}
```

**Test Cases:**

- `legacySum(5, 10, 15)` -> Expected: `30`
- `legacySum(100, 200)` -> Expected: `300`
- `legacySum()` -> Expected: `0`

## Q6: Maximum Temperature (Arguments Object)

**Scenario:** Mausam vibhag (Weather Dept) random temperatures bhejta hai. Hume sabse bada temperature nikalna hai bina `Math.max` ya arrays use kiye.
**Requirements:** `arguments` object par loop lagayein aur sabse maximum value dhoondh kar return karein.
**Starter Code:**

```javascript
function findHighestTemp() {
  // TODO: Iterate arguments to find the maximum value. Return -Infinity if empty.
}
```

**Test Cases:**

- `findHighestTemp(30, 45, 20)` -> Expected: `45`
- `findHighestTemp(10)` -> Expected: `10`
- `findHighestTemp()` -> Expected: `-Infinity`

## Q7: Wedding Guest Combiner (Rest Params)

**Scenario:** Card par "Family Name" aur uske baad "Bacho ke naam" print hone hain.
**Requirements:** Ek array return karein jisme pehla item `family` ho aur baaki `...kids` hon.
**Starter Code:**

```javascript
function formatGuestList(family, ...kids) {
  // TODO: Combine into a single array and return
}
```

**Test Cases:**

- `formatGuestList("Sharma", "Ravi", "Neha")` -> Expected: `["Sharma", "Ravi", "Neha"]`
- `formatGuestList("Gupta")` -> Expected: `["Gupta"]`
- `formatGuestList("Verma", "Rahul")` -> Expected: `["Verma", "Rahul"]`

## Q8: The strict mode 'arguments' trap

**Scenario:** Arrow functions ke andar `arguments` object kaam nahi karta. Agar use karoge toh error aayega.
**Requirements:** Ek standard `function` banayein jo `arguments[0]` return kare.
**Starter Code:**

```javascript
function getFirstArgument() {
  // TODO: Safely return the first item from the arguments object
}
```

**Test Cases:**

- `getFirstArgument("Hello", "World")` -> Expected: `"Hello"`
- `getFirstArgument(99, 100)` -> Expected: `99`
- `getFirstArgument()` -> Expected: `undefined`

## Q9: Order Discounter (Mixed Default + Rest)

**Scenario:** Zomato order mein base discount default hai, par items alag se aate hain.
**Requirements:** Pehle total calculate karein `...prices` se, fir `discount` (default 10) subtract karein.
**Starter Code:**

```javascript
function calculateDiscountedTotal(discount = 10, ...prices) {
  // TODO: Sum prices and subtract discount
}
```

**Test Cases:**

- `calculateDiscountedTotal(20, 100, 50)` -> Expected: `130`
- `calculateDiscountedTotal(undefined, 100, 50)` -> Expected: `140` (Defaults to 10)
- `calculateDiscountedTotal(0, 100)` -> Expected: `100`

## Q10: Combining Multiple Arrays (Rest + Spread)

**Scenario:** ISRO team array aur NASA team array ko mila kar ek joint mission team banani hai parameter levels pe.
**Requirements:** `...teams` parameter use karein. (Ye array of arrays ban jayega). Unhe ek single flat array mein convert karein using nested loop.
**Starter Code:**

```javascript
function createJointMission(...teams) {
  // teams looks like [ ["A", "B"], ["C"] ]
  // TODO: Manually flatten into a 1D array
}
```

**Test Cases:**

- `createJointMission(["A", "B"], ["C", "D"])` -> Expected: `["A", "B", "C", "D"]`
- `createJointMission(["X"])` -> Expected: `["X"]`
- `createJointMission([], ["Y"])` -> Expected: `["Y"]`

## Q11: Argument Fallback to Array

**Scenario:** Ek purani kirana API function mein `arguments` object aata hai, jisme array methods `.push()` nahi chalte.
**Requirements:** `arguments` object ki length padhein aur `for` loop ka use karke usko ek asli Array `[]` mein convert karke return karein.
**Starter Code:**

```javascript
function convertArgumentsToArray() {
  // TODO: Convert 'arguments' to a real array and return it
}
```

**Test Cases:**

- `convertArgumentsToArray(1, 2, 3)` -> Expected: `[1, 2, 3]`
- `convertArgumentsToArray("A", "B")` -> Expected: `["A", "B"]`
- `convertArgumentsToArray()` -> Expected: `[]`

## Q12: Default Object Fallback

**Scenario:** User profile bante waqt agar settings object na bheja jaye toh system default `{ theme: "dark" }` assume karta hai.
**Requirements:** Function parameter mein default object set karein.
**Starter Code:**

```javascript
function setupProfile(name, settings = /* TODO */) {
  return `${name} uses ${settings.theme} theme`;
}

```

**Test Cases:**

- `setupProfile("Raj", { theme: "light" })` -> Expected: `"Raj uses light theme"`
- `setupProfile("Aman")` -> Expected: `"Aman uses dark theme"`
- `setupProfile("Neha", { theme: "blue" })` -> Expected: `"Neha uses blue theme"`
