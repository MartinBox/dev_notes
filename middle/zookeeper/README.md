## Zookeeper 学习笔记

### 环境搭建
机器环境信息：Ubuntu 18.0.4 Thinkpad E430C
zookeeper版本：zookeeper-3.4.12.tar.gz
zookeeper的安装分为三种模式：单机模式、集群模式和伪集群模式。以下为伪集群为例。

### 安装
- `cd /opt/appl/zookeeper` 分别新建 server1 server2 server3，模拟三台zk服务
- 解压`tar -zxvf zookeeper-3.4.12.tar.gz -C /opt/appl/zookeeper/server1/` ...server2  ...server3
- 配置文件 `cd /opt/appl/zookeeper/server1/zookeeper-3.4.12/conf` ,默认名字为zoo_sample.cfg，需要改下，`mv zoo_sample.cfg zoo.cfg` <br>
  修改zoo.cfg文件，设置data保存路径以及日志路径,详细配置见zoo.cfg
- 在server1/data目录下创建myid文件，并写入1，其他server分别为2 3，用来标识集群机器

### 常用命令
- 启动 `./zkServer.sh start`
- 停止 `./zkServer.sh stop`
- 状态 `./zkServer.sh status`
