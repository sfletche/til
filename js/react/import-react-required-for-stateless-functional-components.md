The other day I started removing all the `import React` statements from my stateless functional components 
since I wasn't explicitly using `React` anywhere in the files...

Turns out, while this worked in my current build system, it does not work in all build systems and the current recommendation 
is to include the `import React` for all react components (be they stateless and functional or not).

The rationale is that JSX is compiled to `React.createElement(...)`.

While personally, I'd argue the `import React` is something the tanspiler should be handling under the hood, 
it seems the general community thinks it should be the responsibility of the developer.  
(see [this SO question](https://stackoverflow.com/questions/44141010/do-i-need-to-import-react-for-stateless-functional-components) for more)
