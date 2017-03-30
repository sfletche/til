Today I learned that JS imports have immutable bindings, and imported objects are non-writable.

File #1

    export const obj = { foo: 23 };
    export let pi = 3.14
    
File #2

    import { obj, pi } from './file-1';

    obj.bar = 17; // works fine because imported values are not immutable

    obj = { bar: 17 }; // fails with syntax erro because import bindings are immutable (and not because obj is originally declared as a const)

    obj.foo = 32; // fails because imported values are non-writable (should fail without error)

    pi = 3.1415; // fails with syntax error because primitive imports are immutable
