# version control

- when building a project, how do we track of different versions of code.
- collaborate with other people.

- if we make a change to the code and it didn't work, so we go back to previous version of code.

## git
1. keeping track of different versions to the code
- so if add a line or remove a line, you can access to those history.
- keeping track of all changes happened to a file/folder or entire project.

2. synchronizing between different people working on the project.

3. testing a code without modifying existing codebase (without losing original copy) (testing a new feature)

4. revert back to older version of code.

## github

- storing git repo in the internet

- we can access other people, company's git repos and also host our own repo's, so that other contributors, collaborators access your codebase.

### creating a repository (all project files stored here)

- It consists of all code and the changes you made to the code stored here.

- creating a repo in github will only present in github server. it's not in our computer, so we need to take a copy of the repo in the local machine.

### git clone ```<url>```

- it takes the repo from remote server (like github) and remote version of the code downloaded to your local machine.

- now you have the copy in your own computer.

---
    After you write certain amount of code you want to save or make certain changes next thing to do (every code or anything you do will via files & folder)

---

### git add ```<file/folder>```
+ take one or more files changed and tell git that these are the files to be included the next time we make a commit (version or snapshot of the current repo)
+ git add ```<filename>``` tells git to track that file

### git commit
+ commit is used to take a snapshot of the repos or just save this version.

    ```git commit -m "message"```

    ```git commit -am "message"```
    adds to staging area and commits with single command.

    m stands for message
+ message is just helpful description that tells what changes i've made in this commit.

![git-commit](git-commit.png)

+ this command will create a new version or snapshot of the current repo and also keeping track of older version of code.

### git status
+ this command tells the current status of the repo.

    ```git status```

### git push
+ push our code (send our changes) to the remote repo (in this case github).
    
    ```git push```

### git pull
+ someone made changes and pushed to repo and now you want to download the latest changes happened on that repo.
    
    ```git pull```

### merge conflicts
+  when you save some changes in local repo and some changes in remote repo, when you try to pull down the changes and it matches, then merge conflicts arise.

### git log
+ it lists all the different commits made to this repo.
    
    ```git log```

### git reset

- if you made some changes and you're not okay with it, then you can revert back to older version.

    ```git reset --hard <commit hash>```
    - revert back to version based on commit hash
    
    ```git reset --hard origin/master```
    
    - revert back to origin

### git reflog
+ it logs all the reference git track of.
    
    ```git reflog```





# HTML
+ HTML means hyper text markup language.
+ it is used to structure the content of a web page.

```
    <!DOCTYPE html> 
    <html>
        <head>
            <title>My Web Page</title>
        </head>
        <body>
            Hello, World!
        </body>
    </html>
```
+ <!DOCTYPE html> represents it's html5 version
+ 
