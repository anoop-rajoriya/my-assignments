# Module 4: Mixed Logic & Intermediate Hurdles

## Q1: The Panipuri Combo Tracker (Nested)

**Scenario:** Ek couple panipuri khaa raha hai. Unka order array mein aaya hai. Humein check karna hai: Agar array mein "PaniPuri" hai, toh uske sath "SukhiPuri" bhi free add karni hai (agar pehle se nahi hai).

**Requirements:** Use `if`. Array method `.includes()` use karein. Agar "PaniPuri" hai aur "SukhiPuri" nahi hai, toh array mein push karein. Updated array return karein.

**Starter Code:**

```javascript
function completeOrder(orderItems) {
  // TODO: Nested or compound condition using array.includes()

  return orderItems;
}
```

**Test Cases:**

- `completeOrder(["PaniPuri", "DahiPuri"])` -> Expected: `["PaniPuri", "DahiPuri", "SukhiPuri"]`
- `completeOrder(["DahiPuri"])` -> Expected: `["DahiPuri"]`

## Q2: Kirana Store Object Safety Check

**Scenario:** Pandit ji ne ek naya item system me add kiya par uski `price` dalna bhool gaye. Object property missing hai ya `undefined` hai.

**Requirements:** `if` condition use karein. Agar `item.price` undefined ya 0 hai, toh "Price Not Set" return karein. Warna "Available" return karein.

**Starter Code:**

```javascript
function checkItemPrice(item) {
  // item = { name: "Aata", weight: "5kg" } // price is missing
  // TODO: Check if price property exists and is truthy
}
```

**Test Cases:**

- `checkItemPrice({ name: "Dal" })` -> Expected: `"Price Not Set"`
- `checkItemPrice({ name: "Rice", price: 50 })` -> Expected: `"Available"`

## Q3: Auto Bhaiya ki Booking Status

**Scenario:** Auto bhaiya ka ek status object hai. Status 3 ho sakte hain: "booked", "free", "lunch".

**Requirements:** `switch` case use karein `autoObj.status` par. "booked" -> "Busy", "free" -> "Baitho", "lunch" -> "Khana kha raha hu".

**Starter Code:**

```javascript
function autoAvailability(autoObj) {
  // TODO: Use switch-case on autoObj.status
}
```

**Test Cases:**

- `autoAvailability({ status: "free" })` -> Expected: `"Baitho"`

## Q4: Samosa-Jalebi Combo Discount (Nested if)

**Scenario:** Samosa dadi ka offer: Agar customer ne 5 se zyada samose liye hain, AUR array order list mein "Jalebi" bhi shamil hai, toh "Combo Discount" milega, warna "No Discount".

**Requirements:** `if...else` aur array `.includes()` ko combine karein.

**Starter Code:**

```javascript
function checkComboOffer(samosaQty, orderArray) {
  // TODO: Use nested logic or AND (&&) operator
}
```

**Test Cases:**

- `checkComboOffer(6, ["Samose", "Jalebi"])` -> Expected: `"Combo Discount"`
- `checkComboOffer(6, ["Samose", "Kachori"])` -> Expected: `"No Discount"`

## Q5: Tapri ki Chai Array check (Ternary)

**Scenario:** Chai tapri par agar 5 se zyada log aate hain toh unko alag se glasses ki jagah puri Ketli (Kettle) de di jati hai.

**Requirements:** `peopleArray.length` par ternary operator lagayein. `> 5` hai toh "Ketli de do", else "Glasses dena".

**Starter Code:**

```javascript
function serveGroup(peopleArray) {
  // TODO: One liner return using ternary on array length
}
```

**Test Cases:**

- `serveGroup(["A", "B", "C", "D", "E", "F"])` -> Expected: `"Ketli de do"`

## Q6: Mandi Bargain Logic (If-Else with Objects)

**Scenario:** Sabji mandi mein bargain hota hai. Agar customer `customer.isLocal` true hai, toh owner price ka 10% kam kar deta hai. Agar local nahi hai toh full price.

**Requirements:** `if...else` use karein. Calculate and return final Number price.

**Starter Code:**

```javascript
function negotiatePrice(customer, originalPrice) {
  // customer = { name: "Pooja", isLocal: true }
  // TODO: Reduce price by 10% if local, else return original
}
```

**Test Cases:**

- `negotiatePrice({ isLocal: true }, 100)` -> Expected: `90`
- `negotiatePrice({ isLocal: false }, 100)` -> Expected: `100`

## Q7: Truthy/Falsy in Real Life

**Scenario:** Pandit ji ki dukan par khata book tabhi khulegi jab customer ka naam empty string (`""`) na ho aur null na ho. JavaScript mein aisi empty chizein aapas mein falsy maani jati hain.

**Requirements:** `if (!customerName)` type ka truthy/falsy logic lagayein. Agar name falsy hai toh "Naam batao", else "Entry Done".

**Starter Code:**

```javascript
function makeKhataEntry(customerName) {
  // TODO: Rely on Truthy/Falsy logic to return the string
}
```

**Test Cases:**

- `makeKhataEntry("")` -> Expected: `"Naam batao"`
- `makeKhataEntry("Mohit")` -> Expected: `"Entry Done"`

## Q8: The Biryani Object Switch

**Scenario:** Biryani menu ek object hai `{ portion: "half", type: "chicken" }`.

**Requirements:** Nested conditionals! Pehle `if` mein check karein `type === "chicken"` hai kya. Agar haan, toh `switch` lagayein `portion` par. "half" -> 80, "full" -> 150. (Veg hui toh direct 0 return karein for now).

**Starter Code:**

```javascript
function getBiryaniBill(orderObj) {
  // TODO: if chicken -> switch portion -> return amount
}
```

**Test Cases:**

- `getBiryaniBill({ type: "chicken", portion: "full" })` -> Expected: `150`
- `getBiryaniBill({ type: "veg", portion: "half" })` -> Expected: `0`

## Q9: Complex Ternary with Object Creation

**Scenario:** Dosa order complete hone par bill receipt object banana hai. Agar order `isParcel` true hai toh packaging fee 10 Rs extra judti hai.

**Requirements:** Ek function banayein jo ek object return kare. Object ki `total` key par ternary operator lagayein (`basePrice` + 10 ya sirf `basePrice`).

**Starter Code:**

```javascript
function generateDosaBill(basePrice, isParcel) {
  // TODO: Return an object { billAmount: <calculated value> }
  return {
    billAmount: /* Ternary magic here */
  };
}

```

**Test Cases:**

- `generateDosaBill(50, true)` -> Expected: `{ billAmount: 60 }`
- `generateDosaBill(50, false)` -> Expected: `{ billAmount: 50 }`

## Q10: Momos Special Weekend Offer (Compound If)

**Scenario:** Weekend (`day === "Saturday" || day === "Sunday"`) ko aur Agar bill (`amount >= 200`) hai toh cold drink free milti hai. Do conditions sath me milani hain.

**Requirements:** Compound `if` condition with Logical OR (`||`) and Logical AND (`&&`). Return "Free Cola" or "No Offer".

**Starter Code:**

```javascript
function checkWeekendOffer(day, amount) {
  // TODO: Use || and && properly inside an if statement
}
```

**Test Cases:**

- `checkWeekendOffer("Saturday", 250)` -> Expected: `"Free Cola"`
- `checkWeekendOffer("Monday", 300)` -> Expected: `"No Offer"`
- `checkWeekendOffer("Sunday", 150)` -> Expected: `"No Offer"`
