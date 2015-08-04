### Basic Git Operations

we have talked `git add` and `git commit` in chapter 1, now let's go a little deeper with some of the relevant commands.

#### git add

Use `git add` to add a snapshot of the files in current working directory to staging area. You can use `git add` in the following ways:

`git add .` will add all the files in working directory to staging area. include new/modified files
`git add path/to/file1 path/to/file2` you can also append a file list to add the specified files.
`git add -u` only add the modified files. This will exclude the new files. This is fairly useful when you have files modified and newly add but you only want to add the modified files.

#### git status

As we seen, `git status` gives you the current status of your working directory. for example, which files have been modified/new added/deleted

Simply use `git status`, you will see an completely output of the working directory status. But `git status -s` gives you a lean output like this(there are more cases, but we only talk these now):

```
 M path/to/file1
M  path/to/file2
MM path/to/file3
A  path/to/file4
?? path/to/file5
```

As you see, there are two comlumns at the beginning of each path. It may cause some confusion the first you see this. But it is falirly easy to understand.

The `M` at the second place, as you see the `M` before `path/to/file1`. It means that you did some modifications to `path/to/file1` since the last commit. And this modifications are not in `staging area`.

The `M` at the first place means that you modified `path/to/file2` and you have run `git add` and now it is in staging area, and the changes will go to git database in the next commit.

Sometimes you may see the double `M`, this tells that you modified `path/to/file3` after you do `git add`. Part of the changes are in staging area and others are in your working directory. And when you do `git commit` only the staged changes will be committed.

You will see `A` at the first place after you do `git add` to a newly added files which is not git-controlled before.

The `??` before `path/to/file5` tells you the file is a new file and you should run `git add` if you want to commit it at next time.


#### git diff

`git diff` is a very powerful tool to compare the differences of files among different states/branchs/commits. Now, We will use `git diff` to compare files among different states.

If you simply run `git diff`,  it will show all the difference between working directory and staging area. Following is the output of `git diff`. As you see, it shows the changes of file1 and file2 compare with `staging area`.
```
diff --git a/file1 b/file1
index 1e4ff02..a913e3b 100644
--- a/file1
+++ b/file1
@@ -1 +1,2 @@
 this is file 1
+something new
diff --git a/file2 b/file2
index a39a620..d46ecda 100644
--- a/file2
+++ b/file2
@@ -1 +1,2 @@
 this is file 2
+something new
```

You can also `diff` a specify file, for example `git diff paht/to/file1`. Git diff has other two main `options`.

`git diff --cached` or `git diff --staged`, they are the same. This will show differences between `staging area` and `git database`

`git diff HEAD` will compare the differences between `working directory` and `git database`


#### Hint: A better git diff output
![vimdiff](http://usevim.com/images/posts/vimdiff.png)
You can find how to make your `git diff` fancy here:
[Viewing all git diffs with vimdiff](http://stackoverflow.com/questions/3713765/viewing-all-git-diffs-with-vimdiff)
[Git diff with Vimdiff](https://technotales.wordpress.com/2009/05/17/git-diff-with-vimdiff/)