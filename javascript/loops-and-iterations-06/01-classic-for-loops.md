# Module 1: The Classic for Loop (Counting & Arrays)

## Q1: Virat's Total Runs

**Scenario:** Ek cricket match mein Virat ne har over mein kitne runs banaye, wo ek array mein store hain. Humein total runs calculate karne hain.
**Requirements:** for loop ka use karein. Array ke har element ko ek total variable mein add karein aur return karein.
**Starter Code:**

```javascript
function calculateTotalRuns(runsArray) {
  // TODO: Use a traditional for loop to calculate the sum
}
```

**Test Cases:**

- calculateTotalRuns([4, 6, 2, 0, 1]) -> Expected: 13
- calculateTotalRuns([0, 0, 0]) -> Expected: 0
- calculateTotalRuns([]) -> Expected: 0

## Q2: School ka Pahada (Multiplication Table)

**Scenario:** Bachpan mein hum table (pahada) yaad karte thay. Ek number diya jayega, aur aapko uska table 1 se 10 tak ek array mein return karna hai.
**Requirements:** for loop (1 to 10) chalayein. Har iteration mein num \* i ko ek naye array mein push karein.
**Starter Code:**

```javascript
function generateTable(num) {
  // TODO: Return an array containing the table of num
}
```

**Test Cases:**

- generateTable(2) -> Expected: [2, 4, 6, 8, 10, 12, 14, 16, 18, 20]
- generateTable(5) -> Expected: [5, 10, 15, 20, 25, 30, 35, 40, 45, 50]
- generateTable(0) -> Expected: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0]

## Q3: Alternate Days Medicine (Step Jump)

**Scenario:** Doctor ne dadi ko har alternate day (1 din chhodkar) dawa lene ko kaha hai. Humein 1 se days tak ke numbers mein se alternate days nikalne hain.
**Requirements:** for loop mein increment step ko i += 2 set karein. Result array mein push karein.
**Starter Code:**

```javascript
function getMedicineDays(totalDays) {
  // TODO: Loop starting from 1, jump by 2
}
```

**Test Cases:**

- getMedicineDays(5) -> Expected: [1, 3, 5]
- getMedicineDays(8) -> Expected: [1, 3, 5, 7]
- getMedicineDays(1) -> Expected: [1]

## Q4: Train ki Maximum Speed

**Scenario:** Vande Bharat train ki speed har 10 minute mein record hoti hai. Pata lagana hai ki journey ki sabse highest speed kya thi.
**Requirements:** for loop se array traverse karein. Ek maxSpeed variable maintain karein aur usko update karte rahein.
**Starter Code:**

```javascript
function getTopSpeed(speedRecords) {
  // TODO: Find and return the maximum number in the array
}
```

**Test Cases:**

- getTopSpeed([80, 120, 160, 90]) -> Expected: 160
- getTopSpeed([50, 50, 50]) -> Expected: 50
- getTopSpeed([]) -> Expected: 0 (Handle empty array)

## Q5: Name Reversal (Ulta Naam)

**Scenario:** Ek game mein user ke naam ko peeche se (reverse) display karna hai.
**Requirements:** String ki length se start karke 0 tak ulta for loop lagayein (i--). Characters ko jodkar naya string return karein.
**Starter Code:**

```javascript
function reverseName(name) {
  // TODO: Use a reverse for-loop to flip the string
}
```

**Test Cases:**

- reverseName("Aman") -> Expected: "namA"
- reverseName("Raj") -> Expected: "jaR"
- reverseName("") -> Expected: ""

## Q6: Counting Parle-G

**Scenario:** Dukan ke inventory array mein bahut saare biscuits hain. Humein count karna hai ki "Parle-G" kitni baar aaya hai.
**Requirements:** for loop lagayein. Agar element "Parle-G" ho, toh ek count variable ko badhayein.
**Starter Code:**

```javascript
function countParleG(inventory) {
  // TODO: Count occurrences of strictly "Parle-G"
}
```

**Test Cases:**

- countParleG(["Oreo", "Parle-G", "Monaco", "Parle-G"]) -> Expected: 2
- countParleG(["GoodDay", "Oreo"]) -> Expected: 0
- countParleG(["parle-g"]) -> Expected: 0 (Case-sensitive check)

## Q7: Filtering Adults for 'A' Rated Movie

**Scenario:** Ek cinema hall mein ticket counter par ages ki list aayi hai. Sirf 18 ya usse upar walon ko entry deni hai.
**Requirements:** for loop se check karein. Jo >= 18 hain, unhe ek naye array mein daalein aur return karein. (Do not use .filter()).
**Starter Code:**

```javascript
function getEligibleViewers(ages) {
  // TODO: Return a new array with ages >= 18
}
```

**Test Cases:**

- getEligibleViewers([12, 18, 25, 16]) -> Expected: [18, 25]
- getEligibleViewers([10, 15]) -> Expected: []
- getEligibleViewers([20, 30]) -> Expected: [20, 30]

## Q8: The Factorial Problem (Permutations)

**Scenario:** Shaadi mein 5 chairs par mehman kitne tareeko se baith sakte hain? Ye 5! (Factorial) se nikalta hai (5 _ 4 _ 3 _ 2 _ 1).
**Requirements:** for loop lagakar given n ka factorial calculate karein aur return karein.
**Starter Code:**

```javascript
function calculateSeatingWays(n) {
  // TODO: Calculate and return n!
}
```

**Test Cases:**

- calculateSeatingWays(5) -> Expected: 120
- calculateSeatingWays(3) -> Expected: 6
- calculateSeatingWays(0) -> Expected: 1 (Factorial of 0 is 1)

## Q9: Diwali Diyas (String Repetition)

**Scenario:** Chat par line se diye lagane hain. Ek diye ko "🪔" character se darshaya gaya hai.
**Requirements:** for loop ka use karke ek blank string mein utni baar "🪔" add karein jitna count mein diya hai.
**Starter Code:**

```javascript
function lightDiyas(count) {
  // TODO: Build and return the string of diyas
}
```

**Test Cases:**

- lightDiyas(3) -> Expected: "🪔🪔🪔"
- lightDiyas(1) -> Expected: "🪔"
- lightDiyas(0) -> Expected: ""

## Q10: Finding the First Even Number

**Scenario:** Lottery system mein array ka sabse pehla even number hi winner hota hai.
**Requirements:** for loop se traverse karein. Jaise hi pehla even number mile, use return karke function end kar dein. Agar koi na mile toh -1 return karein.
**Starter Code:**

```javascript
function getFirstEven(numbers) {
  // TODO: Return the very first even number, or -1
}
```

**Test Cases:**

- getFirstEven([1, 3, 4, 7, 8]) -> Expected: 4
- getFirstEven([1, 3, 5]) -> Expected: -1
- getFirstEven([2, 4, 6]) -> Expected: 2
