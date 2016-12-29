For years I've thought lexical scope was equivalent to function level scope. 
I read it somewhere, took it as fact, and dismissed any evidenc to the contrary.
Today, while reading [Kyle Simpson's Scope & Closures](https://github.com/getify/You-Dont-Know-JS/blob/master/scope%20&%20closures/README.md#you-dont-know-js-scope--closures), I learned that I was wrong.

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

Rather than use Block scoping, Javascript's `var` uses Function scope.
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

Lexical Scope

Lexical scope is less about the *where* of a variable's scope and more about the *when*.
Languages that use lexical scope, are able to determine the scope of a declaration **at compile-time** (during lexical analysis).
This enables performance enhancements through compiler optimizations (think V8 engine).

Dynamic Scope

Lexical scoping can be contrasted with Dynamic scoping, in which the scope of a variable is not determined until execution time.  

There are two features of JS that allow for dynamic scoping, `with` and `eval`.
Many of us have been told (without fully appreciating why) to not use `eval` or `with` in our JS code.
Turns out, because these features utilize dynamic scoping, the JS compiler is unable to lexically scope *any* of your code,
which means it eliminates any available compile time optimizations *for your entire program*.  
