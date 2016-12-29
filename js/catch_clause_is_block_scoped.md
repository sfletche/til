Today I learned where JS got it's block scoping from...

Turns out in ES3 the `catch` block was defined as having block scope.
```
try {
  throw 2;
} catch(e) {
  console.log(e); // 2
}
console.log(e); // ReferenceError
```

And this block scope spec in the `catch` clause is what enables `let` to be transpiled...
```
{
 let a = 2;
 console.log( a ); // 2
}
console.log( a ); // ReferenceError
```
can be transpiled to (same thing we saw above)
```
try{
  throw 2
} catch(e) {
 console.log(e); // 2
}
console.log(e); // ReferenceError
```
