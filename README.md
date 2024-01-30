# My First Project on Git
## Steps 
### Step 1
- Created a new directory to my master branch called Git
- Added my new file called myfile.txt in the Git directory
- Committed the changes
```
PS C:\Users\eniol\New folder> echo "This is a line in the master branch" >> myfile.txt
>> git add myfile.txt
>> git commit -m "Add a line in the master branch"
```
### Step 2
- Created a new branch called godly
- Made changes in godly
- Merged it back to my master branch

```
PS C:\Users\eniol\New folder> git branch godly
PS C:\Users\eniol\New folder> git checkout godly
Switched to branch 'godly'
PS C:\Users\eniol\New folder> git add .
PS C:\Users\eniol\New folder> git commit -m "Updated"
[godly 6ca5040] Updated
 1 file changed, 1 insertion(+), 1 deletion(-)
PS C:\Users\eniol\New folder> git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.
PS C:\Users\eniol\New folder> git merge godly
Updating 016d4fe..6ca5040
Fast-forward

```
### Step 3
- Created a third branch called fear
- Intentionally created a conflict
- Resolved conflict
- Committed the changes
```
PS C:\Users\eniol\New folder> git branch fear
PS C:\Users\eniol\New folder> echo "This is a line in the master branch" >> myfile.txt
>> git add myfile.txt
>> git commit -m "Add a line in the master branch"
[master 28b4ac0] Add a line in the master branch
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 myfile.txt
PS C:\Users\eniol\New folder> git checkout fear
>> echo "This is a conflicting line in the fear branch" >> myfile.txt
>> git add myfile.txt
>> git commit -m "Add a conflicting line in the fear branch"
Switched to branch 'fear'
Your branch is ahead of 'origin/master' by 3 commits.
  (use "git push" to publish your local commits)
warning: Cannot merge binary files: myfile.txt (HEAD vs. fear)
Auto-merging myfile.txt
CONFLICT (add/add): Merge conflict in myfile.txt
Automatic merge failed; fix conflicts and then commit the result.
PS C:\Users\eniol\New folder> git add myfile.txt
PS C:\Users\eniol\New folder> git commit -m "Merged conflict"
[master 124fe76] Merged conflict
```
### Step 4
- Listed all branches
- Deleted branch locally
- Understood the difference between local and remote branches
- Explored the concept of tracking branches
```
PS C:\Users\eniol\New folder> git branch
  fear
  godly
* master

PS C:\Users\eniol\New folder> git branch -d fear
Deleted branch fear (was a4ee99d).

PS C:\Users\eniol\New folder> git branch -vv
  godly  6ca5040 Updated
* master 124fe76 [origin/master: ahead 5] Merged conflict
```
### Step 5
- Made Changes
- Committed the changes
- Undid the last commit using git reset
```
PS C:\Users\eniol\New folder> git add .
PS C:\Users\eniol\New folder> git commit -m "updated"
[master 71ecf64] updated
 1 file changed, 0 insertions(+), 0 deletions(-)
PS C:\Users\eniol\New folder> git reset --soft HEAD^
```
### Step 6
- Experimented and understood common git commands

_Git Status:_
The git status command in Git is used to display the current state of your working directory and staging area (index). It provides information about which files have been modified, which files are staged for the next commit, and which files are untracked.
```
PS C:\Users\eniol\New folder> git status
On branch master
Your branch is ahead of 'origin/master' by 5 commits.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   myfile.txt
PS C:\Users\eniol\New folder> git commit -m "uncommitted"
[master a77eece] uncommitted
 1 file changed, 0 insertions(+), 0 deletions(-)
PS C:\Users\eniol\New folder> git status
On branch master
Your branch is ahead of 'origin/master' by 6 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```
_Git Log:_

The git log command in Git is used to display a chronological list of commits in a repository. It shows information about each commit, including the commit hash, author, date, and commit message.
```
 git log
commit a77eecea32ca1387a2f387d313025ce13ba068d2 (HEAD -> master)
```
_Git Remote:_

The git remote command in Git is used to manage remote repositories. It allows you to view, add, or remove remote repositories associated with your local Git repository.
```
PS C:\Users\eniol\New folder> git remote
origin
```

_Git Diff:_

The git diff command in Git is used to display the changes between two states of your Git repository.
```
PS C:\Users\eniol\New folder> git diff
PS C:\Users\eniol\New folder> git diff master godly
diff --git a/index.html b/index.html
index e7d19b9..d0eeacc 100644
--- a/index.html
+++ b/index.html
@@ -6,6 +6,6 @@
     <title>Working with Git</title>
 </head>
 <body>
-    <h1>Who do you know?</h1>
+    <h1>Hi, I am Eniola Kolawole</h1>
 </body>
 </html>
```
_Git Stash:_

The git stash command in Git is used to save changes that have not been committed yet, allowing you to switch to a different branch, apply changes, or perform other operations without committing your current work.
```
PS C:\Users\eniol\New folder> git stash
No local changes to save
```
_Git Rebase:_

git rebase is a Git command used to rewrite commit history by moving, combining, or modifying existing commits. It allows you to integrate changes from one branch onto another, creating a more linear and cleaner history compared to traditional merging.
```
PS C:\Users\eniol\New folder> git rebase
warning: Cannot merge binary files: myfile.txt (HEAD vs. a4ee99d (Add a conflicting line in the fear branch))
Auto-merging myfile.txt
CONFLICT (add/add): Merge conflict in myfile.txt
error: could not apply a4ee99d... Add a conflicting line in the fear branch
hint: Resolve all conflicts manually, mark them as resolved with
hint: "git add/rm <conflicted_files>", then run "git rebase --continue".
hint: You can instead skip this commit: run "git rebase --skip".
hint: To abort and get back to the state before "git rebase", run "git rebase --abort".
Could not apply a4ee99d... Add a conflicting line in the fear branch
PS C:\Users\eniol\New folder> git rebase
fatal: It seems that there is already a rebase-merge directory, and
I wonder if you are in the middle of another rebase.  If that is the
case, please try
        git rebase (--continue | --abort | --skip)
If that is not the case, please
        rm -fr ".git/rebase-merge"
and run me again.  I am stopping in case you still have something
valuable there.

PS C:\Users\eniol\New folder> git rebase --continue
[detached HEAD c87fca2] Add a conflicting line in the fear branch
 1 file changed, 0 insertions(+), 0 deletions(-)
Successfully rebased and updated refs/heads/master.
```

