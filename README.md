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


