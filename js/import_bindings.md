Today I learned that JS imports have immutable bindings, which differ between named and default exports/imports.

**Named exports** are actual bindings (kind of like pointers) to the exported thing (variable, function, etc). For example:

    // File #1
    let awesome = 23;
    function update() { awesome = 100; }
    export { awesome, update };

    // File #2
    import { awesome, update } from './file-1';
    console.log(awesome); // 23
    update();
    console.log(awesome); // 100
    
Even though `awesome` holds a primitive value (and primitive values are immutable), because the `awesome` export is a binding to the variable (not to the value), the second output is 100.

Take-away: named exports are bindings to the variable, not references to the value.

Standard **default exports** export a binding to the expression or value (not to the variable).

    // File #1
    let awesome = 23;
    function update() { awesome = 100; }
    export default { awesome, update };
    
    // File #2
    import stuff from './file-1';
    console.log(stuff.awesome); // 23
    stuff.update();
    console.log(stuff.awesome); // 23
    
Take-away: default exports are bindings to the value, not the variable.
