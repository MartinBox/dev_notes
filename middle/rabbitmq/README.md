### RabbitMQ服务安装备忘录

## 下载

官网下载地址：www.rabbitmq.com/download.html，文件名：rabbitmq-server_3.7.6-1_all.deb

## 安装

- sudo dpkg -i 文件
  安装过程中可能会报错，如：未安装软件包 erlang-nox，此时需要执行：sudo apt-get install erlang-nox，
  如要继续提示：请尝试不指明软件包的名字来运行“apt --fix-broken install”，则执行：sudo apt --fix-broken install


## 服务命令
- 启动：sudo rabbitmq-server start
- 停止：sudo rabbitmq-server stop / sudo rabbitmqctl stop 后者生效，前者不生效，不知道什么原因？？
- 重启：sudo rabbitmq-server restart
- 状态：sudo rabbitmqctl status

## 权限
- 添加用户muscle，设置密码coder
sudo rabbitmqctl add_user muscle coder
- 赋予权限
sudo rabbitmqctl set_user_tags muscle administrator
- 赋予virtual host中所有资源的配置/写/读权限以便管理其中的资源
sudo rabbitmqctl set_permissions -p / muscle '.*' '.*' '.*'

## 网页控制台
- 进入安装目录：cd /usr/lib/rabbitmq
- 查看已经安装的插件：rabbitmq-plugins list
- 开启网页控制台：rabbitmq-plugins enable rabbitmq_management
- 重启rabbitmq服务
- 网页访问：http://127.0.0.1:15672，账号：muscle 密码：coder

## 日志查看
/var/log/rabbitmq/rabbit@[hostname].log  hostname:主机名
例如：/var/log/rabbitmq/rabbit@thinkpad.log
