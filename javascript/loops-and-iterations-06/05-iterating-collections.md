# Module 5: Iterating Collections (for...of Loop)

## Q1: Counting Wallet Cash

**Scenario:** Aapke batwe (wallet) mein notes ka ek array hai [500, 200, 100, 50].
**Requirements:** Naye modern for...of loop ka use karke saare notes ka total (sum) nikal kar return karein.
**Starter Code:**

```javascript
function countWallet(notesArray) {
  // TODO: Use for...of to iterate array elements directly
}
```

**Test Cases:**

- countWallet([500, 100, 50]) -> Expected: 650
- countWallet([20]) -> Expected: 20
- countWallet([]) -> Expected: 0

## Q2: Counting Vowels in a String

**Scenario:** JavaScript mein for...of arrays ke alawa strings par bhi chalta hai! Humein string mein kitne vowels (a, e, i, o, u) hain ye ginna hai.
**Requirements:** String par for...of chalayein. Har character check karein (assume lowercase hi aayega). Count return karein.
**Starter Code:**

```javascript
function countVowels(word) {
  // TODO: Iterate over characters using for...of
}
```

**Test Cases:**

- countVowels("education") -> Expected: 5
- countVowels("xyz") -> Expected: 0
- countVowels("apple") -> Expected: 2

## Q3: Filtering Spam Words

**Scenario:** Comments array me galti se "click here" aur "lottery" jaise words aate hain. Unhe hatana hai.
**Requirements:** for...of loop lagakar check karein. Agar word "spam" hai toh naye array me mat daalo. Baki words ko daal kar return karein.
**Starter Code:**

```javascript
function filterComments(commentsList) {
  // TODO: Filter out the exact string "spam"
}
```

**Test Cases:**

- filterComments(["nice", "spam", "good video"]) -> Expected: ["nice", "good video"]
- filterComments(["spam", "spam"]) -> Expected: []
- filterComments(["hello"]) -> Expected: ["hello"]

## Q4: The Longest Word Contest

**Scenario:** Bacho ke spelling contest array me sabse lamba (longest) word dhundna hai.
**Requirements:** for...of se iterate karein. Ek longest string maintain karein aur uski .length se comparison karte hue result find karein.
**Starter Code:**

```javascript
function getLongestWord(wordsArray) {
  // TODO: Return the string with max length
}
```

**Test Cases:**

- getLongestWord(["Apple", "Watermelon", "Kiwi"]) -> Expected: "Watermelon"
- getLongestWord(["A", "BC", "D"]) -> Expected: "BC"
- getLongestWord([]) -> Expected: ""

## Q5: Appending "Ji" Respectfully

**Scenario:** Shaadi ke invitation card me sabhi naamo ke aage "Ji" (e.g. "Ramesh Ji") lagana compulsory hai.
**Requirements:** Array ke har element par for...of chalayein, " Ji" concatenate karein aur ek naye array mein save kar ke return karein.
**Starter Code:**

```javascript
function addRespect(namesList) {
  // TODO: Append " Ji" to each name
}
```

**Test Cases:**

- addRespect(["Rahul", "Neha"]) -> Expected: ["Rahul Ji", "Neha Ji"]
- addRespect(["Papa"]) -> Expected: ["Papa Ji"]
- addRespect([]) -> Expected: []

## Q6: YouTube Playlist Watch Time

**Scenario:** Playlist ki har video ka duration minute me array me diya hai.
**Requirements:** for...of use karke total minutes ko gino. Agar total minutes > 60 hain, toh string "Too Long" return karo, warna total number return karo.
**Starter Code:**

```javascript
function checkWatchTime(videoLengths) {
  // TODO: Sum lengths using for...of and check condition
}
```

**Test Cases:**

- checkWatchTime([20, 20, 15]) -> Expected: 55
- checkWatchTime([30, 40]) -> Expected: "Too Long"
- checkWatchTime([10]) -> Expected: 10

## Q7: Are the Students Sitting Height-Wise? (Sorted Array check)

**Scenario:** Assembly mein bache array of heights mein khade hain. Humein pata karna hai ki kya unki height perfectly strictly increasing (sort) order mein hai ya nahi.
**Requirements:** for...of se thoda mushkil hai kyunki index nahi hota direct. Aapko previous element ek variable me store karke comparison karna hoga! Return boolean.
**Starter Code:**

```javascript
function isSorted(heights) {
  // TODO: Track the previous item to check if array is sorted ascending
}
```

**Test Cases:**

- isSorted([120, 130, 140]) -> Expected: true
- isSorted([140, 130, 150]) -> Expected: false
- isSorted([100]) -> Expected: true

## Q8: Character Occurence Count

**Scenario:** Ek user ka password string aaya hai. Pata lagana hai usme number "8" kitni baar aaya hai.
**Requirements:** String par for...of lagakar count karein ki "8" char kitni baar loop hua. Number count return karein.
**Starter Code:**

```javascript
function countEight(passwordStr) {
  // TODO: Iterate string characters and count "8"
}
```

**Test Cases:**

- countEight("88AABB8") -> Expected: 3
- countEight("1234567") -> Expected: 0
- countEight("8") -> Expected: 1

## Q9: The Tally Master (Creating an Object Frequency Map)

**Scenario:** Sabji wale bhaiya ke paas list hai: ["Aloo", "Pyaz", "Aloo"]. Unhe pata lagana hai kaunsi sabji kitni hai. (This is a classic algorithmic concept).
**Requirements:** Ek khali object {} banayein. for...of se array padhein. Agar property exists kare toh usko +1 karein, nahi to 1 se start karein. Object return karein.
**Starter Code:**

```javascript
function generateTally(itemsArray) {
  // TODO: Convert array items into an object frequency map
}
```

**Test Cases:**

- generateTally(["A", "B", "A"]) -> Expected: { A: 2, B: 1 }
- generateTally(["Apple"]) -> Expected: { Apple: 1 }
- generateTally([]) -> Expected: {}

## Q10: Sentence Builder (Joining words manually)

**Scenario:** SMS bundle array of words "Hum", "aaj", "aayenge". .join(" ") built-in kaam nahi kar raha. Humein manually string jodni hai.
**Requirements:** for...of loop lagayein. Har word ke baad ek space add karein aur aakhir string ko .trim() karke return karein taaki end ka extra space hat jaye.
**Starter Code:**

```javascript
function buildSentence(wordsList) {
  // TODO: Concatenate strings with spaces
}
```

**Test Cases:**

- buildSentence(["Kaam", "karo", "bhai"]) -> Expected: "Kaam karo bhai"
- buildSentence(["Hi"]) -> Expected: "Hi"
- buildSentence([]) -> Expected: ""
