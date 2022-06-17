## Linux 配置系统环境变量

# Linux 查看系统环境变量

## 查看当前系统定义的所有环境变量

>   使用export命令可查看当前系统定义的所有环境变量

## 查看单个环境变量的值

>   echo $ENV可查看单个环境变量的值，如查看PATH环境变量的值

```shell
echo $PATH
```

其中PATH变量定义了运行命令的查找路径，以冒号:分割不同的路径。

## 配置当前用户临时环境变量

>   export直接修改环境变量：

```shell
export $PATH='/home/blacksuit/bin:$PATH'
```

配置后立即生效，且仅对当前用户，当前终端有效，如下开启新终端后，PATH中不存在/home/blacksuit/bin。

**记得加上PATH（加在前面也是一样）且用:分隔，避免覆盖原来的PATH配置**

## 配置当前用户永久环境变量

>   vim ~/.bashrc 或 vim ~/.bash_profile 在最后一行加入需要添加的环境变量，如果~/.bash_profile文件不存在，则可编辑~/.profile或新建一个文件


![图片.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655205763279/UD-4RMjxq.png align="left")

## 配置所有用户永久环境变量

>   sudo vim /etc/bashrc 或 sudo vim /etc/profile 或 vim /etc/environment 在最后一行加入需要添加的环境变量，这是修改系统配置，需要管理员权限或写入权限


![图片.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655205884188/bSYspm_Wz.png align="left")


## shell配置文件加载

#### Shell配置文件（脚本）的加载

无论是否是交互式，是否是登录式，Bash Shell 在启动时总要配置其运行环境，例如初始化环境变量、设置命令提示符、指定系统命令路径等。这个过程是通过加载一系列配置文件完成的，这些配置文件其实就是 Shell 脚本文件。

 与 Bash Shell  有关的配置文件主要有 /etc/profile、~/.bash_profile、~/.bash_login、~/.profile、~/.bashrc、/etc/bashrc、/etc/profile.d/*.sh，不同的启动方式会加载不同的配置文件。

>   ​	`~`表示用户主目录。`*`是通配符，/etc/profile.d/*.sh 表示 /etc/profile.d/ 目录下所有的脚本文件（以`.sh`结尾的文件）。

Shell四种运行方式（启动方式）: //c.biancheng.net/view/3045.html

Shell配置文件（脚本）的加载: //c.biancheng.net/view/3052.html



————————————————
版权声明：本文为CSDN博主「萧民工」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/u010306832/article/details/117785894