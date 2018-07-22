### Redis 学习笔记

## 下载
官网下载地址：http://www.redis.io/download，下面使用的版本是redis-4.0.10.tar.gz

## 安装
- `cd /opt/appl/download`
- 解压 `tar -zxvf redis-4.0.10.tar.gz -C /opt/appl/`
- 编译 `cd src/`, 执行make，如果没有安装tcl，则需要执行`sudo apt install tcl`，然后再执行`make install`
- 安装完之后，会在src目录下生成几个可执行文件，分别是mkreleasehdr.sh redis-benchmark redis-check-aof redis-check-dump redis-cli redis-sentinel redis-server。其中redis-server是启动Redis服务的，redis-cli是进入Redis客户端的
- 文件迁移<br>
 `sudo mv mkreleasehdr.sh redis-benchmark redis-check-aof redis-cli redis-server /usr/local/redis/bin/` <br>
 `sudo mv redis.conf /usr/local/redis/etc/`
- 设置后台运行模式，`vi redis.conf`，把daemonize no修改成daemonize yes
- 设置密码 `vi redis.conf`，修改requirepass xxxxxx

## 服务命令
- `cd /usr/local/redis/bin`
- 启动`./redis-server ../etc/redis.conf`
- 停止`./redis-cli -a password shutdown`
- 连接 `./redis-cli -h ip -p port -a password`


## 其他
- 查看端口号状态 `netstat -tunpl | grep 6379` 
- 检查进程状态 `ps -ef|grep redis`
