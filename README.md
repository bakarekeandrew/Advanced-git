# Git Exercises

## Advanced Git

### Part 1: Refining Git History

```bash
HP@ABakareke_25497 MINGW64 ~/Desktop/part1
$ git init
Initialized empty Git repository in C:/Users/HP/Desktop/part1/.git/

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git add test1.md && git commit -m "chore: Create initial file"
[master (root-commit) 56c9864] chore: Create initial file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git add test2.md && git commit -m "chore: Create another file"
[master 5b9e0c3] chore: Create another file     
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git add test3.md && git commit -m "chore: Create third and fourth files"
[master 1ce708c] chore: Create third and fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)     
 create mode 100644 test3.md

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test4.md

nothing added to commit but untracked files present (use "git add" to track)

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git status
On branch master
reword 5b9e0c3 chore: Create another file
chore: Create second file
Untracked files:
  (use "git add <file>..." to include in what will be committed)     
        test4.md

nothing added to commit but untracked files present (use "git add" to track)

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
squash 4fa6ca0 chore: Create second file
$ $ git add test4.md
bash: $: command not found

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ $ git commit --amend -m "chore: Create third and fourth files"     
bash: $: command not found

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git add test4.md

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git commit --amend -m "chore: Create third and fourth files"       
[master 2b576dd] chore: Create third and fourth files
 Date: Tue Mar 4 10:43:40 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git rebase -i HEAD~2
[detached HEAD 4fa6ca0] chore: Create second file
 Date: Tue Mar 4 10:43:24 2025 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/master.

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git rebase -i HEAD~2
error: cannot 'squash' without a previous commit
You can fix this with 'git rebase --edit-todo' and then run 'git rebase --continue'.
Or you can abort the rebase with 'git rebase --abort'.

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master|REBASE)
$ git rebase -i HEAD~1
fatal: It seems that there is already a rebase-merge directory, and  
I wonder if you are in the middle of another rebase.  If that is the 
case, please try
        git rebase (--continue | --abort | --skip)
If that is not the case, please
        rm -fr ".git/rebase-merge"
and run me again.  I am stopping in case you still have something    
valuable there.


HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master|REBASE)
$ git rebase --skip
error: cannot 'squash' without a previous commit
error: please fix this using 'git rebase --edit-todo'.

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master|REBASE)
$ git rebase --abort
pick 4fa6ca0 chore: Create second file

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git rebase -i HEAD~1
Successfully rebased and updated refs/heads/master.

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git add test3.md

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git commit -m "Create third file"
On branch master
nothing to commit, working tree clean

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git commit -m "Create third file"
On branch master
nothing to commit, working tree clean

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git add test4.md

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git commit -m "Create fourth file"
On branch master
pick 687f88d chore: Create second file
nothing to commit, working tree clean

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git rebase -i HEAD~2
[detached HEAD 687f88d] chore: Create second file
 Date: Tue Mar 4 10:43:24 2025 +0200
 3 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/master.

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ echo "Unwanted content" > unwanted.txt

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git add unwanted.txt
warning: in the working copy of 'unwanted.txt', LF will be replaced by CRLF the next time Git touches it

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git commit -m "Unwanted commit"
[master cedf51b] Unwanted commit
 1 file changed, 1 insertion(+)
 create mode 100644 unwanted.txt

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git rebase -i HEAD~2
Successfully rebased and updated refs/heads/master.

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git rebase -i HEAD~3
fatal: invalid upstream 'HEAD~3'

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git checkout -b ft/branch
Switched to a new branch 'ft/branch'

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (ft/branch)
$ echo "Test 5 content" > test5.md

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (ft/branch)
$ git add test5.md
warning: in the working copy of 'test5.md', LF will be replaced by CRLF the next time Git touches it

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (ft/branch)
$ git commit -m "Implemented test 5"
[ft/branch aa64d05] Implemented test 5
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (ft/branch)
$ git checkout master
Switched to branch 'master'

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git cherry-pick ft/branch
[master 22c8ac7] Implemented test 5
 Date: Tue Mar 4 11:02:03 2025 +0200
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git log --graph --oneline --all
* 22c8ac7 (HEAD -> master) Implemented test 5
| * aa64d05 (ft/branch) Implemented test 5
|/
* 687f88d chore: Create second file
* 56c9864 chore: Create initial file

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git reflog
22c8ac7 (HEAD -> master) HEAD@{0}: cherry-pick: Implemented test 5
687f88d HEAD@{1}: checkout: moving from ft/branch to master
aa64d05 (ft/branch) HEAD@{2}: commit: Implemented test 5
687f88d HEAD@{3}: checkout: moving from master to ft/branch
687f88d HEAD@{4}: rebase (finish): returning to refs/heads/master    
687f88d HEAD@{5}: rebase (start): checkout HEAD~2
cedf51b HEAD@{6}: commit: Unwanted commit
687f88d HEAD@{7}: rebase (finish): returning to refs/heads/master    
687f88d HEAD@{8}: rebase (squash): chore: Create second file
4fa6ca0 HEAD@{9}: rebase (start): checkout HEAD~2
9b5635b HEAD@{10}: rebase (finish): returning to refs/heads/master   
9b5635b HEAD@{11}: rebase (start): checkout HEAD~1
9b5635b HEAD@{12}: rebase (abort): returning to refs/heads/master    
56c9864 HEAD@{13}: rebase (start): checkout HEAD~2
9b5635b HEAD@{14}: rebase (finish): returning to refs/heads/master   
9b5635b HEAD@{15}: rebase (pick): chore: Create third and fourth files
4fa6ca0 HEAD@{16}: rebase (reword): chore: Create second file        
5b9e0c3 HEAD@{17}: rebase: fast-forward
56c9864 HEAD@{18}: rebase (start): checkout HEAD~2
2b576dd HEAD@{19}: commit (amend): chore: Create third and fourth files
1ce708c HEAD@{20}: commit: chore: Create third and fourth files      
5b9e0c3 HEAD@{21}: commit: chore: Create another file
56c9864 HEAD@{22}: commit (initial): chore: Create initial file      

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git reset --hard
HEAD is now at 22c8ac7 Implemented test 5

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git remote add origin https://github.com/bakarekeandrew/Advanced-git.git

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git push -u origin master
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 4 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (8/8), 691 bytes | 22.00 KiB/s, done.
Total 8 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)        
remote: Resolving deltas: 100% (1/1), done.
To https://github.com/bakarekeandrew/Advanced-git.git
 * [new branch]      master -> master
branch 'master' set up to track 'origin/master'.

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$
```

### Part2: Branching Basics 

```bash

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git checkout -b ft/new-feature
Switched to a new branch 'ft/new-feature'

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (ft/new-feature)
$ echo "Core functionality for the new feature" > feature.txt        

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (ft/new-feature)
$ git add feature.txt
warning: in the working copy of 'feature.txt', LF will be replaced by CRLF the next time Git touches it CRLF the next time Git touches it

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (ft/new-feature)
$ git commit -m  "Implement core functionality for new feature"       1 file changed, 1 insertion(+)
[ft/new-feature 769aee1] Implement core functionality for new feature 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (ft/new-feature)
$ git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ echo "Welcome to the project!" > readme.txt

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)                  CRLF the next time Git touches it
$ git add readme.txt
warning: in the working copy of 'readme.txt', LF will be replaced by 
CRLF the next time Git touches it

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git commit -m "Updated project readme"
[master d3922e2] Updated project readme
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git push origin master
To https://github.com/bakarekeandrew/Advanced-git.git
 ! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'https://github.com/bakarekeandrew/Advanced-git.git'
hint: Updates were rejected because the remote contains work that you do not
hint: have locally. This is usually caused by another repository pushing to
hint: the same ref. If you want to integrate the remote changes, use
hint: 'git pull' before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git push origin ft/new-feature
Enumerating objects: 11, done.
Merge branch 'master' of https://github.com/bakarekeandrew/Advanced-gCounting objects: 100% (11/11), done.
Delta compression using up to 4 threads
Compressing objects: 100% (7/7), done.
Writing objects: 100% (11/11), 968 bytes | 22.00 KiB/s, done.        
Total 11 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)       
remote: Resolving deltas: 100% (2/2), done.
remote:
remote: Create a pull request for 'ft/new-feature' on GitHub by visiting:
remote:      https://github.com/bakarekeandrew/Advanced-git/pull/new/ft/new-feature
remote:
To https://github.com/bakarekeandrew/Advanced-git.git
 * [new branch]      ft/new-feature -> ft/new-feature


HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git pull origin master
remote: Enumerating objects: 7, done.
remote: Counting objects: 100% (7/7), done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 6 (delta 3), reused 0 (delta 0), pack-reused 0 (from 0 
Unpacking objects: 100% (6/6), 3.79 KiB | 53.00 KiB/s, done.
From https://github.com/bakarekeandrew/Advanced-git
 * branch            master     -> FETCH_HEAD
   22c8ac7..797b269  master     -> origin/master
Merge made by the 'ort' strategy.
 README.md | 246 ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 1 file changed, 246 insertions(+)
 create mode 100644 README.md

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git push origin --delete ft/new-feature
To https://github.com/bakarekeandrew/Advanced-git.git
 - [deleted]         ft/new-feature

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git log -- oneline

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git checkout -b ft/new-branch-from-commit
Switched to a new branch 'ft/new-branch-from-commit'

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (ft/new-branch-from-commit)
$ git checkout master
Switched to branch 'master'
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git merge ft/new-branch-from-commit
Already up to date.

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git add .

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git commit -m "Merged ft/new-branch-from-commit into master"
On branch master
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git checkout ft/new-branch-from-commit
Switched to branch 'ft/new-branch-from-commit'

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (ft/new-branch-from-commit)
$ git rebase master
Current branch ft/new-branch-from-commit is up to date.

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (ft/new-branch-from-commit)
$ git branch -m ft/new-branch-from-commit ft/improved-branch-name

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (ft/improved-branch-name)
$ git log --oneline
14e2ce0 (HEAD -> ft/improved-branch-name, master) Merge branch 'master' of https://github.com/bakarekeandrew/Advanced-git I want to pull the latest changes
d3922e2 Updated project readme
797b269 (origin/master) Update README.md
6e1ae9f Create README.md
22c8ac7 Implemented test 5
687f88d chore: Create second file
56c9864 chore: Create initial file

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (ft/improved-branch-name)
$ git checkout master
Switched to branch 'master'
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$
```

## Part 3: Advanced Workflows


### 1. Stashing Changes
```bash
HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ echo "Temporary changes" > temp.txt

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git stash
Saved working directory and index state WIP on master: 14e2ce0 Merge 
branch 'master' of https://github.com/bakarekeandrew/Advanced-git I want to pull the latest changes
```
### 2. Retrieving Stashed Changes

```bash
HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git stash pop
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)     
        temp.txt

no changes added to commit (use "git add" and/or "git commit -a")    
Dropped refs/stash@{0} (a406a87f819e0762868728dd1b4725fcd8ff745f)

```
### 3.Branch Merging Conflicts
```bash
HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ echo "Temporary changes" > temp.txt

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git stash
Saved working directory and index state WIP on master: 14e2ce0 Merge 
branch 'master' of https://github.com/bakarekeandrew/Advanced-git I want to pull the latest changes

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git stash pop
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)     
        temp.txt

no changes added to commit (use "git add" and/or "git commit -a")    
Dropped refs/stash@{0} (a406a87f819e0762868728dd1b4725fcd8ff745f)

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git checkout -b ft/conflict-branch 
Switched to a new branch 'ft/conflict-branch'

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (ft/conflict-branch)
$ echo "Changes in conflict branch" > conflict.txt

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (ft/conflict-branch)      
$ git add conflict.txt
warning: in the working copy of 'conflict.txt', LF will be replaced by CRLF the next time Git touches it

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (ft/conflict-branch)      
$ git commit -m "Changes in conflict branch"
[ft/conflict-branch 36875d0] Changes in conflict branch
 1 file changed, 1 insertion(+)
 create mode 100644 conflict.txt

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (ft/conflict-branch)      
$ git checkout master
M       README.md
Switched to branch 'master'
Your branch is up to date with 'origin/master'.

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ echo "Changes in master branch" > conflict.txt

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git add conflict.txt
warning: in the working copy of 'conflict.txt', LF will be replaced by CRLF the next time Git touches it

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git commit -m "Changes in master branch"
[master 88c762f] Changes in master branch
 1 file changed, 1 insertion(+)
 create mode 100644 conflict.txt

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git merge ft/conflict-branch
Auto-merging conflict.txt
CONFLICT (add/add): Merge conflict in conflict.txt
Automatic merge failed; fix conflicts and then commit the result.    

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master|MERGING)
$ nano conflict.txt

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master|MERGING)
$ git add conflict.txt

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master|MERGING)
$ git commit -m "Resolved merge conflict in conflict.txt"
[master 9823f91] Resolved merge conflict in conflict.txt

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$
```
### 4.Resolving Merge Conflicts with a Merge Tool

```bash
HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git mergetool

This message is displayed because 'merge.tool' is not configured.    
See 'git mergetool --tool-help' or 'git help config' for more details.
'git mergetool' will now attempt to use one of the following tools:  
opendiff kdiff3 tkdiff xxdiff meld tortoisemerge gvimdiff diffuse diffmerge ecmerge p4merge araxis bc codecompare smerge emerge vimdiff nvimdiff
No files need merging

```
### 5.Understanding Detached HEAD State
```bash
HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git log --oneline
9823f91 (HEAD -> master) Resolved merge conflict in conflict.txt     
88c762f Changes in master branch
36875d0 (ft/conflict-branch) Changes in conflict branch
14e2ce0 (origin/master, ft/improved-branch-name) Merge branch 'master' of https://github.com/bakarekeandrew/Advanced-git I want to pull the latest changes
d3922e2 Updated project readme
797b269 Update README.md
6e1ae9f Create README.md
22c8ac7 Implemented test 5
687f88d chore: Create second file
56c9864 chore: Create initial file

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git checkout 
M       README.md
Your branch is ahead of 'origin/master' by 3 commits.
  (use "git push" to publish your local commits)     

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git checkout master
M       README.md
Already on 'master'
Your branch is ahead of 'origin/master' by 3 commits.
  (use "git push" to publish your local commits)

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$
```

### 6.Ignoring Files/Directories:
```bash
HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ echo "/tmp" > .gitignore

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git add .gitignore
warning: in the working copy of '.gitignore', LF will be replaced by 
CRLF the next time Git touches it

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git commit -m "Added .gitignore to exclude /tmp"
[master a7cfa7a] Added .gitignore to exclude /tmp
 1 file changed, 1 insertion(+)
 create mode 100644 .gitignore

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ 
```
### 7.Working with Tags
```bash
HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git tag v1.0

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git push origin v1.0
Enumerating objects: 31, done.
Counting objects: 100% (31/31), done.  
Delta compression using up to 4 threads
Compressing objects: 100% (24/24), done.
Writing objects: 100% (31/31), 5.84 KiB | 122.00 KiB/s, done.  
Total 31 (delta 11), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (11/11), done.
To https://github.com/bakarekeandrew/Advanced-git.git
 * [new tag]         v1.0 -> v1.0

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$
```
### 8.Listing and Deleting Tags
```
HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git tag
v1.0

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git tag -d v1.0
Deleted tag 'v1.0' (was a7cfa7a)

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git push origin --delete v1.0
To https://github.com/bakarekeandrew/Advanced-git.git
 - [deleted]         v1.0

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$
```
### 9. Pushing Local Work to Remote Repositories

```
HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git push origin master
Enumerating objects: 16, done.
Counting objects: 100% (16/16), done.  
Delta compression using up to 4 threads
Compressing objects: 100% (11/11), done.
Writing objects: 100% (14/14), 1.28 KiB | 31.00 KiB/s, done.  
Total 14 (delta 6), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (6/6), completed with 1 local object. 
To https://github.com/bakarekeandrew/Advanced-git.git
   500a2e0..2d49fe6  master -> master

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git push origin ft/conflict-branch
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
remote: 
remote: Create a pull request for 'ft/conflict-branch' on GitHub by visiting:
remote:      https://github.com/bakarekeandrew/Advanced-git/pull/new/ft/conflict-branch
remote:
To https://github.com/bakarekeandrew/Advanced-git.git
 * [new branch]      ft/conflict-branch -> ft/conflict-branch        

HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)

```
### 10.Pulling Changes from Remote Repositories
```bash
HP@ABakareke_25497 MINGW64 ~/Desktop/part1 (master)
$ git pull origin master
From https://github.com/bakarekeandrew/Advanced-git
 * branch            master     -> FETCH_HEAD      
Already up to date.                                                  /Advanced-git.git'
                                                     
```

