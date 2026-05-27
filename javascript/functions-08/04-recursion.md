# Module 4: Recursion & The Function Stack

## Q1: Countdown to Diwali

**Scenario:** Recursion matlab ek function khud ko wapas call kare tab tak jab tak ek "Base Case" hit na ho jaye. Diwali ka reverse countdown (10, 9... 0).
**Requirements:** Recursive function `countdown(n)` banayein jo ek array lautaaye `[n, n-1, ..., 0]`. Base case: agar `n === 0`, toh `[0]` return kare.
**Starter Code:**

```javascript
function countdown(n) {
  // TODO: Base case and recursive call
  if (n === 0) return [0];
  return [n].concat(countdown(n - 1));
}
```

**Test Cases:**

- `countdown(3)` -> Expected: `[3, 2, 1, 0]`
- `countdown(1)` -> Expected: `[1, 0]`
- `countdown(0)` -> Expected: `[0]`

## Q2: Factorial of Chairs (Seating Arrangements)

**Scenario:** 5 kurasiyan (chairs) kitne combination mein lag sakti hain? Ye factorial `n!` hota hai. `5 * 4 * 3 * 2 * 1`.
**Requirements:** Recursion se factorial nikalein. Base case: `n <= 1` ke liye `1` return karein.
**Starter Code:**

```javascript
function factorial(n) {
  // TODO: Calculate factorial recursively
}
```

**Test Cases:**

- `factorial(5)` -> Expected: `120`
- `factorial(3)` -> Expected: `6`
- `factorial(1)` -> Expected: `1`

## Q3: Numerology Digit Sum (Recursive)

**Scenario:** Pandit ji number ke digits ka sum nikal rahe hain. `123 -> 1+2+3 = 6`. Ise manually loop ki jagah recursion se karna hai.
**Requirements:** Number ka right-most digit nikalen (`num % 10`) aur function wapas call karein baaki hisse ke liye (`Math.floor(num / 10)`). Base case `num === 0`.
**Starter Code:**

```javascript
function sumDigits(num) {
  // TODO: Recursive sum of digits
}
```

**Test Cases:**

- `sumDigits(123)` -> Expected: `6`
- `sumDigits(99)` -> Expected: `18`
- `sumDigits(0)` -> Expected: `0`

## Q4: Endless Line Check (Recursive Length)

**Scenario:** Array ki `.length` property use kiye bina pata lagana hai ki array me kitne log hain. (Using array destruction `[first, ...rest]`).
**Requirements:** Recursive array length finder. Agar array khali hai toh `0`. Warna `1 + length(rest_of_array)`. Use `.slice(1)` to get the rest of array.
**Starter Code:**

```javascript
function getLength(arr) {
  // TODO: Return 0 if array is empty, else 1 + recursive call
}
```

**Test Cases:**

- `getLength([1, 2, 3])` -> Expected: `3`
- `getLength(["A", "B", "C", "D"])` -> Expected: `4`
- `getLength([])` -> Expected: `0`

## Q5: Ulta Naam (Recursive String Reversal)

**Scenario:** String ko ulta karna hai. "Ravi" -> "ivaR".
**Requirements:** Recursion ka use karein. Pura string barabar hai `last_character` + `reverse(remaining_string)`. Ya phir `reverse(remaining)` + `first_character`.
**Starter Code:**

```javascript
function reverseString(str) {
  // TODO: Recursively reverse string
  if (str === "") return "";
  return reverseString(str.substring(1)) + str.charAt(0);
}
```

**Test Cases:**

- `reverseString("Ravi")` -> Expected: `"ivaR"`
- `reverseString("JS")` -> Expected: `"SJ"`
- `reverseString("")` -> Expected: `""`

## Q6: Compound Interest Power (Exponentiation)

**Scenario:** Bank loan mein interest compound hota hai (Base ki Power). Ex: `2^3 = 8`.
**Requirements:** `power(base, exponent)` recursively calculate karein. Base case `exponent === 0` par `1` return kare.
**Starter Code:**

```javascript
function power(base, exp) {
  // TODO: Recursive power calculation
}
```

**Test Cases:**

- `power(2, 3)` -> Expected: `8`
- `power(5, 2)` -> Expected: `25`
- `power(10, 0)` -> Expected: `1`

## Q7: Stepping Stones (Fibonacci)

**Scenario:** Ek river mein stones hain. Har naye pathar par aane ke tareeke pichle do patharo ke tareeko ka sum hota hai. (Fibonacci sequence: 0, 1, 1, 2, 3, 5...).
**Requirements:** Recursive function `fibonacci(n)`. Base cases: `if (n === 0) return 0; if (n === 1) return 1;`. Recursive step: return `fibonacci(n-1) + fibonacci(n-2)`.
**Starter Code:**

```javascript
function fibonacci(n) {
  // TODO: Return the nth fibonacci number
}
```

**Test Cases:**

- `fibonacci(5)` -> Expected: `5`
- `fibonacci(6)` -> Expected: `8`
- `fibonacci(0)` -> Expected: `0`

## Q8: The Deep Matryoshka Boxes (Deep Flatten Array)

**Scenario:** Delivery me dabbe ke andar dabba, uske andar dabba hai: `[1, [2, [3, 4]]]`. Sabko baahar nikal kar ek normal array `[1, 2, 3, 4]` banana hai bina inbuilt `.flat()` use kiye.
**Requirements:** Array loop lagayein. Agar element array hai (`Array.isArray(el)`), usko recursively call karke result ko base array me jodein.
**Starter Code:**

```javascript
function flattenArray(arr) {
  let result = [];
  // TODO: Iterate over arr, if item is Array, recurse, else push to result
  return result;
}
```

**Test Cases:**

- `flattenArray([1, [2, [3]]])` -> Expected: `[1, 2, 3]`
- `flattenArray([[1, 2], [3, 4]])` -> Expected: `[1, 2, 3, 4]`
- `flattenArray([1, 2, 3])` -> Expected: `[1, 2, 3]`

## Q9: Palindrome Check ("Nitin")

**Scenario:** "Nitin" aage aur peeche se ek jaisa hota hai (Palindrome). Loop ke bajaye recursive algorithm use karna hai.
**Requirements:** Check karein if first char === last char. Agar haan, toh remaining inner string par wapas call lagayein. Base case: length 0 ya 1 ho toh true.
**Starter Code:**

```javascript
function isPalindrome(str) {
  // TODO: Recursive palindrome check (convert to lowercase first for simplicity if you want, but assume lowercase input)
}
```

**Test Cases:**

- `isPalindrome("racecar")` -> Expected: `true`
- `isPalindrome("hello")` -> Expected: `false`
- `isPalindrome("a")` -> Expected: `true`

## Q10: Function Call Stack Tracker (Simulated Hierarchy)

**Scenario:** Company mein Manager apne Lead ko call karta hai, Lead Dev ko call karta hai. Call stack trace samajhna zaroori hai.
**Requirements:** 3 functions hain `dev()`, `lead()`, `manager()`. `dev` return kare `"Task Done"`. `lead` return kare `dev() + " by Lead"`. `manager` return kare `lead() + " by Manager"`.
**Starter Code:**

```javascript
function dev() {
  return "Task Done";
}
function lead() {
  /* TODO */
}
function manager() {
  /* TODO */
}
```

**Test Cases:**

- `dev()` -> Expected: `"Task Done"`
- `lead()` -> Expected: `"Task Done by Lead"`
- `manager()` -> Expected: `"Task Done by Lead by Manager"`

## Q11: EMI Total Paid (Recursive Aggregation)

**Scenario:** Jab tak EMI pending hai, mahine ka amount sum me add hota jayega.
**Requirements:** `totalPaid(installmentsArray)`. Recursive logic: return `firstElement` + `totalPaid(restArray)`.
**Starter Code:**

```javascript
function totalPaid(installments) {
  // TODO: Recursively sum the array elements
}
```

**Test Cases:**

- `totalPaid([1000, 1000, 1000])` -> Expected: `3000`
- `totalPaid([500, 200])` -> Expected: `700`
- `totalPaid([])` -> Expected: `0`

## Q12: Replacing Spaces with Hyphens (URL Slug)

**Scenario:** Zomato URL me "masala dosa" ban jata hai "masala-dosa". Recursively string ka pehla space dhoond kar replace karein jab tak koi space na bache.
**Requirements:** `str.replace(" ", "-")` siraf pehle space ko replace karta hai. Base case: string mein space na ho `!str.includes(" ")`. Recursive step: call again with modified string.
**Starter Code:**

```javascript
function createSlug(str) {
  // TODO: Recursively replace spaces
}
```

**Test Cases:**

- `createSlug("paneer butter masala")` -> Expected: `"paneer-butter-masala"`
- `createSlug("tea")` -> Expected: `"tea"`
- `createSlug(" a b c ")` -> Expected: `"-a-b-c-"`
