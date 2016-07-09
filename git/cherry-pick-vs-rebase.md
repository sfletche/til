Today I learned why git cherry-pick is sometimes less problematic than git rebase.

I rebase often.  Occasionally the `rebase` is particularly problematic (lots of merge conflicts) 
and my solution in such cases is to `cherry-pick` the individual commits onto master branch, which 
for some reason, produces far fewer conflicts than rebasing.

Until today, I didn't understand why this would be the case.  Isn't rebasing essentially the same as cherry-picking?

After talking with some more knowledgable co-workers, I finally understand why.

Say I have two feature branches, one branched from the other 
    
    A-B-C (master)
       \
        D-E (next)
           \
            F-G (other-next)
    
And then I merge the main feature branch onto master

    git checkout next
    git rebase master
    git checkout master
    git merge next

I then end up with the following

    A-B-C-D`-E` (master)
       \ \
        \ D`-E` (next)
         \
          D-E
             \
              F-G (other-next)

From here, I can either `rebase` or `cherry-pick` `other-next` onto `master` to get what I want...

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

but cherry-picking resulted in far fewer merge conflicts than rebasing.  Why would this be the case?

After talking with the co-workers mentioned above I I now understand why.

In the rebase example, when I rebase `other-next` onto `master`, git needs to first find the common ancestor, `B`, 
and then git rebases all commits from that ancestor to the tip of `other-next`. 
(More details about git's rebase decision making can be found [here](http://stackoverflow.com/a/38253199/379512).)
The side effect of this is that if there were merge conflicts when rebasing `next` onto `master`, 
then those same conflicts will re-emerge when rebasing `other-next` onto master, because those same commits 
are part of the trail from `other-next` to the common ancestor, `B`.  
Cherry picking on the other hand is limited to only those commits on the `other-next` branch, and so those conflicts 
from the `next` remnants are bypassed and the cherry picking results in fewer conflicts.  

viola.
