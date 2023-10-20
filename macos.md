### Dock mac os:
set delay for showing up:
```
defaults write com.apple.dock autohide-delay -float 0; killall Dock
```
set defaults:
```
defaults delete com.apple.dock autohide-delay; killall Dock
```
