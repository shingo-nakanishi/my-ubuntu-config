## Document
* http://nekoya.github.io/blog/2013/01/24/sakura-vps-ubuntu/
* https://gist.github.com/tsabat/1498393
* https://help.ubuntu.com/community/VimHowto
* http://d.hatena.ne.jp/hogem/20060712/1152717623
* http://qiita.com/kazoo04/items/7056704efee66f323ddb
* http://d.hatena.ne.jp/tkrd/20120828/1346123699


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

### change login sh to zsh
```
$ chsh

>>> input zsh path
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

### Install my-config


#### Edit ~/my-config/zsh-config/zshrc.zsh
like this
```
#export LANG=ja_JP.UTF-8
export LC_ALL=en_US.UTF-8
```

### Install rbenv
```
$ apt-get install build-essential bison libreadline6-dev curl git-core zlib1g-dev libssl-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev autoconf libncurses5-dev
```
* https://github.com/sstephenson/rbenv

### Install bundler
* http://bundler.io/

```
$ gem install bundler
```

### Instal Gitlab
* https://github.com/gitlabhq/gitlabhq/blob/master/doc/install/installation.md
* http://stackoverflow.com/questions/10051448/error-failed-to-build-gem-native-extension-mysql2-on-rails-3-2-3
* http://ubuntuforums.org/showthread.php?t=2061057
* http://stackoverflow.com/questions/13018626/add-apt-repository-not-found


#### if your git < 1.7.10
<= 12.04
```
sudo apt-get install python-software-properties
```
for >= 12.10
```
sudo apt-get install software-properties-common
```

```
$ sudo add-apt-repository ppa:voronov84/andreyv
$ sudo apt-get update
$ sudo apt-get upgrade
$ sudo apt-get install git
```

#### open ufw port
If you use ufw open port for gitlab.
