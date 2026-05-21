# Module 2: The Menu & Choices (`switch...case`)

## Q1: Chai Tapri ka Menu

**Scenario:** Tapri par chai ke sizes hote hain: "cutting" (10 Rs), "full" (20 Rs), "kulhad" (25 Rs).

**Requirements:** `switch...case` ka use karein aur size ke hisaab se price (Number) return karein. Default case mein 0 return karein.

**Starter Code:**

```javascript
function getChaiPrice(size) {
  // TODO: Use switch-case to return 10, 20, or 25
}
```

**Test Cases:**

- `getChaiPrice("kulhad")` -> Expected: `25`
- `getChaiPrice("jumbo")` -> Expected: `0` (Hits default)

## Q2: Panipuri ka Special Pani

**Scenario:** Panipuri bhaiya ke paas 4 tarah ka pani hai. "pudina", "jeera", "hing", aur "khatta".

**Requirements:** `switch` use karein. "hing" ke liye "Digestion good", "pudina" ke liye "Refreshing", default mein "Standard Pani" return karein.

**Starter Code:**

```javascript
function getPaniFeedback(paniType) {
  // TODO: Use switch-case to return correct strings
}
```

**Test Cases:**

- `getPaniFeedback("hing")` -> Expected: `"Digestion good"`
- `getPaniFeedback("meetha")` -> Expected: `"Standard Pani"`

## Q3: Samosa Dadi ka "Din ke hisaab se Special"

**Scenario:** Dadi har din alag samosa banati hain. Monday ko "Aloo", Wednesday ko "Dal", Sunday ko "Paneer". Baaki din "Mix Veg".

**Requirements:** `day` (String) par `switch` lagayein. Baaki sabhi dino ke liye (default) "Mix Veg" return karein.

**Starter Code:**

```javascript
function getSpecialSamosa(day) {
  // TODO: Return Samosa type based on the day
}
```

**Test Cases:**

- `getSpecialSamosa("Sunday")` -> Expected: `"Paneer"`
- `getSpecialSamosa("Friday")` -> Expected: `"Mix Veg"`

## Q4: Pandit Ji Payment Methods

**Scenario:** Customer payment kis mode se kar raha hai. "cash" -> "Galle mein daalo", "upi" -> "Scanner dekho", "udhaar" -> "Khata book nikalo".

**Requirements:** Payment mode ke liye `switch` statement use karein.

**Starter Code:**

```javascript
function handlePaymentMethod(mode) {
  // TODO: Switch based on mode string
}
```

**Test Cases:**

- `handlePaymentMethod("upi")` -> Expected: `"Scanner dekho"`
- `handlePaymentMethod("udhaar")` -> Expected: `"Khata book nikalo"`

## Q5: Fruit Juice Options

**Scenario:** Juice wale bhaiya ke menu numbers pe chalte hain. 1 = "Mosambi", 2 = "Orange", 3 = "Mix Fruit".

**Requirements:** Number (1, 2, 3) par `switch` lagayein aur juice ka naam return karein. Default mein "Water" return karein.

**Starter Code:**

```javascript
function getJuiceByCode(codeNumber) {
  // TODO: Switch case for numbers
}
```

**Test Cases:**

- `getJuiceByCode(3)` -> Expected: `"Mix Fruit"`
- `getJuiceByCode(9)` -> Expected: `"Water"`

## Q6: Local Train Pass Check

**Scenario:** Mumbai local train pass 3 classes mein aata hai. "FC" (First Class), "SC" (Second Class), "AC" (AC Local).

**Requirements:** Ticket `classType` ke hisaab se check karein aur us class ka full form return karein. (e.g., "FC" -> "First Class").

**Starter Code:**

```javascript
function checkTrainClass(classType) {
  // TODO: Switch case for train class
}
```

**Test Cases:**

- `checkTrainClass("AC")` -> Expected: `"AC Local"`

## Q7: Vada Pav Spice Scale

**Scenario:** Vada pav thele par spice scale (number) 1 se 3 tak hai. 1 -> "Bacha party", 2 -> "Medium", 3 -> "Kaan se dhua".

**Requirements:** Switch case me strict matching hoti hai. Number `spiceLevel` ke basis par string return karein.

**Starter Code:**

```javascript
function getVadaPavSpice(spiceLevel) {
  // TODO: Use switch to map 1, 2, 3
}
```

**Test Cases:**

- `getVadaPavSpice(3)` -> Expected: `"Kaan se dhua"`

## Q8: Kirana Store Festival Offer

**Scenario:** Pandit ji tyoharon par discount tag lagate hain. Object se `festival` nikalkar check karein. "Diwali" -> 20%, "Holi" -> 15%, "Eid" -> 15%. (Notice: Holi aur Eid dono par 15%).

**Requirements:** `switch` mein fall-through technique (do cases ke liye ek code block) use karein for "Holi" aur "Eid". Discount number return karein.

**Starter Code:**

```javascript
function getFestivalDiscount(eventObj) {
  // eventObj looks like { festival: "Holi" }
  // TODO: Use switch on eventObj.festival
}
```

**Test Cases:**

- `getFestivalDiscount({ festival: "Holi" })` -> Expected: `15`
- `getFestivalDiscount({ festival: "Diwali" })` -> Expected: `20`

## Q9: The Dosa Selector

**Scenario:** Dosa type select karna hai. Array ke first item (index 0) mein dosa ka naam hai. "Masala", "Plain", "Rava".

**Requirements:** `orderArray[0]` par `switch` lagayein aur string return karein. (e.g. "Making Masala Dosa").

**Starter Code:**

```javascript
function prepareDosa(orderArray) {
  // TODO: Switch on orderArray[0]
}
```

**Test Cases:**

- `prepareDosa(["Rava", "Sambar"])` -> Expected: `"Making Rava Dosa"`

## Q10: Auto Bhaiya Meter Error Codes

**Scenario:** Auto ka digital meter kabhi kabhi error code deta hai. 'E1' -> "Meter Kharab", 'E2' -> "Battery Low".

**Requirements:** Error code string ko switch case se parse karke human-readable error return karein.

**Starter Code:**

```javascript
function checkAutoMeter(errorCode) {
  // TODO: Return readable message based on E1 or E2
}
```

**Test Cases:**

- `checkAutoMeter("E2")` -> Expected: `"Battery Low"`
