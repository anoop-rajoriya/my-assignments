# Module 4: Sorting Data (`Array.sort`)

**Storyline:** Aap IPL/Cricket Team ka Player Stats Dashboard bana rahe hain. Yahan data ascending aur descending dono order me sort karna padta hai. `sort()` original array ko modify kar deta hai!

## Q1: Sorting Runs Ascending (Low to High)

**Scenario:** Sabse kam runs kisne banaye ye upar dikhana hai.
**Requirements:** Numbers ke array par `.sort((a, b) => a - b)` lagayein.
**Starter Code:**

```javascript
function sortRunsAscending(runs) {
  // TODO: Sort numbers from lowest to highest
}
```

**Test Cases:**

- `sortRunsAscending([50, 10, 100])` -> Expected: `[10, 50, 100]`
- `sortRunsAscending([0, 5, 2])` -> Expected: `[0, 2, 5]`
- `sortRunsAscending([10, 10, 10])` -> Expected: `[10, 10, 10]`
- `sortRunsAscending([])` -> Expected: `[]`

## Q2: Sorting Runs Descending (Highest First)

**Scenario:** Orange Cap Leaderboard (Top run scorer sabse upar).
**Requirements:** `.sort()` lagayein descending logic ke sath `(b - a)`.
**Starter Code:**

```javascript
function sortRunsDescending(runs) {
  // TODO: Sort numbers from highest to lowest
}
```

**Test Cases:**

- `sortRunsDescending([50, 120, 80])` -> Expected: `[120, 80, 50]`
- `sortRunsDescending([1, 100, 99])` -> Expected: `[100, 99, 1]`
- `sortRunsDescending([5, 5])` -> Expected: `[5, 5]`
- `sortRunsDescending([])` -> Expected: `[]`

## Q3: Alphabetical Team Roster

**Scenario:** Players ke naam A-Z format me lagane hain.
**Requirements:** JS me default `.sort()` strings ko alphabetically sort karta hai. Bas array par sort chala dein.
**Starter Code:**

```javascript
function sortNamesAZ(names) {
  // TODO: Sort strings alphabetically
}
```

**Test Cases:**

- `sortNamesAZ(["Virat", "Rohit", "Dhoni"])` -> Expected: `["Dhoni", "Rohit", "Virat"]`
- `sortNamesAZ(["Zack", "Aman"])` -> Expected: `["Aman", "Zack"]`
- `sortNamesAZ(["Sam", "Sam"])` -> Expected: `["Sam", "Sam"]`
- `sortNamesAZ([])` -> Expected: `[]`

## Q4: Object Sorting (Sort by Property)

**Scenario:** Array me objects hain `[{name: "Virat", runs: 700}, {name: "Rohit", runs: 500}]`. Humein runs ke aadhar par descending sort karna hai.
**Requirements:** `.sort((a, b) => b.runs - a.runs)` ka use karein.
**Starter Code:**

```javascript
function sortPlayersByRuns(players) {
  // TODO: Sort array of objects descending by the 'runs' property
}
```

**Test Cases:**

- `sortPlayersByRuns([{name: "A", runs: 100}, {name: "B", runs: 300}])` -> Expected: `[{name: "B", runs: 300}, {name: "A", runs: 100}]`
- `sortPlayersByRuns([{name: "X", runs: 50}, {name: "Y", runs: 20}])` -> Expected: `[{name: "X", runs: 50}, {name: "Y", runs: 20}]`
- `sortPlayersByRuns([{name: "P", runs: 10}])` -> Expected: `[{name: "P", runs: 10}]`
- `sortPlayersByRuns([])` -> Expected: `[]`

## Q5: Sort by Average (Decimal Sorting)

**Scenario:** Players ko unki batting average ke hisaab se Ascending (Low to high) sort karna hai. Averages decimals me hain.
**Requirements:** Decimals ke liye bhi same math logic `a.avg - b.avg` chalta hai JS me. Apply karein.
**Starter Code:**

```javascript
function sortByAverage(players) {
  // TODO: Sort ascending by the 'avg' property
}
```

**Test Cases:**

- `sortByAverage([{id: 1, avg: 45.5}, {id: 2, avg: 30.2}])` -> Expected: `[{id: 2, avg: 30.2}, {id: 1, avg: 45.5}]`
- `sortByAverage([{id: 1, avg: 50.1}, {id: 2, avg: 50.9}])` -> Expected: `[{id: 1, avg: 50.1}, {id: 2, avg: 50.9}]`
- `sortByAverage([{id: 1, avg: 0}])` -> Expected: `[{id: 1, avg: 0}]`
- `sortByAverage([])` -> Expected: `[]`

## Q6: String Property Sorting (localeCompare)

**Scenario:** Array of objects me player ke naam A-Z sort karne hain. Directly `a.name - b.name` nahi chalega kyunki wo string hai.
**Requirements:** `a.name.localeCompare(b.name)` ka use karein inside `.sort()`.
**Starter Code:**

```javascript
function sortObjectsByName(players) {
  // TODO: Sort objects alphabetically by the 'name' property
}
```

**Test Cases:**

- `sortObjectsByName([{name: "Virat"}, {name: "Dhoni"}])` -> Expected: `[{name: "Dhoni"}, {name: "Virat"}]`
- `sortObjectsByName([{name: "Z"}, {name: "A"}])` -> Expected: `[{name: "A"}, {name: "Z"}]`
- `sortObjectsByName([{name: "B"}])` -> Expected: `[{name: "B"}]`
- `sortObjectsByName([])` -> Expected: `[]`

## Q7: Captains First (Sorting by Boolean)

**Scenario:** Team list me humesha `isCaptain: true` wale player ko sabse upar rakhna hai (Index 0).
**Requirements:** `.sort()` me booleans ko math ke liye number (1, 0) me samjha jata hai. `Number(b.isCaptain) - Number(a.isCaptain)` use karein.
**Starter Code:**

```javascript
function bringCaptainsTop(players) {
  // TODO: Sort so that isCaptain === true comes first
}
```

**Test Cases:**

- `bringCaptainsTop([{name: "A", isCaptain: false}, {name: "B", isCaptain: true}])` -> Expected: `[{name: "B", isCaptain: true}, {name: "A", isCaptain: false}]`
- `bringCaptainsTop([{name: "X", isCaptain: true}, {name: "Y", isCaptain: false}])` -> Expected: `[{name: "X", isCaptain: true}, {name: "Y", isCaptain: false}]`
- `bringCaptainsTop([{name: "P", isCaptain: false}, {name: "Q", isCaptain: false}])` -> Expected: `[{name: "P", isCaptain: false}, {name: "Q", isCaptain: false}]`
- `bringCaptainsTop([])` -> Expected: `[]`

## Q8: Multi-Level Sorting (Runs, then Strike Rate)

**Scenario:** Agar do players ke `runs` bilkul same (tie) ho jayein, toh jiska `strikeRate` high hai usko upar rakhein.
**Requirements:** `.sort()` me `if(b.runs === a.runs)` then return `b.strikeRate - a.strikeRate`, else return `b.runs - a.runs`. (Descending order).
**Starter Code:**

```javascript
function sortLeaderboard(players) {
  // TODO: Sort by runs descending, if tied, sort by strikeRate descending
}
```

**Test Cases:**

- `sortLeaderboard([{id: 1, runs: 500, sr: 120}, {id: 2, runs: 500, sr: 150}])` -> Expected: `[{id: 2, runs: 500, sr: 150}, {id: 1, runs: 500, sr: 120}]`
- `sortLeaderboard([{id: 1, runs: 600, sr: 100}, {id: 2, runs: 500, sr: 150}])` -> Expected: `[{id: 1, runs: 600, sr: 100}, {id: 2, runs: 500, sr: 150}]`
- `sortLeaderboard([{id: 1, runs: 100, sr: 100}])` -> Expected: `[{id: 1, runs: 100, sr: 100}]`
- `sortLeaderboard([])` -> Expected: `[]`
