See instructions [here](https://gist.github.com/joseluisq/1e96c54fa4e1e5647940)

OR, in case that link ^ ever breaks...

Add the following to your `~/.bash_profile`

```
parse_git_branch() {
  git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}

export PS1="\u@\h \W\[\033[32m\]\$(parse_git_branch)\[\033[00m\] $ "
```

