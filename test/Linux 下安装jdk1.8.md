## Linux 下安装jdk1.8

1. 官网下载[jdk-8u144-linux-x64.tar](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)

2. 在windows下在下载好的jdk远程传输到linux下的/usr/java文件中

   ```shell
   cd /usr
   mkdir java
   ```

3. 在当前文件夹下解压jdk

   ```shell
   tar -zxvf jdk-8u144-linux-x64.tar.gz
   ```

4.  配置环境变量

   * 使用 `vi /etc/profile` 编辑profile文件
   * 在`/etc/profile`底部加入

   ```shell
   JAVA_HOME=/usr/java/jdk1.8.0_144
   PATH=$JAVA_HOME/bin:$PATH 
   CLASSPATH=$JAVA_HOME/jre/lib/ext:$JAVA_HOME/lib/tools.jar 
   export PATH JAVA_HOME CLASSPATH
   ```

5. 最后使用`source /etc/profile`让profile文件立即生效

6. 命令测试

   * 使用javac命令，不会出现command not found错误
   * 使用java -version，出现版本为java version "1.8.0_25"
   * `echo $JAVA_HOME, echo $CLASSPATH, echo $PATH`，看看自己的配置是否都正确。

   ​

