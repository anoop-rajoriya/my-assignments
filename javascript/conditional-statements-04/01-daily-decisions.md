## Module 1: The Daily Decisions (`if`, `else if`, `else`)

### Q1: Panipuri Bhaiya ka Teekha Level

**Scenario:** Panipuri wale bhaiya puchte hain, "Bhaiya teekha kaisa banau?" Agar "teekha" bola toh lal mirch, "meetha" bola toh saunth, warna "medium" banate hain.

**Requirements:** `if...else if...else` use karke flavor decide karein. String return karein: "Spicy water", "Sweet water", ya "Mixed water".

**Starter Code:**

```javascript
function makePanipuri(flavor) {
  // TODO: Use if-else to return the correct water type
}
```

**Test Cases:**

- `makePanipuri("teekha")` -> Expected: `"Spicy water"`
- `makePanipuri("medium")` -> Expected: `"Mixed water"`

### Q2: Samosa Dadi ka Stock Check

**Scenario:** Samosa wali dadi ke paas limited samose hote hain. Agar customer ne dadi ke stock se zyada samose maange, toh dadi bolti hain "Kal aana beta".

**Requirements:** `if` condition lagayein. Agar `orderQty` > `stock` hai, toh "Kal aana beta" return karein, warna "Ye lo samose".

**Starter Code:**

```javascript
function checkSamosaStock(orderQty, stock) {
  // TODO: Return correct string based on stock availability
}
```

**Test Cases:**

- `checkSamosaStock(5, 2)` -> Expected: `"Kal aana beta"`
- `checkSamosaStock(2, 10)` -> Expected: `"Ye lo samose"`

### Q3: Pandit Ji ka Udhaar (Khata) System

**Scenario:** Pandit ji ki kirana store par sirf "regular" customers ko hi udhaar (credit) milta hai. Naye logo ko strictly "Cash Only".

**Requirements:** `isRegularCustomer` ek boolean hai. Agar ye true hai toh "Udhaar likh liya", nahi toh "Cash do bhaiya" return karein.

**Starter Code:**

```javascript
function processPayment(isRegularCustomer) {
  // TODO: Use if-else with the boolean
}
```

**Test Cases:**

- `processPayment(true)` -> Expected: `"Udhaar likh liya"`
- `processPayment(false)` -> Expected: `"Cash do bhaiya"`

### Q4: Sabji Mandi mein Free Dhaniya

**Scenario:** Sabji wale bhaiya free dhaniya aur mirchi tabhi dete hain jab customer ka bill 100 Rs ya usse upar ho.

**Requirements:** Check karein agar `billAmount >= 100`, toh return "Free Dhaniya Added", warna "Dhaniya 10 Rs".

**Starter Code:**

```javascript
function getFreeDhaniya(billAmount) {
  // TODO: Return correct string based on billAmount
}
```

**Test Cases:**

- `getFreeDhaniya(150)` -> Expected: `"Free Dhaniya Added"`
- `getFreeDhaniya(50)` -> Expected: `"Dhaniya 10 Rs"`

### Q5: Auto Wale Bhaiya ka Night Charge

**Scenario:** Auto wale bhaiya raat ko 10 baje ke baad (22:00) 50 Rs extra "Night Charge" lete hain.

**Requirements:** Agar `time` 22 ya usse bada hai, toh `baseFare` mein 50 add karke return karein, else sirf `baseFare` return karein.

**Starter Code:**

```javascript
function calculateAutoFare(baseFare, time) {
  // TODO: Add 50 to fare if time is >= 22
}
```

**Test Cases:**

- `calculateAutoFare(100, 23)` -> Expected: `150`
- `calculateAutoFare(100, 14)` -> Expected: `100`

### Q6: Mamu ki Biryani - Half ya Full?

**Scenario:** Mamu ki biryani dukan par agar 3 ya usse zyada doston ka group aaye, toh wo direct "Full" lagate hain. Kam doston ke liye "Half". Doston ki list array mein aati hai.

**Requirements:** `friendsArray` ki `.length` check karein. Agar `>= 3` hai toh "Full Plate", warna "Half Plate".

**Starter Code:**

```javascript
function orderBiryani(friendsArray) {
  // TODO: Check array length and return Full/Half
}
```

**Test Cases:**

- `orderBiryani(["Rahul", "Aman", "Pooja"])` -> Expected: `"Full Plate"`
- `orderBiryani(["Ravi"])` -> Expected: `"Half Plate"`

### Q7: Raju Chaiwala ki Chini (Sugar) Alert

**Scenario:** Raju bhaiya healthy chai banate hain. Agar koi 3 chammach se zyada chini maange, toh wo bolte hain "Bhai diabetes ho jayegi!".

**Requirements:** Agar `sugarSpoons > 3` hai toh warning return karein, warna "Mast Kadak Chai".

**Starter Code:**

```javascript
function orderChai(sugarSpoons) {
  // TODO: Return warning if sugar > 3, else success message
}
```

**Test Cases:**

- `orderChai(4)` -> Expected: `"Bhai diabetes ho jayegi!"`
- `orderChai(2)` -> Expected: `"Mast Kadak Chai"`

### Q8: Jalebi Wali Dukaan ki Limit

**Scenario:** Tyohar ke din 1 customer ko maximum 2 kg jalebi hi milti hai taaki sabko mile.

**Requirements:** Agar `kgRequested > 2`, toh "Sirf 2 kg allowed hai" return karein, else "Pack kar diya".

**Starter Code:**

```javascript
function buyJalebi(kgRequested) {
  // TODO: Apply the 2kg limit condition
}
```

**Test Cases:**

- `buyJalebi(3)` -> Expected: `"Sirf 2 kg allowed hai"`
- `buyJalebi(1.5)` -> Expected: `"Pack kar diya"`

### Q9: Momos ki Chutney Mix

**Scenario:** Red chutney bahut teekhi hoti hai. Agar user object mein `likesSpicy` true hai, toh "Red Chutney", nahi toh "Mayonnaise".

**Requirements:** Object `userPreference` se `likesSpicy` boolean check karein aur string return karein.

**Starter Code:**

```javascript
function getMomosDip(userPreference) {
  // userPreference looks like { name: "Raj", likesSpicy: true }
  // TODO: Check likesSpicy property inside the object
}
```

**Test Cases:**

- `getMomosDip({ likesSpicy: true })` -> Expected: `"Red Chutney"`
- `getMomosDip({ likesSpicy: false })` -> Expected: `"Mayonnaise"`

### Q10: Sunday Closed Notice

**Scenario:** Pandit ji ki dukan Sunday ko completely closed rehti hai.

**Requirements:** String `day` check karein. Agar `day === "Sunday"`, toh "Dukan Band Hai", warna "Welcome".

**Starter Code:**

```javascript
function checkShopStatus(day) {
  // TODO: Return closed status for Sunday
}
```

**Test Cases:**

- `checkShopStatus("Sunday")` -> Expected: `"Dukan Band Hai"`
- `checkShopStatus("Monday")` -> Expected: `"Welcome"`
