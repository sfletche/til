Writing this down, so I'll have to do less googling next time...

# Auto-completion
Follow instructions found [here](https://git-scm.com/book/en/v1/Git-Basics-Tips-and-Tricks#Auto-Completion)
(but use `~/.bash_profile` instead of `.bashrc` if you're on a Mac)

## Auto-complete with bash alias also in place
In `~/.bash_profile`, bind the auto-complete function to the alias...
```
alias g='git'
__git_complete g _git
```
(as shown [here](https://stackoverflow.com/a/24665529/379512))
