# Create Heroku Project


## Heroku Upload
Go to project directory and type

```javascript
$ heroku
```
Login to Heroku

```javascript
$ heroku login
```
Add info to package.json

```git
"scripts": {
    "test": "echo \"Error: no test specified\" && exit 1", // remember add comma
    "start": "node app.js" //This line is new
  },
```
Initialize git repository in project root folder

```javascript
$ git init
```
Add files 

```javascript
$ git status
$ git add . // (stages new and modified, without deleted)
// You can also add files individually - Example: 
$ git add app.js
$ git add package.json
$ git add views/
```
Commit files

```git
$ git commit -m "initial commit"
```
Create Heroku project

```git
$ heroku create
```
Heroku project create w/ link

```git
//Heroku output after heroku create. Example:
Creating app... done, ⬢ whispering-hamlet-61266
https://whispering-hamlet-61266.herokuapp.com/ | https://git.heroku.com/whispering-hamlet-61266.git
//Initial link will state "Heroku | Welcome to your new app
```
Links to push code to

```javascript
$ git remote -v
heroku  https://git.heroku.com/whispering-hamlet-61266.git (fetch)
heroku  https://git.heroku.com/whispering-hamlet-61266.git (push)
```
Push master git repository to Heroku

```git
$ git push heroku master
```
Check for errors

```git
$ heroku logs
```
after rectifying issues or making changes

```git
$ git status
$ git add <filename>
$ git commit -m "leave note here"
```
Once rectified 

```git
$ git push heroku master
```
