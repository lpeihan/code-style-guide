# Code Style Guide

## Javascript

### Use brackets for all control constructs

use brackets for all control constructs like `if`, `else`, `try`, `for`, `while`

```javascript
// BAD
let bar = [];
if (isValid(foo)) bar.push('bar');

// BAD
if (isValid(foo))
  bar.push('bar');

// BAD
for (let i=0; i < AMOUNT; i++) bar.push(i);

// GOOD
if (isValid(foo)) {
  bar.push('bar');
}

// GOOD
for (let i = 0; i < AMOUNT; i++) {
  bar.push(i);
}
```

### Always add semicolon `;` at the end of statements

```javascript
// BAD
let foo = 'foo'
let bar = ['bar', 'baz']

// GOOD
let foo = 'foo';
let bar = ['bar', 'baz'];
```

### Prefer `const` / `let` vs `var`

```javascript
// BAD
function foo() {
    var bar = baz();
    // ...
    var bar = null; // work
}

// GOOD (to avoid implicit errors)
function foo() {
    let bar = baz();
    // ...
    let bar = baz(); // SyntaxError exception prevent re-declaration
}

// BAD
function foo() {
    baz(bar); // work, bar === undefined
    // ...
    var bar = 'bar'; 
}

// GOOD (to avoid implicit errors)
function foo() {
    baz(bar); // SyntaxError
    // ...
    let bar = 'bar'; 
}
```
