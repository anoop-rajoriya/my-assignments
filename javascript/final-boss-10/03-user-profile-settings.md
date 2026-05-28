# Module 3: User Profiles & Settings Data

**Starter Story:** Humara OTT streaming app 'NetPrime' ab nayi profile features laa raha hai. Multiple profiles, watch history, settings aur preferences ek hi user object me store hoti hain. Is module me aapko in deeply nested objects aur arrays ke saath khele bina code break kiye mutations aur merging sikhni hai.

## Q1: Merge User Settings

**Problem story:** User app ki default settings ke upar apni custom settings save karta hai. Hume default aur custom ko combine karke final settings object banana hai.
**Problem to solve:** Do objects input lo (defaults, user). Ek naya object return karo jisme pehle defaults hon aur fir user ki settings unhe overwrite karein.
**Starter code snippet:**

```javascript
const mergeSettings = (defaults, userSettings) => {
  // Your code here
};
```

**Test cases:**

1. `mergeSettings({theme: "light", autoplay: true}, {theme: "dark"})` ➞ `{theme: "dark", autoplay: true}`
2. `mergeSettings({quality: "720p"}, {quality: "1080p"})` ➞ `{quality: "1080p"}`
3. `mergeSettings({a: 1}, {})` ➞ `{a: 1}`
4. `mergeSettings({}, {b: 2})` ➞ `{b: 2}`

## Q2: Extract Active Profile

**Problem story:** Ek account me maximum 4 profiles hoti hain (jaise Kids, Mom, Dad). Hume sirf us profile ka data chahiye jo abhi active status mein hai.
**Problem to solve:** Array of profile objects me se wo ek object nikaalo jiski property `isActive` true ho.
**Starter code snippet:**

```javascript
const getActiveProfile = (profiles) => {
  // Your code here
};
```

**Test cases:**

1. `getActiveProfile([{name: "A", isActive: false}, {name: "B", isActive: true}])` ➞ `{name: "B", isActive: true}`
2. `getActiveProfile([{name: "C", isActive: false}])` ➞ `undefined`
3. `getActiveProfile([])` ➞ `undefined`
4. `getActiveProfile([{name: "D", isActive: true}, {name: "E", isActive: true}])` ➞ `{name: "D", isActive: true}` // First match

## Q3: Toggle Autoplay

**Problem story:** Jab user video player me autoplay icon dabata hai, wo setting true se false, ya false se true hoti hai.
**Problem to solve:** User settings object lo aur uski `autoplay` property (boolean) ko flip (toggle) kar do, phir wahi object return karo.
**Starter code snippet:**

```javascript
const toggleAutoplay = (settings) => {
  // Your code here
};
```

**Test cases:**

1. `toggleAutoplay({autoplay: true})` ➞ `{autoplay: false}`
2. `toggleAutoplay({autoplay: false})` ➞ `{autoplay: true}`
3. `toggleAutoplay({theme: "dark", autoplay: true})` ➞ `{theme: "dark", autoplay: false}`
4. `toggleAutoplay({})` ➞ `{autoplay: true}` // defaults to true if missing

## Q4: Append to Watch History

**Problem story:** User ne koi nayi movie dekhi. Hume us movie ki ID ko user ke watch history array me add karna hai, par duplicate allowed nahi hai.
**Problem to solve:** Ek array (history) aur ek string (movieId) lo. Agar movieId history me nahi hai, tabhi usko array me push karo. Modified array return karo.
**Starter code snippet:**

```javascript
const addToHistory = (history, movieId) => {
  // Your code here
};
```

**Test cases:**

1. `addToHistory(["m1", "m2"], "m3")` ➞ `["m1", "m2", "m3"]`
2. `addToHistory(["m1", "m2"], "m2")` ➞ `["m1", "m2"]`
3. `addToHistory([], "m1")` ➞ `["m1"]`
4. `addToHistory(["x"], "y")` ➞ `["x", "y"]`

## Q5: Check Premium Status

**Problem story:** Premium features tabhi chalte hain jab `subscriptionPlan` "Gold" ya "Platinum" ho, aur `isExpired` false हो.
**Problem to solve:** User profile object lo, conditions check karo, aur boolean return karo.
**Starter code snippet:**

```javascript
const isPremiumUser = (user) => {
  // Your code here
};
```

**Test cases:**

1. `isPremiumUser({subscriptionPlan: "Gold", isExpired: false})` ➞ `true`
2. `isPremiumUser({subscriptionPlan: "Silver", isExpired: false})` ➞ `false`
3. `isPremiumUser({subscriptionPlan: "Platinum", isExpired: true})` ➞ `false`
4. `isPremiumUser({})` ➞ `false`

## Q6: Get Favorite Genres

**Problem story:** Recommendations dikhane ke liye backend ko genres ki array bhejni padti hai, jo ek nested user object me padi hoti hai.
**Problem to solve:** Profile object ke andar `preferences` object, uske andar `genres` array hai. Optional chaining ya conditional check lagao taaki app crash na ho agar key na mile. (Empty array return karo agar missing hai).
**Starter code snippet:**

```javascript
const getGenres = (profile) => {
  // Your code here
};
```

**Test cases:**

1. `getGenres({preferences: {genres: ["Action", "Sci-Fi"]}})` ➞ `["Action", "Sci-Fi"]`
2. `getGenres({preferences: {}})` ➞ `[]`
3. `getGenres({})` ➞ `[]`
4. `getGenres({preferences: {genres: []}})` ➞ `[]`

## Q7: Delete Property from Settings

**Problem story:** App version update hua aur ek purani setting (jaise "flashEnabled") ab deprecated ho gayi hai. Ise memory aur payload se remove karna hai.
**Problem to solve:** Ek object (settings) aur ek string (key) lo. Delete operator ya restructuring se us key ko object se hatakar naya object return karo.
**Starter code snippet:**

```javascript
const removeSetting = (settings, keyToRemove) => {
  // Your code here
};
```

**Test cases:**

1. `removeSetting({flash: true, volume: 50}, "flash")` ➞ `{volume: 50}`
2. `removeSetting({a: 1, b: 2}, "c")` ➞ `{a: 1, b: 2}`
3. `removeSetting({}, "a")` ➞ `{}`
4. `removeSetting({test: 1}, "test")` ➞ `{}`

## Q8: Count Watched Episodes

**Problem story:** User profile me ek object hai `watchedSeries` jisme keys TV shows ke naam hain aur values arrays hain (dekhi hui episode numbers ki). Total episodes kitne dekhe nikalne hain.
**Problem to solve:** `for...in` loop lagakar ya object methods use karke saari arrays ki length ka sum return karo.
**Starter code snippet:**

```javascript
const totalEpisodesWatched = (watchedSeries) => {
  // Your code here
};
```

**Test cases:**

1. `totalEpisodesWatched({ "Friends": [1,2,3], "Dark": [1,2] })` ➞ `5`
2. `totalEpisodesWatched({ "Got": [10] })` ➞ `1`
3. `totalEpisodesWatched({})` ➞ `0`
4. `totalEpisodesWatched({ "ShowA": [], "ShowB": [1] })` ➞ `1`

## Q9: Update Avatar

**Problem story:** Profile edit screen pe user ne naya avatar choose kiya hai. State me user object ko update karna hai immutable tarike se.
**Problem to solve:** Original object me bina changes kiye (spread operator ya `Object.assign` se) nayi avatar URL inject karke new object bhejo.
**Starter code snippet:**

```javascript
const updateAvatar = (userProfile, newAvatarUrl) => {
  // Your code here
};
```

**Test cases:**

1. `updateAvatar({name: "Sam"}, "url1")` ➞ `{name: "Sam", avatar: "url1"}`
2. `updateAvatar({name: "Sam", avatar: "old"}, "new")` ➞ `{name: "Sam", avatar: "new"}`
3. `updateAvatar({}, "img.png")` ➞ `{avatar: "img.png"}`
4. `updateAvatar({a: 1}, "")` ➞ `{a: 1, avatar: ""}`

## Q10: Profile Name Formatter

**Problem story:** Profile names UI me hamesha "First M." format me hone chahiye. (e.g. "Rahul Sharma" -> "Rahul S.")
**Problem to solve:** String input ko space se split karo. Agar last name hai, toh uska pehla character nikaalo aur "." lagao. Combine karke return karo.
**Starter code snippet:**

```javascript
const formatProfileName = (fullName) => {
  // Your code here
};
```

**Test cases:**

1. `formatProfileName("Rahul Sharma")` ➞ `"Rahul S."`
2. `formatProfileName("Amit")` ➞ `"Amit"`
3. `formatProfileName("Neha Singh Rajput")` ➞ `"Neha S."`
4. `formatProfileName("")` ➞ `""`

## Q11: Verify Age Restriction Mode

**Problem story:** Agar profile "Kids" mode me hai, toh certain adult content block hona chahiye.
**Problem to solve:** Ek profile object aur ek content rating (string, e.g. "R", "PG-13", "G") lo. Agar profile `isKidsMode: true` hai aur rating "R" ya "PG-13" hai, toh `false` (blocked) return karo, otherwise `true`.
**Starter code snippet:**

```javascript
const canWatchContent = (profile, rating) => {
  // Your code here
};
```

**Test cases:**

1. `canWatchContent({isKidsMode: true}, "R")` ➞ `false`
2. `canWatchContent({isKidsMode: true}, "G")` ➞ `true`
3. `canWatchContent({isKidsMode: false}, "R")` ➞ `true`
4. `canWatchContent({isKidsMode: true}, "PG-13")` ➞ `false`

## Q12: Reset Watch History

**Problem story:** User settings me "Clear Watch History" ka button dabata hai.
**Problem to solve:** User object input lo. Uski `watchHistory` key par array ko empty kar do aur modified user object return karo.
**Starter code snippet:**

```javascript
const clearHistory = (userProfile) => {
  // Your code here
};
```

**Test cases:**

1. `clearHistory({name: "A", watchHistory: ["m1", "m2"]})` ➞ `{name: "A", watchHistory: []}`
2. `clearHistory({name: "B", watchHistory: []})` ➞ `{name: "B", watchHistory: []}`
3. `clearHistory({name: "C"})` ➞ `{name: "C", watchHistory: []}` // Handle missing key gracefully
4. `clearHistory({})` ➞ `{watchHistory: []}`
