# Lecture1 - CS50's Web Programming with Python and JavaScript

## git branching

1. Intially, we start a commit with initial changes to the file, then we add new features and save these changes via commits. (so that we can refer back to them)

2. when we made series of commits, it becomes pretty long.

3. suppose we want to add a new feature to our application, then we start making the feature by a commit and we keep working on that new feature.

4. some bugs happened in the mid way, so we need to reset back to that commit and fix the bug and keep working on the feature. this linear structure of changes doesn't good because we already made lot of changes for the new features.

5. branching allows us, rather than linear progression, we can have multiple different direction of progression.

6. master branch is the original version of code we working on. we can create other branches for different features that are still in progress. once we completed the feature so that we can merge into master branch.

7. If multiple teammates working on the same application, branching will be helpful. for instance, you will work on master branch and other people work on features and some other people on testing and so on.

8. when you complete adding features, then git allows you to merge to the master branch.

9. the default branch is master branch. we can add as many branches as we want. you can name them as you wish.

10. HEAD is used to indicate where you are in the current repo. usually it points to master branch, so you can change HEAD to points to feature branch so that you can work on them.

- It lists all the branches currently in the repository.

```shell

    git branch
```

- It creates a new branch in the current repository.

```shell

    git branch branch_name
```

- checkout command allows you move from one branch to another.

```shell

    git checkout branch_name
```

- merge allows you to merge a branch to the master.

```shell


    git merge branch_name

```
