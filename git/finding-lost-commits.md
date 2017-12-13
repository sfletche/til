I recently force pushed over a co-workers commit (yeah, i know `--force-with-lease` may have helped prevent this, but things happen...)

I knew the intent of the commit and I knew the ticket number was in the commit message.  With that information all I had to do was 
* search the `reflog`
* identify which commit was lost
* `cherry-pick` the commit back onto the branch
* push it up
* wipe sweat off brow and feel relieved that git is so friggin awesome

Search the `reflog` while grep'ing for content in the commit message
```
git reflog --all --grep='Ticket-409'
```
Use `git show` to explore the contents of likely commits
```
git show <sha>
```
Or list the files that were changed
```
git show --name-only <sha>
```
Or list the content changes in a specific file in that commit
```
git show <sha>:src/my-file.js
```
