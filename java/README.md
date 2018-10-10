# Java

## jdk安装
安装文件存放目录：/opt/appl/soft

1 解压：`tar -zxvf jdk-8u181-linux-x64.tar.gz` <br/>
2 设置环境变量：`sudo vi /etc/profile` 在文件头部添加如下内容 <br />

  `export JAVA_HOME=/opt/soft/jdk1.8.0_181` <br />
  `export JRE_HOME=${JAVA_HOME}/jre` <br />
  `export CLASSPATH=.:${JAVA_HOME}/lib:${JRE_HOME}/lib` <br />
  `export  PATH=${JAVA_HOME}/bin:$PATH` <br />

  执行 `source /etc/profile` 使变量生效 <br />

3 检查 `java -version`

