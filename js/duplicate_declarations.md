Turns out duplicate declarations act differently depending on whether they are variables or functions...

```
// Duplicate variable declarations are ignored

var a = 1; 
var a;
console.log(a); // 1

// Duplicate function declarations overwrite previous ones

function foo() {
  console.log(1);
}
function foo() { 
  console.log(2);
}
foo(); // 2
```
