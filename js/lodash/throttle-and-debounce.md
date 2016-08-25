Today I learned about the lodash functions `_.throttle` and `_.debounce`. 
Both can be used to limit the number of function calls resulting in execution.

Imagine a function that is called whenever the mouse or scroll position is changed, 
such events can cause a handler to be called more often than actually necessary.  

`_.throttle` ensures a function is only executed at most once per every some number of milliseconds.
Example: user scrolls constantly while function is only executed every given number of milliseconds

`_.debounce` delays a subsequent function execution until a given number of milliseconds has passed since the previous execution.
Example: user scrolls a little, while a subsequent function execution is delayed until given number of milliseconds has passed.  

Great explanation and examples provided by Chris Coyier on [CSS-Tricks](https://css-tricks.com/the-difference-between-throttling-and-debouncing/)
