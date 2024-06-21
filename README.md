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



### merging command switch

