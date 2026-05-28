# Module 6: Role-Based Access & Security Rules

**Starter Story:** Kisi bhi SaaS Admin panel ko secure rakhna top priority hai. Yahan "TechOps" team ke portal me aap code kar rahe hain jahan arrays aur nested objects se deal karke ye decide karna hai ki kis user ko kaunse component dikhenge aur kaunse routes accessible honge. Conditional statements, loops, aur Boolean logic ka perfect use karna hi is module ka focus hai.

## Q1: Check Route Permission

**Problem story:** User profile route `/admin/settings` access karna chahta hai. User ke paas uski allowed routes ki array of strings hai.
**Problem to solve:** Ek allowed routes array aur target string route lo. Agar string array me explicitly match karti hai toh `true` warna `false`.
**Starter code snippet:**

```javascript
const canAccessRoute = (allowedRoutes, targetRoute) => {
  // Your code here
};
```

**Test cases:**

1. `canAccessRoute(["/home", "/admin/settings"], "/admin/settings")` ➞ `true`
2. `canAccessRoute(["/home", "/profile"], "/admin/settings")` ➞ `false`
3. `canAccessRoute([], "/home")` ➞ `false`
4. `canAccessRoute(["/*"], "/*")` ➞ `true`

## Q2: Has SuperAdmin Rights

**Problem story:** SaaS system me hierarchical roles hote hain. SuperAdmin hone ke liye roles array me 'superadmin' hona zaruri hai, OR user object ki `overridePrivilege` flag true honi chahiye.
**Problem to solve:** User object input lo. Return `true` agar `overridePrivilege` true hai, YA phir `roles` array me "superadmin" shamil hai.
**Starter code snippet:**

```javascript
const isSuperAdmin = (user) => {
  // Your code here
};
```

**Test cases:**

1. `isSuperAdmin({roles: ["user"], overridePrivilege: true})` ➞ `true`
2. `isSuperAdmin({roles: ["superadmin", "editor"], overridePrivilege: false})` ➞ `true`
3. `isSuperAdmin({roles: ["admin"], overridePrivilege: false})` ➞ `false`
4. `isSuperAdmin({roles: []})` ➞ `false`

## Q3: Feature Flag Evaluator

**Problem story:** Hum naye features selectively rollout karte hain. System object me feature flags padi hain.
**Problem to solve:** Do inputs lo, ek features object `{ betaUI: true, newChart: false }` aur ek featureName string. Return boolean value. Agar flag completely missing hai toh `false` default karo.
**Starter code snippet:**

```javascript
const isFeatureEnabled = (featuresObj, featureName) => {
  // Your code here
};
```

**Test cases:**

1. `isFeatureEnabled({betaUI: true}, "betaUI")` ➞ `true`
2. `isFeatureEnabled({betaUI: true}, "newChart")` ➞ `false` // missing defaults to false
3. `isFeatureEnabled({newChart: false}, "newChart")` ➞ `false`
4. `isFeatureEnabled({}, "any")` ➞ `false`

## Q4: Deep Clone Permissions

**Problem story:** Ek role se doosre naye role ko template karte waqt user permissions (array of strings) reference se copy nahi honi chahiye (mutability issue).
**Problem to solve:** Array of strings lo aur usko accurately naye array me clone karke wapas bhejo bina reference break kiye spread ya slice use karke.
**Starter code snippet:**

```javascript
const clonePermissions = (permissions) => {
  // Your code here
};
```

**Test cases:**

1. `const a = ["read"]; const b = clonePermissions(a); b.push("write"); a` ➞ `["read"]`
2. `clonePermissions([])` ➞ `[]`
3. `clonePermissions(["x", "y"])` ➞ `["x", "y"]` (New array with exact values)
4. `clonePermissions(["*"])` ➞ `["*"]`

## Q5: Validate API Key Format

**Problem story:** Security audit ke hisaab se sabhi backend tokens ya keys hamesha exact 32 characters long aur 'sk*' se start honi chahiye.
**Problem to solve:** Token string ko check karo, agar wo startsWith 'sk*' hai aur length exactly 32 hai toh `true` warna `false`.
**Starter code snippet:**

```javascript
const isValidApiKey = (key) => {
  // Your code here
};
```

**Test cases:**

1. `isValidApiKey("sk_12345678901234567890123456789")` ➞ `true` (length 32)
2. `isValidApiKey("sk_short")` ➞ `false`
3. `isValidApiKey("pk_12345678901234567890123456789")` ➞ `false` (wrong prefix)
4. `isValidApiKey("")` ➞ `false`

## Q6: Redact Sensitive Info

**Problem story:** Error logs server pe bhejne se pehle object me se "password" aur "credit_card" keys ko redact (replace with "**") karna zaruri hai.
**Problem to solve:** User payload object ko loop karo aur agar password ya credit_card field mile toh unki original string ki jagah "**" set kar do.
**Starter code snippet:**

```javascript
const redactPayload = (payload) => {
  // Your code here
};
```

**Test cases:**

1. `redactPayload({name: "A", password: "123"})` ➞ `{name: "A", password: "****"}`
2. `redactPayload({credit_card: "1111-2222"})` ➞ `{credit_card: "****"}`
3. `redactPayload({name: "B", age: 20})` ➞ `{name: "B", age: 20}`
4. `redactPayload({})` ➞ `{}`

## Q7: Require 2FA Validation

**Problem story:** Agar user object me `requires2FA` true hai toh check karo ki session array me "2fa_verified" timestamp maujud hai ya nahi.
**Problem to solve:** User `{requires2FA: true/false}` aur `sessionTags` (array of strings) input lo. Agar requires2FA true hai aur sessionTags me "2fa_verified" nahi hai toh return `false` (block access), else `true`.
**Starter code snippet:**

```javascript
const checkTwoFactorAuth = (user, sessionTags) => {
  // Your code here
};
```

**Test cases:**

1. `checkTwoFactorAuth({requires2FA: true}, ["login", "2fa_verified"])` ➞ `true`
2. `checkTwoFactorAuth({requires2FA: true}, ["login"])` ➞ `false`
3. `checkTwoFactorAuth({requires2FA: false}, ["login"])` ➞ `true`
4. `checkTwoFactorAuth({requires2FA: false}, [])` ➞ `true`

## Q8: Find Malicious Scripts

**Problem story:** Input fields me hack attempt check karna hai. Agar kisi form values (array of strings) me "" ya "eval(" substring aata hai toh reject karna hai.
**Problem to solve:** Array of strings pe loop karo aur agar kisi me alert terms (like or eval) milen toh `true` (meaning malicious found) return karo, else `false`.
**Starter code snippet:**

```javascript
const isMaliciousInput = (inputs) => {
  // Your code here
};
```

**Test cases:**

1. `isMaliciousInput(["hello", "<script>alert(1)</script>"])` ➞ `true`
2. `isMaliciousInput(["clean", "text", "here"])` ➞ `false`
3. `isMaliciousInput(["eval(alert)"])` ➞ `true`
4. `isMaliciousInput([])` ➞ `false`

## Q9: Extract Blocked IPs

**Problem story:** Security config object me ek property `firewall` hai jiske andar array of blocked IPs hain. Kabhi-kabhi firewall property undefined ho sakti hai.
**Problem to solve:** `config.firewall.blockedIPs` se array fetch karo safely (bina crash kiye). Agar missing hai toh empty array return karo.
**Starter code snippet:**

```javascript
const getBlockedIPs = (config) => {
  // Your code here
};
```

**Test cases:**

1. `getBlockedIPs({firewall: {blockedIPs: ["1.1.1.1"]}})` ➞ `["1.1.1.1"]`
2. `getBlockedIPs({firewall: {}})` ➞ `[]`
3. `getBlockedIPs({})` ➞ `[]`
4. `getBlockedIPs({firewall: null})` ➞ `[]`

## Q10: Compute Access Hash (Mock)

**Problem story:** Route protection ke liye username length aur roles count mila kar ek mock integer hash generate kiya jata hai simple authentication checks me.
**Problem to solve:** User object le. `(user.username.length * user.roles.length)` calculate karo aur result integer return karo. Handle cases where fields are empty strings/arrays.
**Starter code snippet:**

```javascript
const computeMockHash = (user) => {
  // Your code here
};
```

**Test cases:**

1. `computeMockHash({username: "admin", roles: ["r1", "r2"]})` ➞ `10` (5 \* 2)
2. `computeMockHash({username: "a", roles: ["x"]})` ➞ `1`
3. `computeMockHash({username: "", roles: ["x", "y"]})` ➞ `0`
4. `computeMockHash({username: "user1", roles: []})` ➞ `0`

## Q11: Apply Default Permissions (Spread)

**Problem story:** Naye user account ko automatically basic privileges object (read: true, write: false) milne chahiye.
**Problem to solve:** `defaultPrivileges` (read: true, write: false) ko given `userPrivileges` (agar custom kuch hai) object se merge karo (userPrivileges ko override karne do defaults pe). Naya combined object return karo.
**Starter code snippet:**

```javascript
const assignPermissions = (userPrivileges) => {
  const defaults = { read: true, write: false };
  // Your code here
};
```

**Test cases:**

1. `assignPermissions({ write: true })` ➞ `{ read: true, write: true }`
2. `assignPermissions({})` ➞ `{ read: true, write: false }`
3. `assignPermissions({ read: false, admin: true })` ➞ `{ read: false, write: false, admin: true }`
4. `assignPermissions({ delete: true })` ➞ `{ read: true, write: false, delete: true }`

## Q12: Expire Idle Sessions

**Problem story:** Ek background timer loop karta hai. Jo sessions 30 minute se idle hain, unko system log out (isActive = false) kar deta hai.
**Problem to solve:** Array of session objects lo. Agar kisi ki `idleMinutes > 30` hai, uski `isActive` state ko `false` kardo aur modified array return karo.
**Starter code snippet:**

```javascript
const expireIdleSessions = (sessions) => {
  // Your code here
};
```

**Test cases:**

1. `expireIdleSessions([{id: 1, idleMinutes: 35, isActive: true}])` ➞ `[{id: 1, idleMinutes: 35, isActive: false}]`
2. `expireIdleSessions([{id: 2, idleMinutes: 10, isActive: true}])` ➞ `[{id: 2, idleMinutes: 10, isActive: true}]`
3. `expireIdleSessions([])` ➞ `[]`
4. `expireIdleSessions([{idleMinutes: 30, isActive: true}, {idleMinutes: 31, isActive: true}])` ➞ `[{idleMinutes: 30, isActive: true}, {idleMinutes: 31, isActive: false}]`
