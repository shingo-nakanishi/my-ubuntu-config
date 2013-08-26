## Document
* http://nekoya.github.io/blog/2013/01/24/sakura-vps-ubuntu/
* https://gist.github.com/tsabat/1498393
* https://help.ubuntu.com/community/VimHowto
* http://d.hatena.ne.jp/hogem/20060712/1152717623
* http://qiita.com/kazoo04/items/7056704efee66f323ddb


## su root
```
$ sudo su -
```

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
$ ufw enable
$ ufw default DENY
$ ufw allow ssh
```
restart Ubuntu!


## Install zsh
### in Ubuntu
check zsh isn't installed

```
$ cat /etc/shells
```

### Install zsh
```
$ apt-get install zsh
```

## Install Git, Vim
```
$ apt-get -y install git-core
$ apt-get install vim
```

## Config SSH (You can git clone from GitHub)
### Make ssh file connect from Ubuntu to Github
```
$ ssh-keygen -t rsa
```
and register yourkey to GitHub.

### Make ssh config
```
$ vim ~/.ssh/config

host github.com
   user git
   hostname github.com
   identityfile ~/.ssh/your_key
```

### Install rbenv
```
apt-get install build-essential bison libreadline6-dev curl git-core zlib1g-dev libssl-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev autoconf libncurses5-dev
```
* https://github.com/sstephenson/rbenv

### Install bundler
* http://bundler.io/

```
$ gem install bundler
```
