# Module 5: Analytics & Report Generation

**Starter Story:** Humara EdTech platform "CodeGuru" apne instructors ko detailed analytics dashboard deta hai. Course kitne log dekh rahe hain, average completion rate kya hai, aur revenue generation ka data raw format me server se aata hai. Ek frontend dev ke naate, aapko is raw data ko process karke UI components ke liye meaningful aggregations aur reports banani hain. Yahan Closures aur IIFEs se private data state ko manage karne ki real test hogi.

## Q1: Calculate Average Completion Rate

**Problem story:** Instructor dekhna chahta hai ki average students ne kitna percent course complete kiya hai (0-100%).
**Problem to solve:** Students ki array of objects (jisme `progress` property ho) lo aur unka average nikalkar return karo. Return integer (Math.round se round karke).
**Starter code snippet:**

```javascript
const calculateAvgProgress = (students) => {
  // Your code here
};
```

**Test cases:**

1. `calculateAvgProgress([{progress: 50}, {progress: 100}])` ➞ `75`
2. `calculateAvgProgress([{progress: 33}, {progress: 33}, {progress: 33}])` ➞ `33`
3. `calculateAvgProgress([])` ➞ `0`
4. `calculateAvgProgress([{progress: 0}, {progress: 100}])` ➞ `50`

## Q2: Revenue Tracker (Closure Pattern)

**Problem story:** Har baar jab koi naya student enroll hota hai, dashboard ka revenue counter bina global variable use kiye automatically update hona chahiye memory me.
**Problem to solve:** Ek function banao jo ek inner function return kare. Inner function ek `amount` le aur previous total me add karke naya total return kare.
**Starter code snippet:**

```javascript
const createRevenueTracker = () => {
  // Your code here
};
```

**Test cases:**

1. `const tracker = createRevenueTracker(); tracker(100);` ➞ `100`
2. `tracker(50);` ➞ `150` (following previous test)
3. `const t2 = createRevenueTracker(); t2(10);` ➞ `10`
4. `t2(10);` ➞ `20`

## Q3: Highest Scorer Finder

**Problem story:** Leaderboard par top scorer ka naam highlight karna hai.
**Problem to solve:** Array of objects me se us object ka `name` property return karo jiski `score` sabse zyada hai.
**Starter code snippet:**

```javascript
const getTopScorerName = (students) => {
  // Your code here
};
```

**Test cases:**

1. `getTopScorerName([{name: "A", score: 80}, {name: "B", score: 95}])` ➞ `"B"`
2. `getTopScorerName([{name: "X", score: 50}])` ➞ `"X"`
3. `getTopScorerName([])` ➞ `null`
4. `getTopScorerName([{name: "C", score: 90}, {name: "D", score: 90}])` ➞ `"C"` // return first if tie

## Q4: Format Course Duration

**Problem story:** Backend se video duration total seconds me aati hai (e.g. 130). UI par ise "2m 10s" format me display karna hai.
**Problem to solve:** Number of seconds lo aur string format `${minutes}m ${seconds}s` return karo.
**Starter code snippet:**

```javascript
const formatDuration = (totalSeconds) => {
  // Your code here
};
```

**Test cases:**

1. `formatDuration(130)` ➞ `"2m 10s"`
2. `formatDuration(60)` ➞ `"1m 0s"`
3. `formatDuration(45)` ➞ `"0m 45s"`
4. `formatDuration(0)` ➞ `"0m 0s"`

## Q5: Grade Categorization

**Problem story:** Raw marks (0-100) ko report card display ke liye Letter Grades (A, B, C, F) me transform karna hai.
**Problem to solve:** Number input lo. 90+ => "A", 75-89 => "B", 50-74 => "C", less than 50 => "F".
**Starter code snippet:**

```javascript
const getGrade = (marks) => {
  // Your code here
};
```

**Test cases:**

1. `getGrade(95)` ➞ `"A"`
2. `getGrade(80)` ➞ `"B"`
3. `getGrade(55)` ➞ `"C"`
4. `getGrade(30)` ➞ `"F"`

## Q6: Aggregate Feedback Ratings

**Problem story:** Star ratings (1-5) 50 alag-alag reviews me hain. Hume dekhna hai ki har star category me kitne votes aaye (e.g., `{ 5: 10, 4: 20 }`).
**Problem to solve:** Array of numbers lo. Loop use karke frequency map (object) banao jo har number ka count store kare.
**Starter code snippet:**

```javascript
const tallyRatings = (ratings) => {
  // Your code here
};
```

**Test cases:**

1. `tallyRatings([5, 5, 4, 3])` ➞ `{ '3': 1, '4': 1, '5': 2 }`
2. `tallyRatings([1, 1, 1])` ➞ `{ '1': 3 }`
3. `tallyRatings([])` ➞ `{}`
4. `tallyRatings([2, 4])` ➞ `{ '2': 1, '4': 1 }`

## Q7: Passed Students Array

**Problem story:** Un students ka email extract karna hai jo pass ho gaye hain (marks >= 50) taaki unhe certificate bheja ja sake.
**Problem to solve:** Array ko filter karo un objects ke liye jinka `score >= 50`, aur map karke unka `email` string ka array return karo.
**Starter code snippet:**

```javascript
const getPassedEmails = (students) => {
  // Your code here
};
```

**Test cases:**

1. `getPassedEmails([{email: "a@x.com", score: 60}, {email: "b@x.com", score: 40}])` ➞ `["a@x.com"]`
2. `getPassedEmails([{email: "c", score: 30}])` ➞ `[]`
3. `getPassedEmails([])` ➞ `[]`
4. `getPassedEmails([{email: "d", score: 50}])` ➞ `["d"]`

## Q8: Find Missed Assignments

**Problem story:** Instructor dashboard bataata hai ki ek student ne kaun kaun se module ke assignment submit nahi kiye.
**Problem to solve:** Student object me ek `submissions` object hai jisme boolean value hai (e.g. `{ mod1: true, mod2: false }`). Woh keys return karo jinki value `false` hai.
**Starter code snippet:**

```javascript
const getPendingModules = (submissions) => {
  // Your code here
};
```

**Test cases:**

1. `getPendingModules({m1: true, m2: false, m3: false})` ➞ `["m2", "m3"]`
2. `getPendingModules({m1: true, m2: true})` ➞ `[]`
3. `getPendingModules({})` ➞ `[]`
4. `getPendingModules({m1: false})` ➞ `["m1"]`

## Q9: Combine Course Tags

**Problem story:** Ek course me multiple instructors ne apne tags array dale hain. Dashboard search me saare tags ki ek combined flat aur unique list dikhani hai.
**Problem to solve:** 2 arrays of strings lo, unhe combine karo aur duplicate tags ko hata do.
**Starter code snippet:**

```javascript
const mergeTags = (tags1, tags2) => {
  // Your code here
};
```

**Test cases:**

1. `mergeTags(["JS", "React"], ["React", "CSS"])` ➞ `["JS", "React", "CSS"]`
2. `mergeTags(["A"], ["B"])` ➞ `["A", "B"]`
3. `mergeTags([], ["X"])` ➞ `["X"]`
4. `mergeTags(["A", "A"], [])` ➞ `["A"]`

## Q10: Convert Object to Query Parameters

**Problem story:** Analytics data mangwane ke liye URL me filter variables bhejney padte hain (e.g. `?year=2026&course=react`).
**Problem to solve:** Ek object lo aur usko key-value pairs format karke `key=value&key2=value2` string me badlo.
**Starter code snippet:**

```javascript
const objectToQueryParams = (params) => {
  // Your code here
};
```

**Test cases:**

1. `objectToQueryParams({year: 2026, course: "react"})` ➞ `"year=2026&course=react"`
2. `objectToQueryParams({id: 1})` ➞ `"id=1"`
3. `objectToQueryParams({})` ➞ `""`
4. `objectToQueryParams({a: 1, b: 2, c: 3})` ➞ `"a=1&b=2&c=3"`

## Q11: Filter Active Enrollments

**Problem story:** Student ka account freeze ho gaya hai, hume analytics se in frozen accounts ko data bias bachane ke liye filter out karna hai.
**Problem to solve:** Arrays of users lo. Agar user object me `status: "frozen"` ya `status: "inactive"` hai, toh use array se nikal do.
**Starter code snippet:**

```javascript
const getActiveUsers = (users) => {
  // Your code here
};
```

**Test cases:**

1. `getActiveUsers([{id: 1, status: "active"}, {id: 2, status: "frozen"}])` ➞ `[{id: 1, status: "active"}]`
2. `getActiveUsers([{id: 1, status: "inactive"}])` ➞ `[]`
3. `getActiveUsers([])` ➞ `[]`
4. `getActiveUsers([{id: 1, status: "active"}, {id: 2, status: "active"}])` ➞ `[{id: 1, status: "active"}, {id: 2, status: "active"}]`

## Q12: Generative ID Creator (IIFE Pattern)

**Problem story:** Reports generate karte time browser session me un reports ko ek sequential ID chahiye hoti hai like (RPT-1, RPT-2).
**Problem to solve:** Ek IIFE closure likho jo har bar call hone par naya ID "RPT-X" return kare, jahan X 1 se start ho aur badhta jaye.
**Starter code snippet:**

```javascript
const getNextReportId = (() => {
  // Your code here
})();
```

**Test cases:**

1. `getNextReportId()` ➞ `"RPT-1"`
2. `getNextReportId()` ➞ `"RPT-2"`
3. `getNextReportId()` ➞ `"RPT-3"`
4. `getNextReportId()` ➞ `"RPT-4"`
