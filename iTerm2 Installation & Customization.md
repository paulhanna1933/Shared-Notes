# iTerm2 Installation & Customization
## Download iTerm2 | [Link](https://www.iterm2.com/)


## Once installed, open up iterm and click (command + ,) to enter into settings
![Image](https://api.monosnap.com/rpc/file/download?id=E54rLCctf4dqprpSP9a3TQunfs2tP7)
## Click on profiles > Window > Style: No Title Bar
![Image](https://api.monosnap.com/rpc/file/download?id=TcftRLT6JFNMsnxJolSw3l4kLAjUmE)
## Change Color Scheme
![Image](https://api.monosnap.com/rpc/file/download?id=d2FZRegMkERKa5umo3f8GU1tZynCjO)
## Preferences page will then forward to: [http://iterm2colorschemes.com/](http://iterm2colorschemes.com/)


![Image](https://api.monosnap.com/rpc/file/download?id=E57Qw2R3E9xIgbRFPi8W9i0Bhx7Mdw)
## Return to preferences > color presets > import > (import themes folder from downloaded file) 
![Image](https://api.monosnap.com/rpc/file/download?id=Fh6f5F856mOxeoJ881RgLRPit8kDij)
## View Git branch from terminal
open bash file in text editor

```git
$ atom .bashrc 
```
Copy & paste following code into .bashrc file & save

```javascript
# Git branch in prompt.
parse_git_branch() {
    git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}
export PS1="\u@\h \W\[\033[32m\]\$(parse_git_branch)\[\033[00m\] $ "
```
Restart terminal and view results!
![Image](https://api.monosnap.com/rpc/file/download?id=yJr71uKEuZxEUgYWh1zhvkXqqHN0dR)
## Custom Command Lines By Alias
Alias command customizes command lines


## Create Alias
Alias is great for creating syntax shortcuts. This method creates temporary alias. Once exited from terminal, they will no longer be available. 

```git
$ alias <somename> = commandlines
// examples
$ alias ex='exit'
$ alias ls='ls -l'
$ alias cl='clear'
$ alias fac='echo we are FAC2 of Nazareth'
```
## View created list of Alias

```git
$ alias
// Example output
alias ex='exit'
alias ls='ls -l'
alias cl='clear'
alias fac='echo we are FAC2 of Nazareth'
```
## How to remove Alias from terminal

```git
$ unalias <aliasname>
```
## Created Alias permanent
open bash file in text editor (Or any text editor)

```git
$ atom .bashrc 
```
![Image](https://api.monosnap.com/rpc/file/download?id=eTpZPmGE6wFCK0pTTvBRyQrm3lxcp6)
# Homebrew
## The missing package manager for macOS
## [Download for MAC](https://brew.sh/)
## [Download for Linux](http://linuxbrew.sh/)


## **Install HomeBrew | [undefinedbrew.sh**undefined]([object Object])
Copy and paste  installation link in terminal
![Image](https://api.monosnap.com/rpc/file/download?id=Kg71FXXbakIaxXa1Ej5z5KBOKCNjGk)










