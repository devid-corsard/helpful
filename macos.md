### Dock mac os:
set delay for showing up (ex: 3 sec):
```
defaults write com.apple.dock autohide-delay -float 3.0; killall Dock
```
set defaults:
```
defaults delete com.apple.dock autohide-delay; killall Dock
```
