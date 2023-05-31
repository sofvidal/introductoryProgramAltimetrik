# Git rebase and squash | merge vs rebase

In Git, there are two main ways to integrate changes from one branch into another: the merge and the rebase. 
The easiest way to integrate the branches is the merge command. It performs a three-way merge between the two latest branch snapshots and the most recent common ancestor of the two, creating a new snapshot (and commit).
With the rebase command, you can take all the changes that were committed on one branch and replay them on a different branch. This operation works by going to the common ancestor of the two branches (the one you’re on and the one you’re rebasing onto), getting the diff introduced by each commit of the branch you’re on, saving those diffs to temporary files, resetting the current branch to the same commit as the branch you are rebasing onto, and finally applying each change in turn. After that, you can go ahead with a fast-forward merge.
rebase local changes before pushing to clean up your work, but never rebase anything that you’ve pushed somewhere.
To "squash" in Git means to combine multiple commits into one. You can do this at any point in time (by using Git's "Interactive Rebase" feature), though it is most often done when merging branches.
Squashing by starting an Interactive Rebase session:
An editor window will then open where you can choose how you want to manipulate the selected part of your commit history. If you mark one or more lines as "squash", they will be combined with the one above. After entering a commit message for the new, combining commit, the Interactive Rebase is completed - and the old commits have been squashed into one.
Squashing when merging branches:
All changes will be combined just as with a normal merge - but by using the --squash option, instead of a merge commit being automatically created, you're left with local changes in your working copy which you can then commit yourself. In the end, this allows you to avoid the automatic commit that typically happens as a result of a merge. It will appear as if the work for your feature had happened in just a single commit.

Sources: https://www.git-tower.com/learn/git/faq/git-squash, https://git-scm.com/docs/git-merge, https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging, https://git-scm.com/book/en/v2/Git-Branching-Rebasing 
