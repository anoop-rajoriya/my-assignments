## Module 1: The World of Arrays

### Q1: The Grocery List

**Scenario:** Ek shopping app banani hai jisme user apne items list mein daal sake. Array multiple values ek saath store karne ka best tarika hai.

**Requirements:** `groceries` naam ka ek array banayein jisme 3 items hon: "Milk", "Bread", aur "Eggs". Array ko return karein.

**Starter Code:**

```javascript
function getGroceryList() {
  // TODO: Create and return the groceries array
}
```

**Test Cases:**

- `getGroceryList()` -> Expected: `["Milk", "Bread", "Eggs"]`

### Q2: Accessing the VIP Guest

**Scenario:** Ek event ki VIP guest list array mein hai. Humein sabse pehle (first) guest ka naam chahiye.

**Requirements:** Array ke pehle element ko uske index number ka use karke return karein.

**Starter Code:**

```javascript
function getFirstGuest(guests) {
  // TODO: Return the first guest from the array
}
```

**Test Cases:**

- `getFirstGuest(["Rahul", "Neha", "Aman"])` -> Expected: `"Rahul"`

### Q3: Updating the Roster

**Scenario:** Cricket team ke array mein ek player injured ho gaya hai aur uski jagah naya player aayega.

**Requirements:** Array ke second item (index 1) ko "Surya" se replace karein aur updated array return karein.

**Starter Code:**

```javascript
function updatePlayer(team) {
  // TODO: Update the 2nd element to "Surya" and return team
}
```

**Test Cases:**

- `updatePlayer(["Virat", "Rohit", "Bumrah"])` -> Expected: `["Virat", "Surya", "Bumrah"]`

### Q4: Counting the Inventory

**Scenario:** Godown mein kitne items aaye hain, ye app dashboard par dikhana hai.

**Requirements:** `length` property ka use karke array mein total items count karein aur return karein.

**Starter Code:**

```javascript
function countItems(inventory) {
  // TODO: Return the total number of items
}
```

**Test Cases:**

- `countItems(["Laptops", "Mobiles", "Tablets", "Watches"])` -> Expected: `4`

### Q5: Adding to the Cart (Push)

**Scenario:** User ne "Shoes" cart mein add kiye hain. Naya item humesha array ke end (aakhir) mein judna chahiye.

**Requirements:** Built-in `push()` method use karke `newItem` ko array mein add karein.

**Starter Code:**

```javascript
function addToCart(cart, newItem) {
  // TODO: Push newItem to cart and return the cart
}
```

**Test Cases:**

- `addToCart(["Shirt"], "Shoes")` -> Expected: `["Shirt", "Shoes"]`

### Q6: Undoing the Last Action (Pop)

**Scenario:** User ne galti se last item add kar diya aur "Undo" dabaya.

**Requirements:** Built-in `pop()` method use karke array ka aakhiri item remove karein aur bacha hua array return karein.

**Starter Code:**

```javascript
function removeLastItem(items) {
  // TODO: Remove the last item and return the array
}
```

**Test Cases:**

- `removeLastItem(["Apple", "Banana", "Orange"])` -> Expected: `["Apple", "Banana"]`

### Q7: Priority Queue (Unshift)

**Scenario:** Ek hospital token system mein emergency patient aaya hai. Use queue ke sabse aage (start mein) place karna hai.

**Requirements:** Built-in `unshift()` method use karke `patientName` ko array ke start mein add karein.

**Starter Code:**

```javascript
function addEmergencyPatient(queue, patientName) {
  // TODO: Add patient to the start of the array and return it
}
```

**Test Cases:**

- `addEmergencyPatient(["Ramesh", "Suresh"], "Kiran")` -> Expected: `["Kiran", "Ramesh", "Suresh"]`

### Q8: The Typeof Array Illusion

**Scenario:** JavaScript mein Array asal mein ek special type ka Object hota hai. Agar aap `typeof` check karenge toh wo "array" nahi dikhayega.

**Requirements:** Ek array banayein aur uska `typeof` return karein taaki sachai pata chale.

**Starter Code:**

```javascript
function checkArrayType() {
  let myArr = [1, 2, 3];
  // TODO: Return the typeof myArr
}
```

**Test Cases:**

- `checkArrayType()` -> Expected: `"object"`

### Q9: The Real Array Checker

**Scenario:** Agar `typeof` array ko "object" batata hai, toh hum verify kaise karein ki data sach mein Array hai? Iske liye `Array.isArray()` built-in method use hota hai.

**Requirements:** Check karein ki aane wala data array hai ya nahi. True ya False return karein.

**Starter Code:**

```javascript
function verifyIsArray(data) {
  // TODO: Use Array.isArray() and return the result
}
```

**Test Cases:**

- `verifyIsArray([10, 20])` -> Expected: `true`
- `verifyIsArray("Hello")` -> Expected: `false`

### Q10: Merging Playlists

**Scenario:** User ke paas do alag-alag music playlists hain aur wo dono ko milakar ek karna chahta hai.

**Requirements:** `concat()` method ka use karke list1 aur list2 ko combine karein. (Bina loop use kiye).

**Starter Code:**

```javascript
function mergePlaylists(list1, list2) {
  // TODO: Concatenate list2 into list1 and return the new array
}
```

**Test Cases:**

- `mergePlaylists(["Song A"], ["Song B", "Song C"])` -> Expected: `["Song A", "Song B", "Song C"]`
