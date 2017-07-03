# Install Brew | Node | MongoDB |


## Install HomeBrew | [brew.sh](http://www.brew.sh)
Copy and paste  installation link in terminal


## Instsall Node

```markdown
$ brew install node
// Check version
$ node -v
// If update needed
$ brew upgrade node
```
## Install MongoDB

```git
$ brew install mongo
```
Create data directory

```git
$ sudo mkdir -p /data/db
// Must enter password
```
Take directory ownership

```git
$ whoami // Will output user name
$ sudo chown -Rv <whoamiusername> /data/db
```
Startup local mongo server

```git
$ mongod
```
If you want MongoDB to always run

```git
$ brew services start mongo
```


## Robomongo | [Download](http://robomongo.org/download)
Install Robomongo


Create DB in Robomongo
![Image](https://api.monosnap.com/rpc/file/download?id=n2uo0qM0kgApfFPDK4CXYwv2uNgXGQ)
Connect to DB
![Image](https://api.monosnap.com/rpc/file/download?id=ONj1aIbEFUfG8KFmINdMgiGf5lX6eh)
