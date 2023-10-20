## SSH keypair setup for GitHub (or GitHub/GitLab/BitBucket, etc, etc)


### Generate a SSH key pair (private/public):
```
ssh-keygen -t rsa -C "your_email@example.com"
```

or even better:
```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

### Copy the contents of the public SSH key

macOS:
```
pbcopy < ~/.ssh/id_rsa.pub
```
GNU/Linux (requires the xclip package):
```
xclip -sel clip < ~/.ssh/id_rsa.pub
```
Windows Command Line:
```
type %userprofile%\.ssh\id_rsa.pub | clip
```
Git Bash on Windows / Windows PowerShell:
```
cat ~/.ssh/id_rsa.pub | clip
```

or ofcourse copy it via your favorite editor, cat, or whatever suits your needs :)


### Copy the public SSH key to GitHub
Copy the contents of the to your SSH keys to your GitHub account settings (https://github.com/settings/keys).


### Test the SSH key:
```
ssh -T git@github.com
```
The keys need to be read-writable only by you:
```
chmod 600 ~/.ssh/id_rsa
```

Add the key to the ssh-agent
```
ssh-add ~/.ssh/id_rsa
