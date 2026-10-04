# Code Quality Kit

Use this skill to write clean, organized, and maintainable code that follows senior programmer practices and conventions.

## 1. Code structure and organization

### File and folder layout

- Keep related files close together
- Use a consistent naming convention (camelCase for functions/variables, PascalCase for classes/components)
- One responsibility per file or module
- Group by feature or domain, not by type

**Good:**
```
src/
├── features/
│   ├── auth/
│   │   ├── login.tsx
│   │   ├── signup.tsx
│   │   └── useAuth.ts
│   └── dashboard/
│       ├── overview.tsx
│       └── stats.tsx
```

**Avoid:**
```
src/
├── components/
│   ├── login.tsx
│   ├── signup.tsx
├── hooks/
│   └── useAuth.ts
```

### Module exports

- Export only what is needed
- Use named exports for clarity
- Avoid default exports unless the module has one clear purpose

```typescript
// Good
export { useAuth } from './useAuth'
export { AuthProvider } from './AuthProvider'

// Avoid
export default { useAuth, AuthProvider }
```

## 2. Naming conventions

### Functions and variables

- Use descriptive names that explain purpose, not just type
- Avoid abbreviations unless widely known (e.g., `id`, `api`)
- Boolean functions should start with `is`, `has`, `can`, or `should`

```typescript
// Good
const isUserLoggedIn = checkAuthStatus()
const getUserOrders = () => { /* ... */ }
const MAX_RETRY_ATTEMPTS = 3

// Avoid
const x = checkAuthStatus()
const getUO = () => { /* ... */ }
const MRA = 3
```

### Classes and components

- Use PascalCase
- Name components after what they render or do
- Avoid generic names like `Container`, `Wrapper`, `Manager`

```typescript
// Good
class AuthenticationService { /* ... */ }
export function ProductCard({ product }) { /* ... */ }

// Avoid
class Service { /* ... */ }
export function Component({ data }) { /* ... */ }
```

## 3. Function design

### Keep functions small and focused

- One function = one responsibility
- Ideal length: 5–20 lines (hard limit: 50)
- Extract nested logic into separate functions

```typescript
// Good
function validateEmail(email: string): boolean {
  return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)
}

function sendVerificationEmail(email: string): Promise<void> {
  if (!validateEmail(email)) throw new Error('Invalid email')
  return emailService.send(email, 'verify-token')
}

// Avoid
function signupUser(email: string, password: string): Promise<void> {
  if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)) throw new Error('Invalid email')
  if (password.length < 8) throw new Error('Password too short')
  const hashed = bcrypt.hash(password)
  const user = await db.users.create({ email, password: hashed })
  const token = jwt.sign({ userId: user.id })
  return emailService.send(email, token)
}
```

### Use early returns

- Return or throw early to reduce nesting
- Makes the happy path clearer

```typescript
// Good
function processUser(user: User | null): void {
  if (!user) return
  if (user.isInactive) return
  
  activateUser(user)
}

// Avoid
function processUser(user: User | null): void {
  if (user) {
    if (!user.isInactive) {
      activateUser(user)
    }
  }
}
```

## 4. Comments and documentation

### Comment the "why", not the "what"

- Code shows what it does; comments explain why
- Avoid obvious comments

```typescript
// Good
// Cache users for 5 minutes to reduce DB load during peak hours
const CACHE_TTL = 5 * 60 * 1000

// Avoid
// Set cache TTL to 5 minutes
const CACHE_TTL = 5 * 60 * 1000
```

### Document public APIs

- Use JSDoc for functions, classes, and exports
- Include parameter types, return type, and use case

```typescript
/**
 * Fetch user by ID with caching.
 * @param userId - The user's unique identifier
 * @returns User object or null if not found
 * @throws Error if database connection fails
 * 
 * @example
 * const user = await getUser(123)
 */
export async function getUser(userId: number): Promise<User | null> {
  // ...
}
```

## 5. Error handling

### Be explicit and specific

- Throw or return meaningful error messages
- Avoid silent failures
- Distinguish between expected errors and bugs

```typescript
// Good
if (!user) {
  throw new Error('User not found. Please check the user ID.')
}

if (user.email !== email) {
  return { success: false, reason: 'Email mismatch' }
}

// Avoid
if (!user) throw new Error('Error')
if (user.email !== email) return false
```

### Use try-catch at boundaries

- Wrap external calls (API, database, file system)
- Let domain logic throw naturally; catch at entry points

```typescript
// Good
async function handleUserSignup(req, res) {
  try {
    const user = await createUser(req.body)
    res.json({ success: true, user })
  } catch (error) {
    res.status(400).json({ error: error.message })
  }
}

// Inside: let it throw
async function createUser(data: SignupData): Promise<User> {
  if (!data.email) throw new Error('Email required')
  // ...
}
```

## 6. Testing and maintainability

### Write testable code

- Avoid tightly coupled dependencies
- Use dependency injection or configuration
- Keep side effects at the edges

```typescript
// Good: testable
function calculateTotal(items: Item[], tax: number): number {
  return items.reduce((sum, item) => sum + item.price, 0) * (1 + tax)
}

// Avoid: tightly coupled
function calculateTotal(items: Item[]): number {
  const tax = getTaxRate() // Hidden dependency
  const db = getDatabase()   // Side effect
  return items.reduce((sum, item) => sum + item.price, 0) * (1 + tax)
}
```

### Make code reviewable

- Limit pull requests to one logical change
- Keep lines under 80–100 characters
- Use consistent formatting (prettier, eslint)

## 7. Performance and readability

### Prefer clarity over cleverness

- Use readable logic over compact but obscure code
- Avoid premature optimization

```typescript
// Good: clear intent
const activeUsers = users.filter(u => u.status === 'active')

// Avoid: clever but harder to read
const activeUsers = users.filter(u => u.s === 'a')
const activeUsers = users.filter(({status}) => status[0] === 'a')
```

### Use constants for magic values

- Name what numbers or strings mean
- Makes code easier to update

```typescript
// Good
const MAX_LOGIN_ATTEMPTS = 5
const SESSION_TIMEOUT_MS = 30 * 60 * 1000

if (attempts >= MAX_LOGIN_ATTEMPTS) lockAccount()

// Avoid
if (attempts >= 5) lockAccount()
if (sessionAge > 1800000) logout()
```

## 8. Type safety (TypeScript)

### Use types to prevent errors

- Define interfaces for data shapes
- Avoid `any`; use `unknown` if needed
- Use strict mode

```typescript
// Good
interface User {
  id: number
  email: string
  isActive: boolean
}

function greetUser(user: User): string {
  return `Hello, ${user.email}`
}

// Avoid
function greetUser(user: any): string {
  return `Hello, ${user.email}`
}
```

## 9. Code review checklist

Before committing or pushing, ask:

- [ ] Does each function do one thing?
- [ ] Are variable and function names clear?
- [ ] Are error cases handled?
- [ ] Is the code testable?
- [ ] Are there obvious performance issues?
- [ ] Would a new team member understand this?
- [ ] Is there duplicated logic that should be extracted?
- [ ] Are there magic numbers or values that should be constants?

## Reference files

- `SKILL.md` — Overall storefront + admin skill
- `landing-page-kit.md` — Public-facing page patterns
- `admin-panel-kit.md` — Backend and admin UI patterns
- `ui-styling.md` — Component and styling conventions
