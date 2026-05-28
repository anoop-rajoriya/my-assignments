# Module 1: User Registration & Onboarding Pipeline

**Starter Story:** Humara startup 'QuickCart' ek growing e-commerce platform hai. Daily hazaron users aate hain, par sign-up forms me bohot ghalatiyan karte hain. Backend server pe load kam karne ke liye, hume data ko API call se pehle hi validate aur sanitize karna hai. Aapka task in raw user inputs ko clean, safe aur properly formatted data me convert karna hai.

## Q1: Email Normalization

**Problem story:** Users aksar email ke aage-peeche spaces chhod dete hain ya capital letters use karte hain. Isse duplicate user check fail ho jata hai.
**Problem to solve:** Ek function likho jo input string se leading/trailing spaces hataye aur sabko lowercase kare. Agar input string nahi hai toh `null` return karo.
**Starter code snippet:**

```javascript
const normalizeEmail = (email) => {
  // Your code here
};
```

**Test cases:**

1. `normalizeEmail("  Hello@World.com ")` ➞ `"hello@world.com"`
2. `normalizeEmail("ADMIN@APP.IN")` ➞ `"admin@app.in"`
3. `normalizeEmail("user@domain.com")` ➞ `"user@domain.com"`
4. `normalizeEmail(12345)` ➞ `null`

## Q2: Phone Number Extractor

**Problem story:** Phone numbers form me alag-alag format (jaise `+91-987-654`, `(91) 987654`) me aate hain. Hume database ke liye sirf pure numbers chahiye.
**Problem to solve:** String me loop chala kar ya method use karke sirf digits (`0-9`) extract karo aur ek single string me combine karo.
**Starter code snippet:**

```javascript
const extractDigits = (phoneStr) => {
  // Your code here
};
```

**Test cases:**

1. `extractDigits("+91-987-654")` ➞ `"91987654"`
2. `extractDigits("(91) 9876 543 210")` ➞ `"919876543210"`
3. `extractDigits("NoNumbersHere")` ➞ `""`
4. `extractDigits("123abc456")` ➞ `"123456"`

## Q3: Password Strength Checker

**Problem story:** Weak passwords account hack hone ka sabse bada reason hain. Hume check karna hai ki password ek basic security standard meet kare.
**Problem to solve:** Check karo ki password kam se kam 8 characters ka ho, usme kam se kam ek number ho, aur ek special character (`@, #, $`) ho. Boolean return karo.
**Starter code snippet:**

```javascript
const isStrongPassword = (pwd) => {
  // Your code here
};
```

**Test cases:**

1. `isStrongPassword("Pass@123")` ➞ `true`
2. `isStrongPassword("password")` ➞ `false`
3. `isStrongPassword("short@1")` ➞ `false`
4. `isStrongPassword("NoNumbers@Here")` ➞ `false`

## Q4: Username Generator

**Problem story:** Jab user sign up karta hai, hume automatically unke full name se ek unique username generate karna hota hai taaki unhe option diya ja sake.
**Problem to solve:** Full name string ko array me split karo, pehle naam ka first letter aur last name poora combine karo. Sab lowercase me hona chahiye. (e.g., "Rahul Sharma" -> "rsharma").
**Starter code snippet:**

```javascript
const generateUsername = (fullName) => {
  // Your code here
};
```

**Test cases:**

1. `generateUsername("Amit Kumar")` ➞ `"akumar"`
2. `generateUsername("John Doe")` ➞ `"jdoe"`
3. `generateUsername("Single")` ➞ `"single"`
4. `generateUsername("  Sara   Khan  ")` ➞ `"skhan"`

## Q5: Empty Fields Validator

**Problem story:** Registration object me kuch fields optional hain aur kuch mandatory. Hume check karna hai ki koi mandatory field empty string, null, ya undefined toh nahi hai.
**Problem to solve:** Ek object aur ek mandatory fields ka array input milega. Check karo agar unme se koi bhi key object me missing ya empty hai. `true` (if all present) ya `false` return karo.
**Starter code snippet:**

```javascript
const validateMandatoryFields = (userData, requiredFields) => {
  // Your code here
};
```

**Test cases:**

1. `validateMandatoryFields({name: "A", age: 20}, ["name"])` ➞ `true`
2. `validateMandatoryFields({name: "", age: 20}, ["name"])` ➞ `false`
3. `validateMandatoryFields({email: "x@y.com"}, ["name", "email"])` ➞ `false`
4. `validateMandatoryFields({}, [])` ➞ `true`

## Q6: Age Eligibility Check

**Problem story:** Platform par 18 saal se kam umar ke users allowed nahi hain. User apna birth year deta hai, aur hume validate karna hai.
**Problem to solve:** Current year (e.g., 2026) fix rakhte hue, user ka birth year input lo aur age calculate karo. Agar >= 18 hai toh `true`, warna `false`.
**Starter code snippet:**

```javascript
const checkEligibility = (birthYear) => {
  const currentYear = 2026;
  // Your code here
};
```

**Test cases:**

1. `checkEligibility(2000)` ➞ `true`
2. `checkEligibility(2010)` ➞ `false`
3. `checkEligibility(2008)` ➞ `true`
4. `checkEligibility(2026)` ➞ `false`

## Q7: Address Object Stringifier

**Problem story:** Shipping backend API ek single address string accept karti hai, lekin frontend pe humne user se address alag-alag fields (street, city, state, zip) me liya hai.
**Problem to solve:** Object ke properties ko combine karke ek single comma-separated string banao. Agar koi property missing hai, toh use skip karo.
**Starter code snippet:**

```javascript
const formatAddress = (addressObj) => {
  // Your code here
};
```

**Test cases:**

1. `formatAddress({city: "Delhi", zip: "110001"})` ➞ `"Delhi, 110001"`
2. `formatAddress({street: "M.G Road", state: "MH"})` ➞ `"M.G Road, MH"`
3. `formatAddress({})` ➞ `""`
4. `formatAddress({street: "A", city: "B", zip: "C"})` ➞ `"A, B, C"`

## Q8: Clean Disallowed Characters

**Problem story:** Bio section me users kabhi-kabhi HTML tags (`<`, `>`) daal dete hain jo XSS attacks ka reason ban sakte hain. Hume basic sanitization karni hai.
**Problem to solve:** Input string me se `<` aur `>` characters ko replace karke empty space ya remove kar do.
**Starter code snippet:**

```javascript
const sanitizeBio = (bioString) => {
  // Your code here
};
```

**Test cases:**

1. `sanitizeBio("Hello <script>alert(1)</script>")` ➞ `"Hello scriptalert(1)/script"`
2. `sanitizeBio("I love <coding>")` ➞ `"I love coding"`
3. `sanitizeBio("Normal text")` ➞ `"Normal text"`
4. `sanitizeBio("<<>>")` ➞ `""`

## Q9: Array of Roles validation

**Problem story:** Jab admin user banata hai, uski roles array hoti hai. Agar array me "admin" hai, toh extra privileges milengi.
**Problem to solve:** Check karo agar input array me "admin" string exist karti hai (case-insensitive). Return `true` ya `false`.
**Starter code snippet:**

```javascript
const isAdmin = (rolesArray) => {
  // Your code here
};
```

**Test cases:**

1. `isAdmin(["editor", "Admin", "viewer"])` ➞ `true`
2. `isAdmin(["viewer", "user"])` ➞ `false`
3. `isAdmin([])` ➞ `false`
4. `isAdmin(["ADMINISTRATOR"])` ➞ `false`

## Q10: Profile Completeness Score

**Problem story:** Hum chahte hain ki user apna profile poora bhare. Humhe profile fields count karke completion percentage dikhani hai UI par.
**Problem to solve:** Ek profile object lo. Object mein total 5 expected keys hain (name, email, phone, bio, avatar). Jo available (truthy) hain unka count nikaal ke percentage (0 se 100) return karo.
**Starter code snippet:**

```javascript
const calculateProfileScore = (profile) => {
  // Your code here
};
```

**Test cases:**

1. `calculateProfileScore({name: "A", email: "B"})` ➞ `40`
2. `calculateProfileScore({name: "A", email: "B", phone: "C", bio: "D", avatar: "E"})` ➞ `100`
3. `calculateProfileScore({})` ➞ `0`
4. `calculateProfileScore({name: "", email: null})` ➞ `0`

## Q11: Referral Code Formatter

**Problem story:** Referral codes user randomly type karte hain. Hume database me unhe strictly uppercase aur max 8 characters ka store karna hai.
**Problem to solve:** String ko uppercase karo, aur agar length 8 se zyada hai toh trim (slice) karke 8 chars ki bana do.
**Starter code snippet:**

```javascript
const formatReferral = (code) => {
  // Your code here
};
```

**Test cases:**

1. `formatReferral("welcome20")` ➞ `"WELCOME2"`
2. `formatReferral("abc")` ➞ `"ABC"`
3. `formatReferral("superlongcode")` ➞ `"SUPERLON"`
4. `formatReferral("")` ➞ `""`

## Q12: OTP Generator (Mock)

**Problem story:** Login ke waqt hum ek mock OTP bhejna chahte hain. Halanki math.random API use nahi karni, hum timestamp ya basic math logic se 4 digit generate karenge.
**Problem to solve:** Ek closure/IIFE banao jisme ek counter ho. Har call pe counter 1 se badhe aur ek 4-digit string return kare. Start "1000" se karo.
**Starter code snippet:**

```javascript
const generateOTP = (() => {
  // Your code here
})();
```

**Test cases:**

1. `generateOTP()` ➞ `"1000"`
2. `generateOTP()` ➞ `"1001"`
3. `generateOTP()` ➞ `"1002"`
4. `generateOTP()` ➞ `"1003"`
