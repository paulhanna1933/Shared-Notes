# Git Install & Commands


## Install Git from this [link](https://git-scm.com/)


See what version of git is installed



```git
$ git --version 
```


Create git directory in any folder or within project folder at root point



```git
$ mkdir <gitFolderName>
```


CD into the folder



```git
$ cd <gitFolderName>
```


Test git by creating file inside folder



```git
$ touch test.js
```


Initialize Git



```git
$ git init
```


Check repository status



```git
$ git status
```


Add to repository



```git
$ git add . //to add everything
$ git add -A //to add everything
$ git add filename.js //to add individual files
```


Commit to git



```git
$ git commit -m "add message here" // final stage to save commited version
```
Git Push Origin

```git
$ git push <filename>
```
View all logged commits

```git
$ git log 
```
Change Branch

```git
$ git checkout <branchname> 
```
