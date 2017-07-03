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






