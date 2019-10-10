# Thinking in TypeScript

by Godfrey Chan

## Introduction

TypeScript can help us annotate and document our code signatures. Instead of trying to document everything in code comments, we can implement strict typing. For example:

```typescript
let i: number;

i = 0; // Ok
i = "Hello"; // Error

// Define our own interface for what we expect
interface Options {
  margin: boolean;
}

let options: Options;

options = { margin: true }; // Ok
options = {}; // Error

// The `:` is used everywhere to denote types
function greetingsFor(name: string): string {
  return `Hello, ${name}!`;
}
```

## `undefined`

In TypeScript 1, `undefined` and `null` were allowed to be assigned everywhere! In TypeScript 2, we now have strict null checks to prevent this.

```typescript
// TypeScript 1
let i: number;

i = null; // Ok

// TypeScript 2
let i: number;

i = 1; // Ok
i = undefined; // Error

let k: number | undefined;

k = undefined; // Ok
k = 3; // Ok
k = null; // Error
```

## Warning Signs: `undefined` and unexpected

### Bare `return`'s

Using `return` without a value - does the caller expect `undefined`?

### Property Access

Accessing nonexistent properties on objects

### Missing arguments

Not passing enough arguments to a function, will fill them with `undefined`

### Void functions

Functions that don't return anything - does the caller expect a value?
