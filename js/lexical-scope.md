For years I've thought lexical scope was equivalent to function level scope. 
I read it somewhere, took it as fact, and dismissed any evidenc to the contrary.
Today, while reading [Kyle Simpson's Scope & Closures](https://github.com/getify/You-Dont-Know-JS/blob/master/scope%20&%20closures/README.md#you-dont-know-js-scope--closures),
I finally understand that lexical scope and function level scope are not the same thing.

Block Scope
Most programming languages use Block level scope, which scopes a declaration to the block (think curly braces) in which it is declared.
For example
```
function foo(a) {
  if(a) {
    let b = 2;
  } else {
    let c = 3;
  }
  console.log(b); // 2
  console.log(c); // Reference Error
}
foo(true);
```
Function Scope
Rather than use Block scoping, Javascript's `var` is Function scoped.
This means that any `var` within a function is declared for the entire function (and not just the block in which it is declared).
For example
```
function foo(a) {
  if(a) {
    var b = 2;
  } else {
    var c = 3;
  }
  console.log(b); // 2
  console.log(c); // undefined
}
foo(true);
```
is roughly (not getting too far into the weeds here) equivalent to 
```
function foo(a) {
  var b;
  var c;
  if(a) {
    b = 2;
  } else {
    c = 3;
  }
  console.log(b); // 2
  console.log(c); // undefined
}
foo(true);
```

Lexical Scoping
Lexical scope is less about the where of a variable's scope and more about the when.
Languages that use lexical scope, are able to determine the scope of a declaration at compile-time (during lexical analysis).
This allows for performance enhancements through compiler optimizations (think V8 engine).
Lexical scoping can be contrasted with Dynamic scoping, in which the scope of a variable is not determined until execution time.
