# Module 2: The Conditionals (while & do...while)

## Q1: Filling the Water Tank

**Scenario:** Ghar ki motor chalu hai. Tanki har minute 10 liter bharti hai. Jab tak current volume capacity tak na pahunche, motor chalni chahiye.
**Requirements:** while loop use karein. Har iteration mein currentVolume ko 10 badhayein aur minutes variable ko 1. Total minutes return karein.
**Starter Code:**

```javascript
function calculateTimeToFill(capacity, currentVolume) {
  // TODO: Use while loop to find total minutes taken
}
```

**Test Cases:**

- calculateTimeToFill(50, 0) -> Expected: 5
- calculateTimeToFill(100, 8) -> Expected: 2
- calculateTimeToFill(50, 5) -> Expected: 0

## Q2: ATM PIN Retry System

**Scenario:** User galat ATM PIN daal raha hai. Max 3 attempts allowed hain. (Array of attempts diya hai).
**Requirements:** while loop use karein jab tak attempts < 3 aur PIN galat ho. Jaise hi correct PIN "1234" aaye, "Success" return karein. Warna "Blocked".
**Starter Code:**

```javascript
function checkATM(pinsEntered) {
  const correctPin = "1234";
  // TODO: Check up to 3 pins using a while loop
}
```

**Test Cases:**

- checkATM(["1111", "2222", "1234", "9999"]) -> Expected: "Success"
- checkATM(["1111", "2222", "3333"]) -> Expected: "Blocked"
- checkATM(["1234"]) -> Expected: "Success"

## Q3: Halwai ki Mithai (do...while)

**Scenario:** Halwai dukan par aaya hai toh kam se kam ek (1) laddoo toh banayega hi, chahe demand 0 hi kyun na ho. Ye guarantee do...while loop deta hai.
**Requirements:** do...while use karein. Ek laddoosMade counter maintain karein. Condition ho: while (laddoosMade < demand). Return the total made.
**Starter Code:**

```javascript
function makeLaddoos(demand) {
  // TODO: Use do...while to ensure at least 1 laddoo is made
}
```

**Test Cases:**

- makeLaddoos(3) -> Expected: 3
- makeLaddoos(0) -> Expected: 1
- makeLaddoos(-5) -> Expected: 1

## Q4: Clearing the EMI Loan

**Scenario:** User par 10,000 ka loan hai. Har mahine wo 2,000 pay karta hai. Kitne mahino mein loan clear (0) hoga?
**Requirements:** while (balance > 0) lagayein. Har baar balance se emiAmount ghata dein aur months badhayein.
**Starter Code:**

```javascript
function monthsToClearLoan(balance, emiAmount) {
  // TODO: Return number of months
}
```

**Test Cases:**

- monthsToClearLoan(10000, 2000) -> Expected: 5
- monthsToClearLoan(5000, 1500) -> Expected: 4 (Takes 4 months: 1500, 1500, 1500, 500)
- monthsToClearLoan(0, 1000) -> Expected: 0

## Q5: ISRO Rocket Countdown

**Scenario:** Rocket launch hone se pehle reverse countdown hota hai.
**Requirements:** while loop use karein jahan timer > 0 ho. Har number ko ek array mein daalein. Aakhir mein array mein "Liftoff!" push karke return karein.
**Starter Code:**

```javascript
function launchCountdown(timer) {
  // TODO: Return array [timer, timer-1, ..., "Liftoff!"]
}
```

**Test Cases:**

- launchCountdown(3) -> Expected: [3, 2, 1, "Liftoff!"]
- launchCountdown(1) -> Expected: [1, "Liftoff!"]
- launchCountdown(0) -> Expected: ["Liftoff!"]

## Q6: Next Power of 2 (Memory Allocation)

**Scenario:** Computer RAM hamesha 2 ki powers mein hoti hai (2, 4, 8, 16, 32). Agar user ne 10 GB mangi toh use 16 GB milti hai.
**Requirements:** while loop se next power of 2 nikalein. Shuru karein power = 1. Jab tak power < input, use 2 se multiply karein.
**Starter Code:**

```javascript
function getRAMSize(requestedSize) {
  // TODO: Find the nearest greater or equal power of 2
}
```

**Test Cases:**

- getRAMSize(10) -> Expected: 16
- getRAMSize(32) -> Expected: 32
- getRAMSize(3) -> Expected: 4

## Q7: Removing from the Stack (pop loop)

**Scenario:** Dadi purane kapde trunk (array) se ek-ek karke tab tak nikal rahi hain jab tak unhe "Lal Saree" na mil jaye.
**Requirements:** while loop aur .pop() method ka use karein. Array tab tak pop karein jab tak last element "Lal Saree" na ho. Bacha hua trunk array return karein.
**Starter Code:**

```javascript
function searchTrunk(trunkItems) {
  // TODO: Pop items until "Lal Saree" is found or array is empty
}
```

**Test Cases:**

- searchTrunk(["Suit", "Lal Saree", "Jeans"]) -> Expected: ["Suit", "Lal Saree"]
- searchTrunk(["Shirt", "Pant"]) -> Expected: [] (If not found, trunk becomes empty)
- searchTrunk(["Lal Saree", "Shirt"]) -> Expected: ["Lal Saree"]

## Q8: The Chutta Machine (Coin Dispenser)

**Scenario:** Machine hamesha pehle 10 ke sikke deti hai jab tak de sakti hai.
**Requirements:** amount me se 10 subtract karte rahein while (amount >= 10) aur ek tensCount badhate rahein. Finally return the count of 10s.
**Starter Code:**

```javascript
function getTensCoins(amount) {
  // TODO: Use while loop to extract 10s
}
```

**Test Cases:**

- getTensCoins(45) -> Expected: 4
- getTensCoins(9) -> Expected: 0
- getTensCoins(100) -> Expected: 10

## Q9: Digit Sum (Sum of Digits)

**Scenario:** Numerology wale pandit ji kisi bhi bade number (jaise 145) ke digits ka sum nikalte hain (1 + 4 + 5 = 10).
**Requirements:** while (num > 0) use karein. Har baar num % 10 se aakhiri digit nikal kar sum mein jodein, aur Math.floor(num / 10) se number chota karein.
**Starter Code:**

```javascript
function sumOfDigits(num) {
  // TODO: Calculate digit sum using modulo and division
}
```

**Test Cases:**

- sumOfDigits(145) -> Expected: 10
- sumOfDigits(99) -> Expected: 18
- sumOfDigits(7) -> Expected: 7

## Q10: Waiting for the OTP (do...while)

**Scenario:** System SMS tab tak bhejne ki koshish karega jab tak delivery success na ho jaye. do...while lagayein kyunki ek koshish (attempt) toh confirm hogi.
**Requirements:** Ek array networkStatus diya hai. Ek index maintain karein. do..while tab tak chale while (status !== "Success"). Return kitne attempts lage.
**Starter Code:**

```javascript
function sendOTP(networkStatusArray) {
  // TODO: Count attempts until "Success" is encountered
}
```

**Test Cases:**

- sendOTP(["Fail", "Fail", "Success"]) -> Expected: 3
- sendOTP(["Success", "Fail"]) -> Expected: 1
- sendOTP(["Fail"]) -> Expected: 1 (Loop stops reading safely if array ends, though in real life it hangs. Assume "Success" is always eventually present for this logic). Let's fix test case: sendOTP(["Fail", "Success"]) -> Expected: 2
