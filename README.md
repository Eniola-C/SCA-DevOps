# My First Project on Git
## Steps 
### First Step
Created a new directory to my master branch called Git
Added my new file called myfile.txt in the Git directory
Committed the changes
```
PS C:\Users\eniol\New folder> echo "This is a line in the master branch" >> myfile.txt
>> git add myfile.txt
>> git commit -m "Add a line in the master branch"
```
### Second Step
Created a new branch called godly
Made changes in godly
Merged it back to my master branch

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
Created a third branch called fear
Intentionally created a conflict
Resolved conflict
Committed the changes
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
Listed all branches
Deleted branch locally
Understood the difference between local and remote branches
Explored the concept of tracking branches
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
Made Changes
Committed the changes
Undid the last commit using git reset
```
PS C:\Users\eniol\New folder> git add .
PS C:\Users\eniol\New folder> git commit -m "updated"
[master 71ecf64] updated
 1 file changed, 0 insertions(+), 0 deletions(-)
PS C:\Users\eniol\New folder> git reset --soft HEAD^
```
### Step 6
Experimented and understood common git commands

