Helped a co-worker with a problem they were having in which they were unable to push a feature branch...

Turns out they had accidentally set `push.default` to `matching` which meant when they tried to push their feature branch, 
**they were actually pushing all branches**, which was resulting in an error because another branch was behind origin.

Get `push.default` setting...
```
git config push.default
```

Set `push.default`...
```
git config push.default <setting>
```

From the docs...
* `matching` - push all branches having the same name on both ends
* `current` - push the current branch to update a branch with the same name on the receiving end
* `nothing` - do not push anything (error out) unless a refspec is explicitly given
