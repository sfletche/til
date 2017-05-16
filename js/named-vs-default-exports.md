Today I learned some of the differences between *named* and *default* exports with ES6 modules.

**Named Exports** (multiple exports per script...curly braces on import
```
// module my-module.js
export { myFunction }; 
export const myConstant = Math.sqrt(2); 

// other file
import { myFunction, myConstant } from 'my-module';
```

**Default Exports** (only one export per script...no curly braces on import)
```
// module my-module.js
export default function myFunction() { ... }

// module my-other-module.js
export default const myConstant = Math.sqrt(2);

// other file
import myFunction from 'my-module';
import myConstant from 'other-module';
```

[More Notes](https://gist.github.com/sfletche/9b53668a2489a6885d0031062e769c7e)
