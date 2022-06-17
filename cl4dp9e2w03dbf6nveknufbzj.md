## 云Linux安装OpenJDK

创建目录

    1 cd /usr/local/
    2 mkdir java
    3 cd /usr/local/java

下载压缩包

    1 wget https://download.java.net/openjdk/jdk11/ri/openjdk-11+28_linux-x64_bin.tar.gz

解压

    1 tar -xvf openjdk-11+28_linux-x64_bin.tar.gz

配置环境变量

    1 vim /etc/profile

在文件末尾插入 jdk 路径

    1 export JAVA_HOME=/usr/local/java/jdk-11
    2 export CLASSPATH=$JAVA_HOME/lib
    3 export PATH=$JAVA_HOME/bin:$PATH

如图

![云Linux安装JDK11VIM配置.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655182768074/3jZZNe8RA.png align="left")

ESC + :wq 保存退出
刷新系统配置

    1 source /etc/profile

校验

    1 javac 
    2 # 或者 
    3 java -version
