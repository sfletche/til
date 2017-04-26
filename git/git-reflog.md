Ok. So I already knew abou this one, but I love it so much I feel compelled to document it here...

`git reflog` can be used to find any commit...even when that commit is not longer attached to an active branch!!!

Today I had a rebase go weird, and I was in a hurry, and I followed some instructions without thinking them through 
or paying much attention and only later realized I had lost a commit somehow.

`git reflog` to the rescue!

`git reflog | grep "<commit message>"` and viola, it showed me the original commit sha and a couple of rebase shas.

I could take a closer look at the commit with `git reset --hard <sha>`

And I could grab the sha and `git cherry-pick <sha>` back on branch.  

Thank you git!
