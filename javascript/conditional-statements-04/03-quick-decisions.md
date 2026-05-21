# Module 3: The Quick Decisions (`Ternary Operator ? :`)

## Q1: The Sukhi Puri Demand

**Scenario:** Panipuri khaane ke baad end mein "Bhaiya ek sukhi puri dena!" compulsory hai. Agar customer ne 5 puri se zyada khayi hain tabhi sukhi puri milti hai.

**Requirements:** Sirf 1 line mein ternary operator (`? :`) use karke true ya false return karein based on `puriEaten > 5`.

**Starter Code:**

```javascript
function getsSukhiPuri(puriEaten) {
  // TODO: Return true if puriEaten > 5, else false using ternary
}
```

**Test Cases:**

- `getsSukhiPuri(6)` -> Expected: `true`
- `getsSukhiPuri(4)` -> Expected: `false`

## Q2: Samosa Garam Hai?

**Scenario:** Customer hamesha puchte hain "Samosa garam hai na?". Dadi check krti hain `isHot` boolean.

**Requirements:** Ternary operator se agar true hai toh "Garam hai", false hai toh "Thanda hai" return karein.

**Starter Code:**

```javascript
function checkSamosaTemp(isHot) {
  // TODO: Return exact string using ternary
}
```

**Test Cases:**

- `checkSamosaTemp(true)` -> Expected: `"Garam hai"`

## Q3: Chai Biscuit Combo

**Scenario:** Tapri par agar customer ka budget 15 Rs ya usse zyada hai, toh use "Chai + Parle-G" milta hai, warna "Sirf Chai".

**Requirements:** `budget >= 15` par ternary logic likhein aur string return karein.

**Starter Code:**

```javascript
function getChaiOrder(budget) {
  // TODO: Use ternary operator
}
```

**Test Cases:**

- `getChaiOrder(15)` -> Expected: `"Chai + Parle-G"`
- `getChaiOrder(10)` -> Expected: `"Sirf Chai"`

## Q4: Udhaar Limit Check

**Scenario:** Pandit ji ne udhaar limit 500 Rs set ki hai. Naya samaan tabhi milega jab current udhaar 500 se kam ho.

**Requirements:** Agar `currentUdhaar < 500` hai toh "Samaan le lo", warna "Pehle purana hisaab karo". Use Ternary.

**Starter Code:**

```javascript
function checkCreditLimit(currentUdhaar) {
  // TODO: One line ternary logic
}
```

**Test Cases:**

- `checkCreditLimit(600)` -> Expected: `"Pehle purana hisaab karo"`
- `checkCreditLimit(300)` -> Expected: `"Samaan le lo"`

## Q5: Zomato Delivery Fee

**Scenario:** Local delivery 2 km tak free hai, uske baad 20 Rs lagte hain.

**Requirements:** Ternary use karke agar `distance <= 2` hai toh 0 return karein, warna 20.

**Starter Code:**

```javascript
function getDeliveryFee(distance) {
  // TODO: Return Number 0 or 20 using ternary
}
```

**Test Cases:**

- `getDeliveryFee(1.5)` -> Expected: `0`
- `getDeliveryFee(3)` -> Expected: `20`

## Q6: Barish ka Thela Cover

**Scenario:** Panipuri bhaiya ka thela khule aasmaan ke niche hai. `isRaining` object property ke hisaab se tirpal (cover) lagana hai.

**Requirements:** `weatherObj.isRaining` true hai toh "Cover lagao", warna "Khula rakho".

**Starter Code:**

```javascript
function manageThela(weatherObj) {
  // TODO: Ternary check on object property
}
```

**Test Cases:**

- `manageThela({ isRaining: true })` -> Expected: `"Cover lagao"`

## Q7: Fresh Sabji Test

**Scenario:** Sabji mandi me sabji ki freshness 1 se 10 scale pe hoti hai. Agar freshness >= 8 hai tabhi thele par rakhenge.

**Requirements:** Ternary se return karein "Sale" (if >= 8) or "Throw" (if < 8).

**Starter Code:**

```javascript
function sabjiQualityCheck(freshnessScale) {
  // TODO: Return "Sale" or "Throw"
}
```

**Test Cases:**

- `sabjiQualityCheck(9)` -> Expected: `"Sale"`
- `sabjiQualityCheck(5)` -> Expected: `"Throw"`

## Q8: Momos Price Fixer

**Scenario:** Veg momos ki plate 40 Rs ki hai, Non-Veg ki 60 Rs.

**Requirements:** Boolean `isVeg` check karein. True hai toh Number 40 return karein, false pe 60. Use Ternary.

**Starter Code:**

```javascript
function getMomosPrice(isVeg) {
  // TODO: Return Number 40 or 60
}
```

**Test Cases:**

- `getMomosPrice(true)` -> Expected: `40`
- `getMomosPrice(false)` -> Expected: `60`

## Q9: The VIP Discount Array Check

**Scenario:** Pandit ji VIP customers ke naam ek array mein rakhte hain. Hume check karna hai agar customer list mein hai ya nahi.

**Requirements:** Array built-in method `.includes()` ke saath ternary lagayein. Agar customer `vipList` mein hai toh 10 return karein (discount), else 0.

**Starter Code:**

```javascript
function checkVIPDiscount(customerName, vipList) {
  // TODO: Use Array.includes() inside ternary condition
}
```

**Test Cases:**

- `checkVIPDiscount("Raju", ["Raju", "Babu", "Shyam"])` -> Expected: `10`
- `checkVIPDiscount("Kachra Seth", ["Raju", "Babu"])` -> Expected: `0`

## Q10: Night Fare Object Update

**Scenario:** Auto ride ka data object format mein aata hai. Agar `isNight` true hai toh fare double karna hai short-hand mein.

**Requirements:** Ride object ki `baseFare` property par ternary logic lagakar final fare calculate karein aur return karein.

**Starter Code:**

```javascript
function getFinalAutoFare(rideData) {
  // rideData = { baseFare: 50, isNight: true }
  // TODO: Return baseFare * 2 if isNight, else just baseFare
}
```

**Test Cases:**

- `getFinalAutoFare({ baseFare: 50, isNight: true })` -> Expected: `100`
- `getFinalAutoFare({ baseFare: 50, isNight: false })` -> Expected: `50`
