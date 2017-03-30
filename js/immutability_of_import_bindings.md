Today I learned that JS imports have immutable bindings, while imported objects are non-writable.

File #1

    export let obj = { foo: 23 };
    export let pi = 3.14
    
File #2

    import { obj, pi } from './file-1';

    obj.bar = 17; // works fine because imported objects are not immutable

    obj = { bar: 17 }; // fails with syntax error because import bindings are immutable

    obj.foo = 32; // fails because imported values are non-writable (silently fails without modification / error)

    pi = 3.1415; // fails with syntax error because primitive imports are immutable
