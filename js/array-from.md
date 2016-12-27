Today I learned about the ES6 Array method `Array.from`.

`Array.from` creates an array from an array-like or iterable object (like the `arguments` object).

Example:
```
function foo() {
  const args = Array.from(arguments);
  // [17, 23, 42]
}
foo(17, 23, 42);
```

A much more convenient strategy than the now old-fashioned `Array.prototype.slice.call(arguments)`

Of note: `Array.from` includes an optional 2nd parameter which allows the user to include a map function on each element of the array.

Example
```
function bar() {
  const args = Array.from(arguments, x => '' + x);
  // ['17', '23', '42']
}
bar(17, 23, 42);
```

UPDATE:  A still more convenient way for creating an array from an array-like object...

```
function foo() {
  const args = [...arguments];
  // [17, 23, 42]
}
foo(17, 23, 42);
```
