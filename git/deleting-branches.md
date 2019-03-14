Just writing this down hoping I remember for next time...

// Delete remote branch
git push -d origin <branch-name>

// Delete local branch
git branch -d <branch-name>
(or -D for unmerged branches)

// Delete all merged branches (clean up all branches pulled locally, won't delete anything that isn't fully merged to master)
git br -l | grep -v master | xargs git br -d
