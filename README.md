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

### -v / --verbose flag
Shows files as they are being added to the staging area.

