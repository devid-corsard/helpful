### Dock mac os:
set delay for showing up (ex: 3 sec):
```
defaults write com.apple.dock autohide-delay -float 3.0; killall Dock
```
set defaults:
```
defaults delete com.apple.dock autohide-delay; killall Dock
```
### Key repet rate
You can also change the preference keys by running the following in Terminal:
```
defaults write -g InitialKeyRepeat -int 10 # normal minimum is 15 (225 ms)
defaults write -g KeyRepeat -int 1 # normal minimum is 2 (30 ms)
```
The changes aren't applied until you log out and back in. KeyRepeat can't be set between 2 (30 ms) and 1 (15 ms) though.
