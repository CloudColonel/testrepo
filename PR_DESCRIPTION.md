# Capitalize Function Fix

## Summary
Fixed the capitalize function that was incorrectly lowercasing the entire string instead of capitalizing the first letter.

## Changes Made
- Updated `src/string-utils.ts` to properly capitalize the first letter
- Added handling for empty strings

## Before
```typescript
export function capitalize(str: string): string {
    return str.toLowerCase(); // Bug: should capitalize first letter
}
```

## After
```typescript
export function capitalize(str: string): string {
    if (!str) return str;
    return str.charAt(0).toUpperCase() + str.slice(1).toLowerCase();
}
```

## Testing
All test cases passed:
- capitalize("hello") → "Hello" ✓
- capitalize("WORLD") → "World" ✓  
- capitalize("test") → "Test" ✓
- capitalize("") → "" ✓
- capitalize("a") → "A" ✓
