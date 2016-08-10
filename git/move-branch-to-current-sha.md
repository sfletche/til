Today I learned (not for the first time) how to move a branch to the commit that I am currently on...

`git branch -f branch-name [ref]`

with the optional `ref` argument used to indicate a position in the git history other than the current position
(leaving off the `ref` arg moves `branch-name` to whatever commit you are currently on).
