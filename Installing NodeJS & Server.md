# NodeJS Environment


## Install NodeJS


Go to [nodejs.org ](https://nodejs.org)and download mature and dependable version
![Image](https://content.screencast.com/users/paulhanna33/folders/Jing/media/fead33b3-872a-4d9f-8f1a-ab8816c693c8/00000008.png)


Check if installed



```git
$ node -v //will output version
```


Create project folder anywhere on system (preferebly in documents or direct under user)



```git
$ mkdir <projectname>
```


Create server JS file inside the folder (server.js | app.js | index.js are conventional)



```git
$ touch server.js
```


Open project folder inside of text editor (Atom, sublime)


![Image](https://content.screencast.com/users/paulhanna33/folders/Jing/media/144e68cb-3cb4-4bd9-9be6-e5debf9a6585/00000009.png)


Include requirements inside of server.js file to create server



```javascript
var http = require('http');

function onRequest(request, response) {
    response.writeHead(200, {'Content-Type': 'text/plain'});
    response.write('Hello World');
    response.end();
}

http.createServer(onRequest).listen(8000); //will be viewable localhost:8000

```


In terminal (within root of project folder)  execute server



```git
$ node server.js
```


In browser type localhost:8000


![Image](https://content.screencast.com/users/paulhanna33/folders/Jing/media/0fd965d4-4b74-421c-8c4f-364e54459665/00000010.png)






