## Document
http://nekoya.github.io/blog/2013/01/24/sakura-vps-ubuntu/
https://gist.github.com/tsabat/1498393
https://help.ubuntu.com/community/VimHowto

## Make ssh file connect from Mac to Ubuntu
### in Mac
```
$ ssh-keygen
```

### in Ubuntu
```
$ mkdir .ssh
$ chmod 700 .ssh
```
Paste public key to `~/.ssh/authorized_keys`
```
$ sudo chmod 600 .ssh/authorized_keys
```

### Only connect use public key
Edit file `/etc/ssh/sshd_config`
```
PermitRootLogin no
PasswordAuthentication no
```

## ufw
```
$ sudo ufw enable
$ sudo ufw default DENY
$ sudo ufw allow ssh
```
restart Ubuntu!



## Install zsh
### in Cent OS
check zsh isn't installed

```
$ cat /etc/shells
```

### Install zsh
```
$ sudo apt-get install zsh
```

## Config SSH (You can git clone from GitHub)
### Make ssh file connect from Cent OS to Github
```
$ ssh-keygen -t rsa
```
and register yourkey to GitHub.

### Make ssh config
```
vim ~/.ssh/config

host github.com
   user git
   hostname github.com
   identityfile ~/.ssh/your_key
```
