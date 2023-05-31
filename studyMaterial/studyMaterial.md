# studyMaterial

What is git?
Git is a free and open source version control system. Version Control is the management of changes to documents, computer programs, large web sites, and other collections of information. 

Most common commands
git clone <repository url> // will download the latest version of a remote project and copy it to the selected location on the local machine
git clone <repository url> -b <branch name> // to clone a specific branch
git fetch // will get all the updates form the remote repository, including new branches
git checkout <branch name> // to switch the branch that you are currently working on
git checkout -b <branch name> // will create a new branch and switch to it
git init <repository name> // to start a new empty repository or to reinitialize an existing one in the project root, it will create a .git directory with its subdirectories. 
git commit -m "<commit message>" // create a new commit. A commit is like a local snapshot of the current state of the branch, to which you can always come back. 
git push // upload Git commits to a remote branch, like Github
git push –set-upstream <remote branch> <branch name> // for when the branch is not yet tracked, and only resides on the local machine
git pull // download changes from remote repo to your local machine, it'll merge any remote changes in the current branch, the opposite of push
git diff // see the unstaged changes on the current branch
git diff -staged // to see the staged changes
get diff <branch1> <branch2> // to compare two branches
git add // stage changed files
git add <file path> // stage individual files
git add . // all files
git branch // will list all the branches of the repository
git branch <new branch> // create a new branch (without checking it out)
git branch -d <branch name> // to delete a branch
git merge <branch name> // merges your branch with the parent branch
git status // returns information about your branch, current branch name, if it's up to date or not, number of commits that your branch is behind its remote branch, changes that are staged and to be committed, changes that are not staged for commit, untracked files. 

Git - Tagging
Git has the ability to tag specific points in a repository’s history as being important. Typically, people use this functionality to mark release points (v1.0, v2.0 and so on).
Git supports two types of tags: lightweight and annotated. 
A lightweight tag is very much like a branch that doesn’t change, it’s just a pointer to a specific commit. 
Annotated tags, however, are stored as full objects in the Git database. They’re checksummed; contain the tagger name, email, and date; have a tagging message; and can be signed and verified with GNU Privacy Guard. 

git tag // (with optional -l or -list) will list all the existing tags in Git, the list will be in alphabetical order
git tag <tagname> // creates a lightweight tag, it only requires the tag name
git tag -a <tagname> -m "my version 1.4" // creates an annotated tag, the -m specifies a tagging message, which is stored in the tag. you can also tag commits after you've moved past them, you'll only need to add the checksum (or part of it) at the end of the command 
git show <tagname> // to check tag date along with the commit that was tagged
git push origin <tagname> // will share to a remote server
git push origin -tags // will transfer all tags to the remote server that are not already there
git tag -d <tagname> // delete a tag on your local repository
git checkout <tagname> // for viewing the versions of files a tag is pointing to, it's advised to be careful since it puts your repository in "detached HEAD" state.

Git - Stash commands
Git stash is used when you want to record the current state of the working directory and the index, but want to go back to a clean working directory. The command saves your local modifications away and reverts the working directory to match the HEAD commit.
The modifications stashed away by this command can be listed with git stash list, inspected with git stash show, and restored (potentially on top of a different commit) with git stash apply. Calling git stash without any arguments is equivalent to git stash push. A stash is by default listed as "WIP on branchname …​", but you can give a more descriptive message on the command line when you create one.
The latest stash you created is stored in refs/stash; older stashes are found in the reflog of this reference and can be named using the usual reflog syntax (e.g. stash@{0} is the most recently created stash, stash@{1} is the one before it, stash@{2.hours.ago} is also possible). Stashes may also be referenced by specifying just the stash index (e.g. the integer n is equivalent to stash@{n}).

git stash list [<log-options>] // List the stash entries that you currently have. Each stash entry is listed with its name (e.g. stash@{0} is the latest entry, stash@{1} is the one before, etc.), the name of the branch that was current when the entry was made, and a short description of the commit the entry was based on.
git stash show [-u | --include-untracked | --only-untracked] [<diff-options>] [<stash>]  // Show the changes recorded in the stash entry as a diff between the stashed contents and the commit back when the stash entry was first created.
git stash drop [-q | --quiet] [<stash>] // Remove a single stash entry from the list of stash entries.
git stash pop [--index] [-q | --quiet] [<stash>] // Remove a single stashed state from the stash list and apply it on top of the current working tree state, i.e., do the inverse operation of git stash push. The working directory must match the index. Applying the state can fail with conflicts; in this case, it is not removed from the stash list. You need to resolve the conflicts by hand and call git stash drop manually afterwards.
git stash apply // Like pop, but do not remove the state from the stash list. Unlike pop, <stash> may be any commit that looks like a commit created by stash push or stash create.
git stash branch <branchname> [<stash>] // Creates and checks out a new branch named <branchname> starting from the commit at which the <stash> was originally created, applies the changes recorded in <stash> to the new working tree and index. If that succeeds, and <stash> is a reference of the form stash@{<revision>}, it then drops the <stash>.
git stash [push [-p | --patch] [-S | --staged] [-k | --[no-]keep-index] [-q | --quiet]
	     [-u | --include-untracked] [-a | --all] [(-m | --message) <message>]
	     [--pathspec-from-file=<file> [--pathspec-file-nul]]
	     [--] [<pathspec>...​]] // Save your local modifications to a new stash entry and roll them back to HEAD (in the working tree and in the index). The <message> part is optional and gives the description along with the stashed state.
git stash save [-p | --patch] [-S | --staged] [-k | --[no-]keep-index] [-q | --quiet]
	     [-u | --include-untracked] [-a | --all] [<message>] // This option is deprecated in favour of git stash push. It differs from "stash push" in that it cannot take pathspec. Instead, all non-option arguments are concatenated to form the stash message.
git stash clear // Remove all the stash entries. Note that those entries will then be subject to pruning, and may be impossible to recover (see Examples below for a possible strategy).
git stash create [<message>] // Create a stash entry (which is a regular commit object) and return its object name, without storing it anywhere in the ref namespace. This is intended to be useful for scripts. It is probably not the command you want to use; see "push" above.
git stash store [(-m | --message) <message>] [-q | --quiet] <commit> // Store a given stash created via git stash create (which is a dangling merge commit) in the stash ref, updating the stash reflog. This is intended to be useful for scripts. It is probably not the command you want to use; see "push" above.


Git Hooks
Git has a way to fire off custom scripts when certain important actions occur. There are two groups of these hooks: client-side and server-side. Client-side hooks are triggered by operations such as committing and merging, while server-side hooks run on network operations such as receiving pushed commits. 

Client-Side Hooks:
Committing-Workflow Hooks 
The pre-commit hook is run first, before you even type in a commit message. It’s used to inspect the snapshot that’s about to be committed, to see if you’ve forgotten something, to make sure tests run, or to examine whatever you need to inspect in the code. 
The prepare-commit-msg hook is run before the commit message editor is fired up but after the default message is created. It lets you edit the default message before the commit author sees it. This hook takes a few parameters: the path to the file that holds the commit message so far, the type of commit, and the commit SHA-1 if this is an amended commit.
The commit-msg hook takes one parameter, which again is the path to a temporary file that contains the commit message written by the developer. If this script exits non-zero, Git aborts the commit process, so you can use it to validate your project state or commit message before allowing a commit to go through. 
After the entire commit process is completed, the post-commit hook runs. It doesn’t take any parameters, but you can easily get the last commit by running git log -1 HEAD. Generally, this script is used for notification or something similar.

Email Workflow Hooks
The first hook that is run is applypatch-msg. It takes a single argument: the name of the temporary file that contains the proposed commit message. Git aborts the patch if this script exits non-zero. You can use this to make sure a commit message is properly formatted, or to normalize the message by having the script edit it in place.
The next hook to run when applying patches via git am is pre-applypatch. Somewhat confusingly, it is run after the patch is applied but before a commit is made, so you can use it to inspect the snapshot before making the commit. You can run tests or otherwise inspect the working tree with this script.
The last hook to run during a git am operation is post-applypatch, which runs after the commit is made. You can use it to notify a group or the author of the patch you pulled in that you’ve done so. 

Server-Side Hooks:
In addition to the client-side hooks, you can use a couple of important server-side hooks as a system administrator to enforce nearly any kind of policy for your project. These scripts run before and after pushes to the server. The pre hooks can exit non-zero at any time to reject the push as well as print an error message back to the client; you can set up a push policy that’s as complex as you wish.
The first script to run when handling a push from a client is pre-receive. It takes a list of references that are being pushed from stdin; if it exits non-zero, none of them are accepted. You can use this hook to do things like make sure none of the updated references are non-fast-forwards, or to do access control for all the refs and files they’re modifying with the push.
The update script is very similar to the pre-receive script, except that it’s run once for each branch the pusher is trying to update. If the pusher is trying to push to multiple branches, pre-receive runs only once, whereas update runs once per branch they’re pushing to. Instead of reading from stdin, this script takes three arguments: the name of the reference (branch), the SHA-1 that reference pointed to before the push, and the SHA-1 the user is trying to push. If the update script exits non-zero, only that reference is rejected; other references can still be updated.
The post-receive hook runs after the entire process is completed and can be used to update other services or notify users. It takes the same stdin data as the pre-receive hook. Examples include emailing a list, notifying a continuous integration server, or updating a ticket-tracking system – you can even parse the commit messages to see if any tickets need to be opened, modified, or closed. This script can’t stop the push process, but the client doesn’t disconnect until it has completed, so be careful if you try to do anything that may take a long time.


Sources: https://www.syncfusion.com/blogs/post/top-10-git-commands-every-developer-should-know.aspx, https://blog.testproject.io/2021/03/22/git-commands-every-sdet-should-know/, https://git-scm.com/book/en/v2/Git-Basics-Tagging, https://git-scm.com/docs/git-tag, https://git-scm.com/docs/git-stash, https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks. 
