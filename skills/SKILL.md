# Code Quality Kit

Use this skill when the task is to write code that is clean, maintainable, scalable, and easy for senior engineers to review.

## Goal

Write code that is:
- readable
- organized
- testable
- consistent with team conventions
- easy to extend without introducing technical debt

## 1. Write for clarity first

Prefer code that is obvious to a teammate over clever code that is hard to follow.

### Good
```ts
const activeUsers = users.filter((user) => user.isActive)
```

### Avoid
```ts
const a = users.filter((u) => u.isActive)
```

Avoid writing code that only looks smart. Senior engineers usually optimize for readability, not micro-cleverness.

## 2. Keep functions small and focused

A function should do one thing well. If it has too many responsibilities, split it up.

### Good
```ts
function calculateTotal(items: number[]) {
  return items.reduce((sum, item) => sum + item, 0)
}

function formatCurrency(amount: number) {
  return new Intl.NumberFormat('en-US', {
    style: 'currency',
    currency: 'USD'
  }).format(amount)
}
```

### Avoid
```ts
function calculateAndDisplayTotal(items: number[]) {
  const total = items.reduce((sum, item) => sum + item, 0)
  console.log(total)
  return `$${total.toFixed(2)}`
}
```

## 3. Use strong naming

Names should communicate intent.

### Good
```ts
const isUserAuthenticated = user !== null && user.token !== null
const getUserOrders = async (userId: string) => { /* ... */ }
```

### Avoid
```ts
const ok = user !== null && user.token !== null
const doStuff = async (id: string) => { /* ... */ }
```

## 4. Organize your project

Use modular structure and clear folders.

```text
src/
  components/
  features/
  hooks/
  lib/
  utils/
  services/
```

Good organization patterns:
- one responsibility per file
- group by feature or domain
- avoid mixing business logic and UI logic in the same file
- keep shared code in `lib`, `utils`, or service modules

## 5. Keep code consistent

Use consistent patterns across the codebase:
- one style for variable naming
- one style for error handling
- one style for API/service calls
- one style for file structure

Consistency reduces cognitive load and makes code easier to review.

## 6. Prefer explicit logic over hidden behavior

Avoid magic values and unclear branching.

### Good
```ts
const MAX_RETRY_ATTEMPTS = 3

if (attempts >= MAX_RETRY_ATTEMPTS) {
  throw new Error('Too many retry attempts')
}
```

### Avoid
```ts
if (attempts >= 3) {
  throw new Error('Error')
}
```

## 7. Handle errors clearly

Good code fails clearly and predictably.

### Good
```ts
try {
  const result = await fetchData()
  return result
} catch (error) {
  console.error('Failed to fetch data:', error)
  throw new Error('Unable to load data')
}
```

### Avoid
```ts
try {
  await fetchData()
} catch {
  // ignored
}
```

## 8. Use types and validation

Strong typing catches issues earlier.

```ts
interface User {
  id: string
  email: string
  isActive: boolean
}

function getDisplayName(user: User) {
  return user.email.split('@')[0]
}
```

If possible, validate inputs and shape data before using it.

## 9. Keep it maintainable

Senior code is usually:
- specific
- readable
- modular
- tested
- easy to refactor

### Best practices
- avoid deeply nested conditionals
- avoid large classes with many unrelated methods
- use small utility functions
- prefer composition over duplication
- extract repeated logic into reusable code

## 10. Write code like a senior engineer

Senior developers usually do the following:
- simplify before optimizing
- reduce unnecessary complexity
- make logic obvious
- document intent when needed
- keep comments helpful, not noisy
- ensure naming reflects purpose
- prefer maintainability over cleverness

## 11. Review checklist

Before shipping, ask:
- Is this function too long?
- Is the naming clear?
- Is the code easy to test?
- Is there duplicate logic?
- Are error states handled?
- Is the structure easy to follow?
- Can another developer understand the intent quickly?

## 12. Default mindset

When in doubt:
- simplify
- separate concerns
- clarify names
- reduce duplication
- write readable code
- make the next engineer's job easier

This is the standard expected from strong engineering work.
