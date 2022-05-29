# gitflow
> 使用内容不做多累述

## 在win下的使用

### 相关组件
~~~html
「gitflow」https://www.aliyundrive.com/s/Btg2JpZB8KD
点击链接保存，或者复制本段内容，打开「阿里云盘」APP ，无需下载极速在线查看，视频原画倍速播放。
~~~
如上进入阿里云盘下载分享即可
相关
### win下安装
* Git flow是git的一个扩展集，它基于Vincent Driessen 的分支模型，可以用来简化代码的版本发布流程。
  * 本文讲述如何为msysgit安装git flow。

* 下载getopt.exe
  * 解压，进入bin目录，复制其中的getopt.exe文件到你的git安装目录，例如，D:\Program Files (x86)\Git\bin

* 下载libintl3.dll

  * 解压，进入bin目录，复制libintl3.dll文件到你的git安装目录。

* 下载libiconv2.dll
  * 解压，进入bin目录，复制libiconv2.dll文件到你的git安装目录。

* 获取git flow的代码
  * 打开git bash，输入以下命令：

  * git clone -–recursive git://github.com/nvie/gitflow.git

  * 运行git flow的安装脚本
  * 打开windows的cmd（可能需要管理员权限），进入上面的git flow代码目录，键入以下命令：

  * cd gitflow

  * cd contrib
  * msysgit-install.cmd [git的安装目录]

  * 例如，

  * msysgit-install.cmd “D:\Program Files (x86)\Git”
  * 无需处理报错
### 命令行处理方式
  
#### 脚本命令
~~~shell
# 新建
# git flow 分支类型 start 分支名 例如：
git flow feature start 1.0.0.1/LWC/AddUserLogin

# 推送到远端留档
# git flow 分支类型 publish 分支名 例如：
git flow feature publish 1.0.0.1/LWC/AddUserLogin

# 完成并保留本地分支
# git flow 分支类型 finish -k 分支名 例如：
git flow feature finish -k 1.0.0.1/LWC/AddUserLogin
~~~

#### 传统命令
> 把分支名当做带'/'的特殊分支名就行
~~~shell
git checkout A
git pull 
git checkout -b feature/b
# 开发结束
git checkout A
git pull
git merge --no-ff feature/b
# 处理冲突
~~~
