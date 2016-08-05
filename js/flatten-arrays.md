Today I learned (for the gazillionth time) how to flatten an array of arrays.

For example, I have an array like so

`[[1],[2,3],[4]]`

and I want

`[1,2,3,4]`

And easy solution to this is to use the built in `Array.prototype.concat` function with `apply`...

`[].concat.apply([], [[1],[2,3],[4]])`

`apply` will parse the second argument, the array of arrays, and concatenate each array to the first argument `[]`,
resulting in a new array that is the concatenation of all of the nested arrays.
