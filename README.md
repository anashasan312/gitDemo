# gitDemo

<br>
author - MOHD ANAS HASAN

### -A / --all command 
Stages all changes, including new, modified, and deleted files.

``` PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git status 
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md
        new file:   text1.txt
```

### -u / --update flag
Stages changes to already tracked files only (modifications and deletions, but not new files).

```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md
        new file:   text1.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   text1.txt

PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git add -u
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md
        new file:   text1.txt
```



### . (dot) flag
Stages all changes in the current directory and subdirectories, but unlike -A, it does not stage deleted files.

```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md
        new file:   text1.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        text2.txt

PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git add .
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md
        new file:   text1.txt
        new file:   text2.txt

PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md
        new file:   text1.txt
        new file:   text2.txt

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    text2.txt

PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git add .
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md
        new file:   text1.txt
```

### -p / --patch flag
Allows you to interactively select chunks of changes within a file to stage.
```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git add -p
diff --git a/README.md b/README.md
index 8697722..827f6b2 100644
--- a/README.md
+++ b/README.md
@@ -48,3 +48,61 @@ Changes to be committed:
 ### . (dot) flag
 Stages all changes in the current directory and subdirectories, but unlike -A, it does not stage deleted files.

+```
+PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git status
+On branch main
+Your branch is up to date with 'origin/main'.
+
+Changes to be committed:
+  (use "git restore --staged <file>..." to unstage)
+        modified:   README.md
+        new file:   text1.txt
+
+Changes not staged for commit:
+  (use "git add <file>..." to update what will be committed)
+  (use "git restore <file>..." to discard changes in working directory)
+        modified:   README.md
+
+Untracked files:
+  (use "git add <file>..." to include in what will be committed)
+        text2.txt
+
+PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git add .
+PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git status
+On branch main
+Your branch is up to date with 'origin/main'.
+
+Changes to be committed:
+  (use "git restore --staged <file>..." to unstage)
+        modified:   README.md
+        new file:   text1.txt
+        new file:   text2.txt
+
+PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git status
+On branch main
+Your branch is up to date with 'origin/main'.
+
+Changes to be committed:
+  (use "git restore --staged <file>..." to unstage)
+        modified:   README.md
+        new file:   text1.txt
+        new file:   text2.txt
+
+Changes not staged for commit:
+  (use "git add/rm <file>..." to update what will be committed)
+  (use "git restore <file>..." to discard changes in working directory)
+        deleted:    text2.txt
+
+PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git add .
+PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git status
+On branch main
+Your branch is up to date with 'origin/main'.
+
+Changes to be committed:
+  (use "git restore --staged <file>..." to unstage)
+        modified:   README.md
+        new file:   text1.txt
+```
+
+### -p / --patch flag
+Allows you to interactively select chunks of changes within a file to stage.
(1/1) Stage this hunk [y,n,q,a,d,e,?]? y
```

### -i / --interactive:
Opens an interactive prompt where you can choose which changes to stage.

```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git add -i        
           staged     unstaged path
  1:      +182/-1      nothing README.md
  2:        +1/-0      nothing text1.txt

*** Commands ***
  1: status       2: update       3: revert       4: add untracked
  5: patch        6: diff         7: quit         8: help
What now> 

```

```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git commit -m " commit for add commands"
[main 9cb6e9b]  commit for add commands
 2 files changed, 183 insertions(+), 1 deletion(-)
 create mode 100644 text1.txt

```

### <pathspec>
Files to add content from. Fileglobs (e.g. *.c) can be given to add all matching files
```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git add text2.txt
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   text2.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git add -A
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md
        new file:   text2.txt

```

```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git commit -m "commit for add command"
[main 082a8a4] commit for add command
 2 files changed, 24 insertions(+), 2 deletions(-)
 create mode 100644 text2.txt

```
### git status

The git status command is used to display the state of the working directory and the staging area. It lets you see which changes have been staged, which haven't, and which files aren't being tracked by Git. 

```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md
        modified:   text1.txt

no changes added to commit (use "git add" and/or "git commit -a")

```

```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git commit -m " commit for status command"
[main 1195329]  commit for status command
 2 files changed, 64 insertions(+), 1 deletion(-)
 ```

 ### Compare Working Directory with Staging Area
 git diff

 ```
 PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git diff
diff --git a/README.md b/README.md
index 3da8c39..9ecee2a 100644
--- a/README.md
+++ b/README.md
@@ -245,4 +245,26 @@ PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git commit -m "commit for ad

 The git status command is used to display the state of the working directory and the staging area. It lets you see which changes have been staged, which haven't, and which files aren't being tracked by Git.

+```
+PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git status
+On branch main
+Your branch is ahead of 'origin/main' by 2 commits.
+  (use "git push" to publish your local commits)
+
+Changes not staged for commit:
+  (use "git add <file>..." to update what will be committed)
+  (use "git restore <file>..." to discard changes in working directory)
+        modified:   README.md
+        modified:   text1.txt
+
+no changes added to commit (use "git add" and/or "git commit -a")
+
+```
+
+```
+PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git commit -m " commit for status command"
+[main 1195329]  commit for status command
+ 2 files changed, 64 insertions(+), 1 deletion(-)
+ ```

+ ### Compare Working Directory with Staging Area
\ No newline at end of file
diff --git a/text1.txt b/text1.txt
index 97a764c..cf4cf9b 100644
--- a/text1.txt
+++ b/text1.txt
@@ -1,19 +1,4 @@
 for git flag -u

 for working status command
-```
-PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git status
-On branch main
-Your branch is ahead of 'origin/main' by 2 commits.
-  (use "git push" to publish your local commits)
-
-Changes not staged for commit:
-  (use "git add <file>..." to update what will be committed)
-  (use "git restore <file>..." to discard changes in working directory)
-        modified:   README.md
-        modified:   text1.txt
-
-no changes added to commit (use "git add" and/or "git commit -a")
```

### Compare Staging Area with Last Commit

git diff --cached
```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git diff --cached
diff --git a/README.md b/README.md
index 3da8c39..7ae7c2a 100644
--- a/README.md
+++ b/README.md
@@ -245,4 +245,84 @@ PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git commit -m "commit for ad
 
 The git status command is used to display the state of the working directory and the staging area. It lets you see which changes have been staged, which haven't, and which files aren't being tracked by Git. 
 
+```
+PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git status
+On branch main
+Your branch is ahead of 'origin/main' by 2 commits.
+  (use "git push" to publish your local commits)
+
+Changes not staged for commit:
+  (use "git add <file>..." to update what will be committed)
+  (use "git restore <file>..." to discard changes in working directory)
+        modified:   README.md
+        modified:   text1.txt
+
+no changes added to commit (use "git add" and/or "git commit -a")
+
+```
+
+```
+PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git commit -m " commit for status command"
+[main 1195329]  commit for status command
+ 2 files changed, 64 insertions(+), 1 deletion(-)
+ ```
+
+ ### Compare Working Directory with Staging Area
+ git diff
+
+ ```
+ PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git diff
+diff --git a/README.md b/README.md
```

### Compare Working Directory with Last Commit

```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git diff ba76506 6c50503
diff --git a/text1.txt b/text1.txt
index 5e13d8d..7bfc4be 100644
--- a/text1.txt
+++ b/text1.txt
@@ -5,3 +5,5 @@ for working status command
 for diff command

 commit1
+
```

### Compare Specific File or Directory

```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git diff README.md
diff --git a/README.md b/README.md
index 9c5f7d9..0a2c6c0 100644
--- a/README.md
+++ b/README.md
@@ -372,3 +372,15 @@ index 3da8c39..7ae7c2a 100644
 
 ### Compare Working Directory with Last Commit

 ```

```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git commit -m " commit for diff command"
[main 0db6024]  commit for diff command
 1 file changed, 28 insertions(+)
```

### commit 
### -m / --message
```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git commit -m " commit for showing message commit" 
[main f87ad01]  commit for showing message commit
 1 file changed, 1 insertion(+)
 create mode 100644 text3.txt
 ```
 ### --amend
```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git commit --amend -m " this i amend commit"
[main 383d37c]  this i amend commit
 Date: Fri Jun 21 02:38:18 2024 +0530
 1 file changed, 1 insertion(+)
 create mode 100644 text3.txt
```
### notes
### Adding a Note
```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git notes add -m "Your note message"
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git notes show
Your note message
```

### Appending to an Existing Note
```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git notes append -m "Additional note message"
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git notes show
Your note message

Additional note message
```

### Removing a Note
```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git notes remove
Removing note for object HEAD
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git notes show
error: no note found for object 8f17bc100b93f0769457ca9cc70e4e13229da02f.
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo>
```

### rm
This command removes the specified file from both the working directory and the staging area.
```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git rm text4.txt
rm 'text4.txt'
```

### Remove Cached File
This command removes the specified file from the staging area but leaves it in the working directory. This is useful when you want to stop tracking a file without deleting it from your working directory.
```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git rm --cached text4.txt
rm 'text4.txt'
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md
        deleted:    text4.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        text4.txt
```

<<<<<<< HEAD
<<<<<<< HEAD
### Create a New Branch
```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git branch
* main
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git checkout -b feature1
Switched to a new branch 'feature1'
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git checkout -b feature2
Switched to a new branch 'feature2'
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git checkout -b feature3
Switched to a new branch 'feature3'
```

### List All Branches
```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git branch
  feature1
  feature2
* feature3
  main
  ```

### Switching Branches
```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git branch   
  feature1
  feature2
* main
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git checkout feature1
Switched to branch 'feature1'
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git branch
* feature1
  feature2
  main
```
### delete 
```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git checkout -b feature3
Switched to a new branch 'feature3'
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git checkout main
Switched to branch 'main'
M       README.md
Your branch is up to date with 'origin/main'.
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git branch
  feature1
  feature2
  feature3
* main
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git branch -d feature3
Deleted branch feature3 (was ce7a59e).
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git branch
  feature1
  feature2
* main
```


=======


### cureently in second branch name feature2
>>>>>>> feature2

### merging command switch


### log command
The git log command is used to view the commit history in a Git repository. It is a powerful tool with many options to customize the output and make it easier to navigate and understand the commit history. Here are some important options and examples to help you make the most of git log.

```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git commit -m " commit for log command"
[main 73bf4b4]  commit for log command
 1 file changed, 4 insertions(+)
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git log
commit 73bf4b47710d86b7f2b052efcac2aa2dce446859 (HEAD -> main)
Author: anas <anashasan251309@gmail.com>
Date:   Fri Jun 21 11:23:43 2024 +0530

     commit for log command

commit 6ba2dedb59e3019b26423b15034599f6abfbeed2 (origin/main, origin/HEAD)
Merge: d2628d0 657a44b
Author: anas <anashasan251309@gmail.com>
Date:   Fri Jun 21 11:12:40 2024 +0530

     merging feature2 into main
```

### stash command with message


### deleting specific stash

### deleting stash 

```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git stash
Saved working directory and index state WIP on main: b5deff5  commiting log command
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git stash -m " stash with message"
Saved working directory and index state On main:  stash with message
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git stash list
stash@{0}: On main: stash with message
stash@{1}: WIP on main: b5deff5 commiting log command
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git stash apply
error: Your local changes to the following files would be overwritten by merge:
        README.md
Please commit your changes or stash them before you merge.
Aborting
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
    (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git stash list
stash@{0}: WIP on main: b5deff5 commiting log command
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git stash
Saved working directory and index state WIP on main: b5deff5  commiting log command
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git apply
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git stash apply
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git add README.md  
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git commit -m " commiting for stash adding and deleting"
[main 638f9a8]  commiting for stash adding and deleting
[main 638f9a8]  commiting for stash adding and deleting
 1 file changed, 4 insertions(+), 1 deletion(-)
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git stash apply
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Unmerged paths:
  (use "git restore --staged <file>..." to unstage)
  (use "git add <file>..." to mark resolution)
        both modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git stash list
stash@{0}: WIP on main: b5deff5 commiting log command
stash@{1}: WIP on main: b5deff5 commiting log command

PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git add README.md  
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git commit -m " troubleshooting remove in stash deleting"
[main 31cda2b]  troubleshooting remove in stash deleting
 1 file changed, 3 insertions(+)
 PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git stash
Saved working directory and index state WIP on main: 31cda2b  troubleshooting remove in stash deleting
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git stash list
stash@{0}: WIP on main: 31cda2b troubleshooting remove in stash deleting
stash@{1}: WIP on main: b5deff5 commiting log command
stash@{2}: WIP on main: b5deff5 commiting log command
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git stash push -m " deleting stash"
Saved working directory and index state On main:  deleting stash
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git stash list
stash@{0}: On main: deleting stash
stash@{1}: WIP on main: 31cda2b troubleshooting remove in stash deleting
stash@{2}: WIP on main: b5deff5 commiting log command
stash@{3}: WIP on main: b5deff5 commiting log command
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git stash pop 
error: Your local changes to the following files would be overwritten by merge:
        README.md
Please commit your changes or stash them before you merge.
Aborting
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git stash drop 2        
Dropped refs/stash@{2} (6b278d6820c1032b3240ff9e5de8977ede10bd0b)
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git stash drop 3
fatal: log for 'refs/stash' only has 3 entries
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git stash drop 0
Dropped refs/stash@{0} (11c502b1024032cf3cabe10a2bdd0e1ae7c502f0)
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git stash list
stash@{0}: WIP on main: 31cda2b troubleshooting remove in stash deleting
stash@{1}: WIP on main: b5deff5 commiting log command
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git stash clear
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git stash list

```

### tag command
The git tag command is used to create, list, delete, and verify tags in Git. Tags are useful for marking specific points in your repository's history, such as releases.


<<<<<<< HEAD
### git worktree command
The git worktree command allows you to manage multiple working directories attached to a single Git repository. This can be useful when you need to work on different branches simultaneously without having to switch back and forth within the same directory.

```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git worktree add ../w1 feature1
Preparing worktree (checking out 'feature1')
HEAD is now at 6e110ce  for switch
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git worktree list
C:/Users/mohda/OneDrive/Desktop/gitdemo/gitDemo  c066852 [main]
C:/Users/mohda/OneDrive/Desktop/gitdemo/w1       6e110ce [feature1]
C:/Users/mohda/OneDrive/Desktop/gitdemo/w2       657a44b [feature2]
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git worktree remove ../w2         
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git worktree list
C:/Users/mohda/OneDrive/Desktop/gitdemo/gitDemo  c066852 [main]
C:/Users/mohda/OneDrive/Desktop/gitdemo/w1       6e110ce [feature1]

PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git add README.md  
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git commit " commit for completing worktree"
error: pathspec ' commit for completing worktree' did not match any file(s) known to git
```

### fetch

### for fetch command
### for fetch second time


### for clear pull 
```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git add README.md  
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git commit -m " fetch"
[main 4dfac62]  fetch
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git pull origin main
From https://github.com/anashasan312/gitDemo
 * branch            main       -> FETCH_HEAD
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
Automatic merge failed; fix conflicts and then commit the result.
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git add README.md     
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git commit -m " fetch and pull"
[main 0c7a30f]  fetch and pull
```

### remote and submodule

### show
To display the details of the most recent commit:
```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git show
commit 0c7a30f929969d0018c880068f760b66ad94d574 (HEAD -> main, origin/main, origin/HEAD)
Merge: 4dfac62 d67c584
Author: anas <anashasan251309@gmail.com>
Date:   Fri Jun 21 15:08:45 2024 +0530

     fetch and pull

diff --cc README.md
index 6efd481,0869ee5..5907781
--- a/README.md
+++ b/README.md
```

### for pecific commit
```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git show d2628d0
commit d2628d04dfdd58567a402c18febd0e0550981392
Merge: cfd6242 6e110ce
Author: anas <anashasan251309@gmail.com>
Date:   Fri Jun 21 11:09:36 2024 +0530

     merging feature1 into main

diff --cc README.md
index 5f99399,3e49815..8e60f89
--- a/README.md
+++ b/README.md
@@@ -474,59 -474,4 +474,63 @@@ Untracked files
```
```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git add README.md   
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git commit -m " commit for show command"
[main 1fe6367]  commit for show command
 1 file changed, 54 insertions(+), 3 deletions(-)
 ```

### shortlog command
```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git shortlog -n
anas (37):
      commit for add commands
      commit for add command
      commit for status command
      for diff command for commit 1 andcommit 2
      for diff command for commit 1 and commit 2
      commit for diff command
      this i amend commit
      revise
      for notes
      for restoring process
      for removing command
      commit for branch
      just for flow
      just check
      just check
      commit for switching branches
      deleting branch
      just flow
      for switching
      for merging
      just check
      for switch
      commit for adding something in feature2
      for merging check
      merging feature1 into main
      merging feature2 into main
      commit for log command
      commiting log command
      commiting for stash adding and deleting
      troubleshooting remove in stash deleting
      stash
      commit stash command once
      commit for tag command
      commit for fetch
      fetch
      fetch and pull
      commit for show command

anashasan312 (5):
      Initial commit
      Update README.md
      Update README.md
      Update README.md
      Update README.md
```

```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git shortlog -e
anas <
anashasan251309@gmail.com> (37):
```
```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git shortlog -s
    37  anas
     5  anashasan312
```
### describe
The git describe command is used to create a human-readable name for a given commit based on the nearest tag in its history.
```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git describe
tag3-10-g3e4e654
```


### rebase command


### using feature3
```
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git checkout main
Already on 'main'
Your branch is up to date with 'origin/main'.
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git rebase feature3    
Successfully rebased and updated refs/heads/main.
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git checkout main
Already on 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)
PS C:\Users\mohda\OneDrive\Desktop\gitdemo\gitDemo> git push origin main
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
```

### testing rebse 
###
