   Here is the help of Git Command.
   
## Git help 获取git基本命令
```bash
   # 查询clone命令 
   git help clone
```

## Git help 创建一个空的Git库
```bash
   git init
   git init-db
```

## Git add 添加文件
```bash
   # 添加dir1这个目录，目录下的所有文件都被加入
   git add dir1
   # 添加f1，f2文件
   git add f1 f2
   # 添加当前目录下的所有文件和子目录
   git add .
```

## Git rm 删除文件
```bash
   # 进入某个目录中，执行此语句，会删除该目录下的所有文件和子目录
   git rm –r *
   # 删除文件f1，包含本地目录和index中的此文件记录
   git rm f1
   # 删除文件f1，不会删除本地目录文件，只删除index中的文件记录
   git rm --ached f1
```

## Git commit 提交修改
```bash
   # 直接调用git commit命令，会提示填写注释
   git commit 
   # 可以将那些没有通过git add标识的变化一并强行提交
   git commit -a
   # 在一个commit id上不断修改提交的内容
   git commit –-amend –m “message” 
```

## Git status 查询变化
```bash
   git status
```

## Git log 查询日志
```bash
   # -1的意思是只显示一个commit
   git log -1 
   # 显示每次版本的详细变化
   git log --stat –summary
```

## Git merge 代码合并
```bash
   # 将服务器git库的eclair_eocket分支合并到本地分支上
   git merge nov/eclair_eocket 
   # 将本地分支上的变化合并到这个临时分支，然后再用这个临时分支初始化本地分支
   git rebase nov/eclair_eocket
```

## Git merge 代码合并
```bash
   # 将服务器git库的eclair_eocket分支合并到本地分支上
   git merge nov/eclair_eocket 
   # 将本地分支上的变化合并到这个临时分支，然后再用这个临时分支初始化本地分支
   git rebase nov/eclair_eocket
```

## Git diff 代码比较
```bash
   # 比较工作目录和Index中的代码
   git diff 
   # 比较index和本地仓库中的代码
   git diff - - cached 
```
 
## Git checkout 切换分支 
```bash
   # 创建一个新分支，并切换到该分支上
   git checkout –b 新分支名 
   # 切换到某个已经建立的本地分支local_branch(cat .git/HEAD后，显示refs:refs/heads/ local_branch)
   git checkout local_branch 
   # 切换到服务器上的某个分支remote_branch（远程分支remote_branch可以通过 git branch –r 列出） 
   git checkout remote_branch 
   # 切换到某个commit id（使用cat .git/HEAD后，显示commit_id） 
   git checkout commit_id 
   # 切换到某个tag （使用cat .git/HEAD后，显示tag） 
   git checkout tag 
```

## Git checkout 初始化新分支
```bash
   # 切换到某个已经建立的本地分支local_branch，并且使用此分支初始化一个新分支new_branch。 
   git checkout –b new_branch local_branch 
   # 切换到某个远程分支remote_branch，并且用此分支初始化一个新分支new_branch。 
   git checkout –b new_branch remote_branch 
   # 切换到某个commit id，并建立新分支new_branch 
   git checkout –b new_branch commit_id 
   # 切换到某个tag，并建立新分支new_branch 
   git checkout –b new_branch tag 
```

## Git checkout 初始化新分支
```bash
   # 将user.rb文件从上一个已提交的版本中更新回来，未提交的工作目录中的内容全部会被覆盖。
   git checkout app/model/user.rb
```

## Git-ls-files 
   查看当前的git库中有那些文件。
   
## Git mv 
   重命名一个文件、目录或者链接。
```bash
   # 把文件helloworld.c 重命名为 helloworld1.c
   git mv helloworld.c helloworld1.c
```

   This script is free collection of shell scripts for rapid deployment of `LNMP`/`LAMP`/`LANMP` stacks (`Linux`, `Nginx`/`Tengine`, `MySQL`/`MariaDB`/`Percona` and `PHP`) for CentOS/Redhat Debian and Ubuntu.

   Script features: 
- Constant updates 
- Source compiler installation, most source code is the latest stable version, and downloaded from the official website
- Fixes some security issues 
- You can freely choose to install database version (MySQL-5.6, MySQL-5.5, MariaDB-10.0, MariaDB-5.5, Percona-5.6, Percona-5.5)
- You can freely choose to install PHP version (php-5.5, php-5.4, php-5.3)
- You can freely choose to install Nginx or Tengine 
- You can freely choose to install Apache version (Apache-2.4, Apache-2.2) 
- According to their needs can to install ngx_pagespeed
- According to their needs can to install ZendOPcache, xcache, APCU, eAccelerator, ionCube and ZendGuardLoader (php-5.4, php-5.3) 
- According to their needs can to install Pureftpd, phpMyAdmin
- According to their needs can to install memcached, redis
- According to their needs can to optimize MySQL and Nginx with jemalloc or tcmalloc 
- Add a virtual host script provided 
- Nginx/Tengine, PHP, Redis, phpMyAdmin upgrade script provided
- Add backup script provided 

## How to use 

```bash
   yum -y install wget screen # for CentOS/Redhat
   #apt-get -y install wget screen # for Debian/Ubuntu 
   wget http://blog.linuxeye.com/lnmp.tar.gz
   #or wget http://blog.linuxeye.com/lnmp-full.tar.gz # include source packages
   tar xzf lnmp.tar.gz
   cd lnmp
   chmod +x install.sh
   # Prevent interrupt the installation process. If the network is down, you can execute commands `screen -r lnmp` network reconnect the installation window.
   screen -S lnmp
   ./install.sh
```

## How to add a virtual host

```bash
   ./vhost.sh
```

## Hown to backup

```bash
   ./backup_setup.sh # Set backup options 
   ./backup.sh # Start backup, You can add cron jobs
   # crontab -l # Examples 
     0 1 * * * cd ~/lnmp;./backup.sh  > /dev/null 2>&1 &
```

## How to manage service
Nginx/Tengine:
```bash
   service nginx {start|stop|status|restart|condrestart|try-restart|reload|force-reload|configtest}
```
MySQL/MariaDB/Percona:
```bash
   service mysqld {start|stop|restart|reload|force-reload|status}
```
PHP:
```bash
   service php-fpm {start|stop|force-quit|restart|reload|status}
```
Apache:
```bash
   service httpd {start|restart|graceful|graceful-stop|stop}
```
Pure-Ftpd:
```bash
   service pureftpd {start|stop|restart|condrestart|status}
```
Redis:
```bash
   service redis-server {start|stop|status|restart|condrestart|try-restart|reload|force-reload}
```
Memcached:
```bash
   service memcached {start|stop|status|restart|reload|force-reload}
```

## How to upgrade 
```bash
   ./upgrade_php.sh # upgrade PHP
   ./upgrade_web.sh # upgrade Nginx/Tengine
   ./upgrade_redis.sh # upgrade Redis 
   ./upgrade_phpmyadmin.sh # upgrade phpMyAdmin 
```

## How to uninstall 

```bash
   ./uninstall.sh
```

   For feedback, questions, and to follow the progress of the project (Chinese): <br />
   [lnmp最新源码一键安装脚本](http://blog.linuxeye.com/31.html)<br />
