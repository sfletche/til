Today I learned that Git allows alias creation through `git config`...

Just type something similar to any of the following
```
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status
```
and you now only need to type
```
git co <branch-name>
```
to checkout a branch (for example)

See [Creating Alias](https://github.com/sfletche/til/blob/master/shell/alias-creation.md) for creating other bash aliases.
