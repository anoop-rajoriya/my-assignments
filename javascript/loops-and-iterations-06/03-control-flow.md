# Module 3: Control Flow (break & continue)

## Q1: The VIP Entry (Skip Queue)

**Scenario:** Mandir ki line mein kuch VIPs hain. Scanner jab ["Normal", "VIP", "Normal"] read karega, toh VIP ko process nahi karna (skip karna hai).
**Requirements:** for loop lagayein. Agar item "VIP" ho toh continue keyword se iterarion skip kar dein. Jo Normal hain unhe naye array me push karein.
**Starter Code:**

```javascript
function getNormalQueue(queue) {
  // TODO: Use continue to skip "VIP"
}
```

**Test Cases:**

- getNormalQueue(["Normal", "VIP", "Normal"]) -> Expected: ["Normal", "Normal"]
- getNormalQueue(["VIP", "VIP"]) -> Expected: []
- getNormalQueue(["Normal"]) -> Expected: ["Normal"]

## Q2: Red Light Halt! (Break)

**Scenario:** Gadi traffic signals ki array follow kar rahi hai: ["Green", "Yellow", "Red", "Green"]. Jaise hi "Red" aaye, aage dekhna band. Gadi ruk jani chahiye.
**Requirements:** for loop se signals traverse karein. Agar "Red" aaye toh break karein. Baki signals count karein (kitne cross kiye).
**Starter Code:**

```javascript
function countSignalsCrossed(signals) {
  // TODO: Break the loop on "Red" and return the count
}
```

**Test Cases:**

- countSignalsCrossed(["Green", "Green", "Red", "Yellow"]) -> Expected: 2
- countSignalsCrossed(["Red", "Green"]) -> Expected: 0
- countSignalsCrossed(["Green"]) -> Expected: 1

## Q3: Searching the Lost Keys (Break early)

**Scenario:** 10 bags hain. Jaise hi keys mil jayein, baaki bags check karne ki zaroorat nahi. Time bachao!
**Requirements:** Agar array item "Keys" hai, toh ek variable foundAt mein uska index save karke immediately break karein.
**Starter Code:**

```javascript
function findKeys(bags) {
  // TODO: Return the index where keys are found, use break. Return -1 if not found.
}
```

**Test Cases:**

- findKeys(["Book", "Keys", "Pen"]) -> Expected: 1
- findKeys(["Keys", "Laptop"]) -> Expected: 0
- findKeys(["Wallet", "Phone"]) -> Expected: -1

## Q4: Pure Veg Buffet (Continue)

**Scenario:** Shaadi ki daawat mein, ek veg aadmi sab items dekh raha hai. Agar koi dish "Non-Veg" hai toh wo dekhega hi nahi (skip karega) aur agli dish par jayega.
**Requirements:** Agar dish "Non-Veg" ho toh continue karein. Baaki dishes naye array mein collect karein.
**Starter Code:**

```javascript
function getVegPlate(buffetItems) {
  // TODO: Use continue to skip "Non-Veg"
}
```

**Test Cases:**

- getVegPlate(["Paneer", "Non-Veg", "Dal"]) -> Expected: ["Paneer", "Dal"]
- getVegPlate(["Non-Veg"]) -> Expected: []
- getVegPlate(["Roti", "Rice"]) -> Expected: ["Roti", "Rice"]

## Q5: Daily Step Goal Met!

**Scenario:** Fitness watch me din ka goal 10,000 steps hai. Steps batches mein add ho rahe hain. Jaise hi sum >= 10000 ho, watch counting notify kar deti hai (loop break).
**Requirements:** Sum karte waqt break lagayein jaise hi total >= 10000 ho. Kitne batches of steps lage wo return karein.
**Starter Code:**

```javascript
function batchesToGoal(stepBatches) {
  // TODO: Sum the array, break if total >= 10000, return index + 1
}
```

**Test Cases:**

- batchesToGoal([4000, 5000, 2000, 1000]) -> Expected: 3
- batchesToGoal([12000, 100]) -> Expected: 1
- batchesToGoal([1000, 1000]) -> Expected: 2 (Even if goal not met, it returns total batches checked)

## Q6: Avoiding Out-of-Stock Items

**Scenario:** Cart check out karte waqt, API check karti hai ki kya array ke andar "OOS" (Out of Stock) item hai. Usko hata kar baki bill mein jodein.
**Requirements:** Price ka array hai. Agar price string "OOS" hai toh continue. Warna Number me sum karein.
**Starter Code:**

```javascript
function billValidItems(prices) {
  // TODO: Sum valid numbers, continue if "OOS"
}
```

**Test Cases:**

- billValidItems([100, "OOS", 50]) -> Expected: 150
- billValidItems(["OOS", "OOS"]) -> Expected: 0
- billValidItems([10, 20]) -> Expected: 30

## Q7: Fastag Toll Plaza Logic

**Scenario:** Toll plaza par gaadiyan aati hain. ["Valid", "Invalid", "Valid"]. Jo valid hain wo seedhe cross karti hain. Jiske paas Invalid fastag hai, use cash dena padega (process rukega nahi, par skip hogi checking mechanism normal wali).
_Correction_: Let's make it simpler. Count the valid fastags. If "Police" vehicle comes, break the whole queue check immediately out of respect.
**Requirements:** for loop karein. Agar "Police" mile toh break. Agar "Invalid" mile toh continue. "Valid" ko count karein.
**Starter Code:**

```javascript
function countTollCrossings(queue) {
  // TODO: Implement logic with continue and break
}
```

**Test Cases:**

- countTollCrossings(["Valid", "Invalid", "Valid"]) -> Expected: 2
- countTollCrossings(["Valid", "Police", "Valid"]) -> Expected: 1
- countTollCrossings(["Invalid", "Police"]) -> Expected: 0

## Q8: The First Defective Item

**Scenario:** Quality assurance line par items check ho rahe hain. Agar array mein koi "Defective" item aaye, to line wahi rok do (break) aur defect ka index return karo.
**Requirements:** Array traverse karein. "Defective" milte hi uska index return karein. Agar na mile to -1.
**Starter Code:**

```javascript
function findDefect(productionLine) {
  // TODO: Use loop and break logic
}
```

**Test Cases:**

- findDefect(["Good", "Good", "Defective", "Good"]) -> Expected: 2
- findDefect(["Good", "Good"]) -> Expected: -1
- findDefect(["Defective"]) -> Expected: 0

## Q9: Skipping Vowels (Consonant Generator)

**Scenario:** Secret code banane ke liye kisi message se saare vowels (a, e, i, o, u) hatane hain.
**Requirements:** for loop lagakar characters check karein. Agar character vowel hai toh continue. Baaki characters naye string mein jodkar return karein.
**Starter Code:**

```javascript
function removeVowels(message) {
  // TODO: Skip vowels using continue
}
```

**Test Cases:**

- removeVowels("hello") -> Expected: "hll"
- removeVowels("javascript") -> Expected: "jvscrpt"
- removeVowels("apple") -> Expected: "ppl"

## Q10: Battery Saver Mode (Break)

**Scenario:** Phone background apps close kar raha hai (array of apps). Jaise hi battery level 15% ke barabar ya usse kam par gire, closing process immediately ruk jana chahiye.
**Requirements:** appsClosed count karein. Ek battery parameter har app close hone par -2% girta hai. Agar battery <= 15 ho, toh loop break karein.
**Starter Code:**

```javascript
function closeApps(totalApps, battery) {
  // TODO: Break when battery <= 15
}
```

**Test Cases:**

- closeApps(5, 20) -> Expected: 2 (App1 drops battery to 18, App2 to 16, App3 would drop to 14 so it breaks before closing? Wait, let's specify: drop happens _after_ closing. If battery is 20, close App1 -> battery 18. Close App2 -> battery 16. Close App3 -> battery 14 (<= 15, break). Apps closed: 3.) Let's standardize logic: if(battery <= 15) break; closeApp; battery -= 2;
- Let's refine:
  closeApps(5, 20) -> Expected: 3 (Ends at 14)
  closeApps(2, 100) -> Expected: 2
  closeApps(4, 15) -> Expected: 0
