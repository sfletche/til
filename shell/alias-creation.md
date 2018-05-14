Haven't done this in so long, I forgot how...adding here to help me remember for next time...

Adding aliases to `~/.bashrc` (or `.bash_profile` for mac)

```
vi ~/.bash_profile
```
add the following
```
alias g='git'
```
save, quit, and reload your `bashrc` or `bash_profile` (bash run commands)
```
. ~/.bash_profile
```
Now you should be able to use the aliases e.g.
```
g pull
```

See [Git Alias](https://github.com/sfletche/til/blob/master/git/git-alias.md) for creating git aliases through `git config`
