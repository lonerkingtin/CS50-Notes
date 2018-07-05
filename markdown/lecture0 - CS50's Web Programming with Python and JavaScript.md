# CS50's Web Programming with Python and JavaScript

## version control

- when building a project, how do we track of different versions of code.
- collaborate with other people.

- if we make a change to the code and it didn't work, so we go back to previous version of code.

## git

1.keeping track of different versions to the code

- so if add a line or remove a line, you can access to those history.
- keeping track of all changes happened to a file/folder or entire project.

2.synchronizing between different people working on the project.

3.testing a code without modifying existing codebase (without losing original copy) (testing a new feature)

4.revert back to older version of code.

## github

- storing git repo in the internet

- we can access other people, company's git repos and also host our own repo's, so that other contributors, collaborators access your codebase.

### creating a repository (all project files stored here)

- It consists of all code and the changes you made to the code stored here.

- creating a repo in github will only present in github server. it's not in our computer, so we need to take a copy of the repo in the local machine.

### git clone url

- it takes the repo from remote server (like github) and remote version of the code downloaded to your local machine.

- now you have the copy in your own computer.

---
    After you write certain amount of code you want to save or make certain changes next thing to do (every code or anything you do will via files & folder)

---

### git add file/folder

- take one or more files changed and tell git that these are the files to be included the next time we make a commit (version or snapshot of the current repo)

- git add ```<filename>``` tells git to track that file

### git commit

- commit is used to take a snapshot of the repos or just save this version.

    ```git
    git commit -m "message"
    ```

    ```git
    git commit -am "message"
    ```
    adds to staging area and commits with single command.

    m stands for message
- message is just helpful description that tells what changes i've made in this commit.

- this command will create a new version or snapshot of the current repo and also keeping track of older version of code.

### git status

- this command tells the current status of the repo.

    ```git
    git status
    ```

### git push

- push our code (send our changes) to the remote repo (in this case github).

  ```git
  git push
  ```

### git pull

- someone made changes and pushed to repo and now you want to download the latest changes happened on that repo.

   ```git
   git pull
   ```

### merge conflicts

- when you save some changes in local repo and some changes in remote repo, when you try to pull down the changes and it matches, then merge conflicts arise.

### git log

- it lists all the different commits made to this repo.

  ```git
  git log
  ```

### git reset

- if you made some changes and you're not okay with it, then you can revert back to older version.

  ```git
    git reset --hard <commit hash>
  ```

  - revert back to version based on commit hash.

  ```git
    git reset --hard origin/master
  ```

  - revert back to origin

### git reflog

- it logs all the reference git track of.

    ```git
        git reflog
    ```

## HTML

- HTML means hyper text markup language.

- it is used to structure the content of a web page.

```html

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

- line 1 represents it is html5 version. the browser identifies its in HTML5 version.

- Tags begins with opening angle bracket and ending with closing angle bracket. eg) ```<html>, <head>, <body>```

- most html tags has an ending tag. ending tag begins with / symbol.
  eg) ```</html>, </head>, </body>```

- ```<head>``` tag contains meta-data i.e information about the page.

- it didn't appear on the screen but telling important info about your page to the browser.

- ```<title>``` tag lets you to set the title of the webpage.

- Actually web content will be settled inside ```<body>``` tag.

- the browser actually interprets the ```<title>``` tag and screens it in top of the title bar, ```<body>``` tag content will screens it in main area of the browser. the browser understands the html and displays it appropriately.

- indentation is just for style not necessary. but it helps us to read the html code more easily.

## headings

- ```<h1>``` is used to specify the heading text.

- ```<h1>``` for big heading text and moving from ```<h2>``` to ```<h6>``` will decrease the size of heading text.

```html

  <h1>This is heading level 1</h1>
  <h2>this is heading level 2</h2>
  <h3>this is heading level 3</h3>
  <h4>this is heading level 4</h4>
  <h5>this is heading level 5</h5>
  <h6>this is heading level 6</h6>

```

## viewing page source in browsers

- right click the browser and click "view page source"

- that way you can see the source of the webpage.

## lists

```html
  <ul>
    <li>one item</li>
    <li>another item</li>
    <li>yet another item</li>
  </ul>
  <ol>
    <li>first item</li>
    <li>second item</li>
    <li>third item</li>
  </ol>
```

- ul means unordered list, ol means ordered list, li means list.

- unordered list representation will be bullets and ordered list representation will be numbers.

Note:

- when you want someone to read the list in linear way, then use numbers else use bullets (don't want the user to read in linear way.)

## images

    ```html
        <img src="cat.jpg">
    ```

- in this ```<img>``` tag, we only see starting tag and not the ending ```</img>``` tag, because it doesn't make sense to put an end tag. start the image and end the image and what goes inside is not making any sense.

- src means source of the image file. it's an html attribute which adds additional information to this img tag.

- without src attribute ```<img>``` tag don't know which images file to render.

- height attribute sets the height of the image in pixels.

- width attribute sets the width of the image in pixels.

- when you don't specify height and width attribute, then the default image pixels will be taken into account.

- instead of specifying pixels for width and height, you can also specify width and height using percentage.

```<img src="cat.jpg" width = 75% >```

- this image will take 75 percent width of the total size.

## Tables

```html

    <table>
        <tr>
            <th>First Name</th>
            <th>Last Name</th>
            <th>Years in Office</th>
        </tr>
        <tr>
            <td>George</td>
            <td>Washington</td>
            <td>1789-1797</td>
        </tr>
        <tr>
            <td>John</td>
            <td>Adams</td>
            <td>1797-1801</td>
        </tr>
    </table>

```

- ```<table>``` tag is used to create a table.

- ```<tr>``` means table row. it is used to create a row in a table.

- ```<th>``` means table header. it is used to create a header in a table.

- ```<td>``` means table data. it is used to create each individual cell in a table.

- when we create table using html, there is no borders, colors or styles. we can give this by using css.

## form controls (HTML4)

- form control is used to get information from the user.

- Like sign up for our website or login into our websites,
survey, poll etc.

```html

    <form>
        <input type="text" placeholder="Full Name" name="name">
        <button>Submit!</button>
    </form>

```

## Document Object Model

- think html like a tree structure.

- why we need to understand like this, is because once we start learning javascript we start manipulate the tree structure, by add things to trees, remove things from trees and so on.

## paragraph tag

- ```<p>``` tag is used to create a paragraph of text in html.



## Cascading StyleSheet

- css means cascading stylesheet.

- it is used to style the html tags.

```html

    <h1 style="color:blue;text-align:center;">Welcome to My Web Page!</h1>

```

- we can apply css styles by using style attribute. it is called inline style.

- every css property is in key-value pairs i.e ```color:blue```, ```text-align:center``` and must be ended with semi-colon ```;```

## colors



## text-align

- text-align property is used to align the text and the values will be ```left```, ```center```, ```right```.

## style Tag








