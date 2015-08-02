### States - The thing you must know before start

You may want to ask why should I do `git add` before doing `git commit`? What happened when I run `git commit`? In this chapter we will talk about this.

#### Three Git States

A file in Git has three states - modified, staged, committed. To help to have a better understand, let's imagine there are three places to 'store' the three states.

Obviously, the working directory is where to store the `modified` files. You modify files in working directory.

And there is a `.git` directory in the working directory, here is git database and the `committed` files are all there when you do `git commit`.

But where is the `staged` files? That's a main difference of Git and other VCS which only have two states. Because Git has a `staging area`. You can consider `staging area` as a mysterious place which stores a snapchat of the files when you do `git add`, since only staged files(to have a better understand, let's say changes) will be committed to Git database in the next commit, you can continue editing the same file while only commit the staged changes. Which means that you can commit part of your change to the repo. This gives you many flexibilities when working with git.

![states](https://git-scm.com/book/en/v2/book/01-introduction/images/areas.png)