Today I learned the `this` binding order of precedence and a vocabulary to go with it (thank you [Kyle Simpson](https://github.com/getify/You-Dont-Know-JS/blob/1efb94d9a98d873461e3416de625e398ddce31fd/this%20%26%20object%20prototypes/ch2.md#determining-this)!)

Starting from the highest precedence and working down...

1. The **new binding** in which `this` is the newly constructed object.

  ```var foo = new bar()```

2. **Explicit binding** (function is called with `call` or `apply`) or **hard binding** (with `bind`) in which `this` is the specified object.

  ```var foo = bar.call(obj)```
  
3. **Implicit binding** (function is called with a context) in which `this` is the context object.

  ```var foo = obj.bar()```
  
4. **Default binding** (function is called with no context) in which `this` is either the `global` object or `undefined` in `strict` mode.

  ```var foo = bar()```
  
