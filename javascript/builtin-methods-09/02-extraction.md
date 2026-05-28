# Module 2: Data Extraction (`Array.filter`)

**Storyline:** Aap IRCTC Train Booking app ka search system bana rahe hain. Users hazaron trains me se apne kaam ki trains (Filter) karte hain.

## Q1: The Destination Filter

**Scenario:** User ne "Delhi" search kiya hai. Humein sirf wo trains chahiye jinki destination "Delhi" hai.
**Requirements:** `.filter()` ka use karein jahan `train.to === "Delhi"`.
**Starter Code:**

```javascript
function getTrainsToDelhi(trains) {
  // TODO: Filter trains where the 'to' property is strictly "Delhi"
}
```

**Test Cases:**

- `getTrainsToDelhi([{name: "Rajdhani", to: "Delhi"}, {name: "Shatabdi", to: "Mumbai"}])` -> Expected: `[{name: "Rajdhani", to: "Delhi"}]`
- `getTrainsToDelhi([{name: "Local", to: "Pune"}])` -> Expected: `[]`
- `getTrainsToDelhi([{name: "T1", to: "Delhi"}, {name: "T2", to: "Delhi"}])` -> Expected: `[{name: "T1", to: "Delhi"}, {name: "T2", to: "Delhi"}]`
- `getTrainsToDelhi([])` -> Expected: `[]`

## Q2: Available Seats Only

**Scenario:** Housefull (0 seats) trains UI pe nahi dikhani.
**Requirements:** `.filter()` lagayein taaki sirf wo trains bachein jinki `seats > 0` hai.
**Starter Code:**

```javascript
function getAvailableTrains(trains) {
  // TODO: Filter out trains with 0 or negative seats
}
```

**Test Cases:**

- `getAvailableTrains([{id: 1, seats: 50}, {id: 2, seats: 0}])` -> Expected: `[{id: 1, seats: 50}]`
- `getAvailableTrains([{id: 1, seats: 0}, {id: 2, seats: -5}])` -> Expected: `[]`
- `getAvailableTrains([{id: 1, seats: 100}])` -> Expected: `[{id: 1, seats: 100}]`
- `getAvailableTrains([])` -> Expected: `[]`

## Q3: Removing Cancelled Trains

**Scenario:** API me cancelled trains ka boolean `isCancelled: true` aata hai. Unhe list se hatana hai.
**Requirements:** `.filter()` ka use karein. Sirf wo object rakhein jahan `isCancelled` `false` (ya falsy) ho.
**Starter Code:**

```javascript
function removeCancelled(trains) {
  // TODO: Filter trains keeping only the active ones
}
```

**Test Cases:**

- `removeCancelled([{id: 1, isCancelled: true}, {id: 2, isCancelled: false}])` -> Expected: `[{id: 2, isCancelled: false}]`
- `removeCancelled([{id: 1, isCancelled: true}])` -> Expected: `[]`
- `removeCancelled([{id: 1, isCancelled: false}, {id: 2, isCancelled: false}])` -> Expected: `[{id: 1, isCancelled: false}, {id: 2, isCancelled: false}]`
- `removeCancelled([])` -> Expected: `[]`

## Q4: Budget Search (Premium Trains)

**Scenario:** Ek VIP user ne sirf "Premium" trains mangi hain jinka ticket 1500 Rs se upar ho.
**Requirements:** `.filter()` karein jahan `price > 1500`.
**Starter Code:**

```javascript
function getPremiumTrains(trains) {
  // TODO: Filter trains strictly above 1500
}
```

**Test Cases:**

- `getPremiumTrains([{id: 1, price: 1600}, {id: 2, price: 800}])` -> Expected: `[{id: 1, price: 1600}]`
- `getPremiumTrains([{id: 1, price: 1500}])` -> Expected: `[]` (Must be > 1500)
- `getPremiumTrains([{id: 1, price: 2000}, {id: 2, price: 3000}])` -> Expected: `[{id: 1, price: 2000}, {id: 2, price: 3000}]`
- `getPremiumTrains([])` -> Expected: `[]`

## Q5: Smart Search Box (String Includes)

**Scenario:** User search box me "Express" type karta hai. List me sabhi Express trains aani chahiye.
**Requirements:** `.filter()` ke andar `.includes()` string method ka use karein taaki naam match ho sake.
**Starter Code:**

```javascript
function searchTrains(trains, query) {
  // TODO: Filter trains whose name includes the query
}
```

**Test Cases:**

- `searchTrains([{name: "Duronto Express"}, {name: "Shatabdi"}], "Express")` -> Expected: `[{name: "Duronto Express"}]`
- `searchTrains([{name: "Pune Mail"}], "Express")` -> Expected: `[]`
- `searchTrains([{name: "Express A"}, {name: "Express B"}], "Express")` -> Expected: `[{name: "Express A"}, {name: "Express B"}]`
- `searchTrains([], "Test")` -> Expected: `[]`

## Q6: The AC Coach Toggle

**Scenario:** UI par ek checkbox hai "AC Only". Pata lagana hai array of strings me se kaunse items me "AC" shamil hai.
**Requirements:** Array of strings (e.g. `["Sleeper", "3AC", "2AC"]`) pe `.filter()` lagayein.
**Starter Code:**

```javascript
function filterACCoaches(coaches) {
  // TODO: Return only strings that contain "AC"
}
```

**Test Cases:**

- `filterACCoaches(["1AC", "General", "Sleeper", "3AC"])` -> Expected: `["1AC", "3AC"]`
- `filterACCoaches(["General", "Sleeper"])` -> Expected: `[]`
- `filterACCoaches(["AC Chair Car", "General"])` -> Expected: `["AC Chair Car"]`
- `filterACCoaches([])` -> Expected: `[]`

## Q7: Removing Junk Data

**Scenario:** Data corruption ki wajah se API ne kuch string values null, undefined ya empty string bhej di hain train schedules me.
**Requirements:** `.filter(Boolean)` ya custom filter ka use karke sirf "Truthy" values (valid strings) retain karein.
**Starter Code:**

```javascript
function cleanSchedule(stops) {
  // TODO: Remove all falsy values from the array
}
```

**Test Cases:**

- `cleanSchedule(["Delhi", null, "Agra", "", undefined])` -> Expected: `["Delhi", "Agra"]`
- `cleanSchedule([null, undefined, ""])` -> Expected: `[]`
- `cleanSchedule(["Mumbai", "Pune"])` -> Expected: `["Mumbai", "Pune"]`
- `cleanSchedule([])` -> Expected: `[]`

## Q8: Method Chaining (Map + Filter)

**Scenario:** Humein sirf Available trains (seats > 0) chahiye, aur UI ko sirf un trains ke "Names" ka string array chahiye (objects nahi).
**Requirements:** Pehle `.filter()` lagayein seats > 0 ke liye, fir usi ke aage `.map()` chain karein sirf names nikalne ke liye.
**Starter Code:**

```javascript
function getAvailableTrainNames(trains) {
  // TODO: Chain filter() and map()
}
```

**Test Cases:**

- `getAvailableTrainNames([{name: "A", seats: 10}, {name: "B", seats: 0}])` -> Expected: `["A"]`
- `getAvailableTrainNames([{name: "X", seats: 0}, {name: "Y", seats: 0}])` -> Expected: `[]`
- `getAvailableTrainNames([{name: "P", seats: 5}, {name: "Q", seats: 5}])` -> Expected: `["P", "Q"]`
- `getAvailableTrainNames([])` -> Expected: `[]`
