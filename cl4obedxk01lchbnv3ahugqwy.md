## Win 11 家庭版获取管理员权限

# Win 11 家庭版获取管理员权限

>   作者：特立独行的汤姆猫 https://www.bilibili.com/read/cv15310135/ 出处：bilibili

  家庭版没有组策略工具，这个时候win + R 运行gpedit.msc是没反应的，需要自己建立一个脚本打开组策略，方法来自网络，如下：

  新建一个txt文档，复制下面代码，保存为xxx.bat，右键管理员权限运行，耐心等待安装完成即可。 

```shell
@echo off

pushd "%~dp0"

dir /b C:\Windows\servicing\Packages\Microsoft-Windows-GroupPolicy-ClientExtensions-Package~3*.mum >List.txt

dir /b C:\Windows\servicing\Packages\Microsoft-Windows-GroupPolicy-ClientTools-Package~3*.mum >>List.txt
for /f %%i in ('findstr /i . List.txt 2^>nul') do dism /online /norestart /add-package:"C:\Windows\servicing\Packages\%%i"

pause 
```

1、在右下方任务栏的“搜索web和windows”输入框中输入“gpedit.msc”，电脑会自行搜索，搜索完毕之后鼠标点击打开。

2、打开本地组策略管理器。

3、依次点击打开“计算机配置”选项，然后再找到“Windows设置”这个选项，再从“Windows设置”找到并打开“安全设置”选项，接着打开“本地策略”最后找到打开“安全选项”即可。

4、找到“账户：管理员状态”，可以看见状态为“已禁用”，需要的是将它开启。

5、鼠标右键单击“账户：管理员状态”，在弹出的快捷菜单中选择“属性”。

6、在“账户：管理员状态”属性中，将以启用选中即可。