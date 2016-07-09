Today I learned why git cherry-pick is sometimes easier than git rebase.

I rebase often.  
Occasionally the `rebase` is particularly problematic (lots of merge conflicts) 
and my solution in such cases is to `cherry-pick` the individual commits onto master branch. 
I do this because nearly every time I do, the number of conflicts is considerably less.

My question was why this would be the case.  

After talking with some knowledgable co-workers, I finally understand why.

Say I have the following 
    
    A-B-C (master)
       \
        D-E (next)
           \
            F-G (other-next)
    
And then I do the following 

    git checkout next
    git rebase master
    git checkout master
    git merge next

I end up with the following

    A-B-C-D`-E` (master)
       \ \
        \ D`-E` (next)
         \
          D-E
             \
              F-G (other-next)

From here, I can either rebase or cherry-pick other-next onto master to get what I want...

**Rebasing example**

    git checkout other-next
    git rebase master 

produces 

    A-B-C-D`-E`-F`-G` (master)

**Cherry picking example**

    git checkout master
    git cherry-pick F G

produces the same result

    A-B-C-D`-E`-F`-G` (master)

but cherry-picking resulted in far fewer merge conflicts than rebasing.

After talking with the co-workers mentioned above I think I now understand why.

In the rebase example, when I rebase other-next onto master, git goes back to the common ancestor, B, 
and rebases all commits from that ancestor to the tip of other-next on top of master. 
(More details about git's rebase decision making can be found [here](http://stackoverflow.com/a/38253199/379512).)
The side effect of this is that if there were merge conflicts when rebasing next on top of master, 
then those same conflicts will re-emerge when rebasing those same commits again on top of master as part of the 
other-next rebase.  
Cherry picking on the other hand is limited to those commits on the other-next branch alone.
