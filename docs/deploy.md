---
title: 安装指南
icon: leaf
order: 1
category:
  - 安装指南 
tag:
  - Markdown
---

## 前言
小派蒙推荐配置为4G运行内存及以上，最终大约需要5G存储空间。

关于Linux各种发行版，这里推荐您使用`Ubuntu20+`或`Debian11+`系统，**极不推荐**使用CentOS或其他不常见发行版系统。

本教程将通过[小派蒙脚手架插件](https://github.com/CMHopeSunshine/nb-cli-plugin-littlepaimon)，以最简时间从0搭建一个小派蒙机器人，通常你只需要跟着本教程**复制粘贴**即可。

本教程中关于[前置环境](#前置环境)、[安装go-cqhttp](#go-cqhttp)等可以参考[Well404](https://space.bilibili.com/33138220)的[NoneBot2.0.0RC 全平台保姆级新手教学](https://www.bilibili.com/video/BV1984y1b7JY)中的相关视频教程。

如安装过程中遇到问题可以在QQ频道中提问，点击上方QQ频道或[这里](https://pd.qq.com/s/kl9dor)加入。

::: warning 以下涉及到的命令中，#后面的为注释，不要复制运行。
:::

## 前置环境

### Windows
#### 安装Python
::: info 可以打开命令行，运行 python -V ，查看是否已安装，如已有版本为3.8~3.10，就不用再安装
:::
请参考该以下教程之一完成python的安装：
- [windows系统中python3.10安装简易教程](http://events.jianshu.io/p/e14a8cce863f)
- [Windows下Python3.9.13的安装教程](https://blog.csdn.net/weixin_43909005/article/details/128594336)

安装完成后，在命令行依次运行以下命令：
```shell
pip -V  # 查看指出的python版本是否为刚刚安装的版本
pip install pipx  # 安装pipx
pipx ensurepath  # 把pipx添加到环境变量
```

#### 安装git
::: info 可以打开命令行，运行 git --version ，查看是否已安装，如已安装就不用再安装
:::
请参考以下教程之一完成git的安装：
- [超详细Git 安装教程(Windows)](https://cloud.tencent.com/developer/article/2099150)
- [Windows安装git图文教程](https://blog.csdn.net/chen15369337607/article/details/119272661)


### Ubuntu
请使用**20.04**或**22.04**版本，这两个版本已自带派蒙所必需的**python**版本和**git**，其余版本请自行升级python到3.8-3.10版本。

依次执行以下命令：
```shell
sudo -i  # 获取root权限，如果本来就以root权限登录，那可以跳过
apt update && apt upgrade  # 更新系统
apt install pipx  # 安装pipx
pipx ensurepath  # 把pipx添加到环境变量
```

## 安装小派蒙

选择一个**你想要存放的目录**，打开命令行，依次运行以下命令：
::: warning 目录路径最好不要有中文，如果使用了中文路径，报错了的话请尝试更换为英文路径
:::
```shell
pipx install nb-cli  # 安装nonebot脚手架
nb self install nb-cli-plugin-littlepaimon  # 安装小派蒙脚手架插件
nb paimon create  # 创建小派蒙项目
```
::: tip 如果提示找不到nb，刷新或重启一下终端或命令行即可
:::

在运行`nb paimon create`后，脚手架会一步步指引安装，以下为可能出现的选项：
- 项目名称：你想要存放的小派蒙文件夹名，默认为`LittlePaimon`
- 克隆源：推荐默认，如果下载失败可尝试其他源
- 超级用户QQ号：相当于机器人的管理员，填写你自己的QQ号
- 立刻安装依赖：请选择是(直接回车)
- 创建虚拟环境：请选择是(直接回车)，随后会进行下载和安装依赖，时长取决于你的网络情况
- go-cqhttp安装和使用方式：详见下方[关于go-cqhttp](#go-cqhttp)


在创建完成后，**继续运行以下命令**：
```shell
cd LittlePaimon  # LittlePaimon为你刚刚填写的项目目录名
nb paimon res  # 给出的两次选择均保持默认
nb paimon run playwright install-deps  # 仅Ubuntu系统需要运行，安装playwright相关依赖
nb paimon run  # 启动小派蒙
```

以下为快速演示视频：

<a href="https://asciinema.org/a/555256" target="_blank"><img src="https://asciinema.org/a/555256.svg" /></a>

## go-cqhttp


`go-cqhttp`是一个无头QQ客户端，负责与小派蒙交互，进行消息的收发。

### 方式一 `nonebot-plugin-gocqhttp`插件
如果你使用的是**本地电脑**或有**公网IP**的的服务器，推荐使用 **`nonebot-plugin-gocqhttp`** 插件，
该插件会以子进程调用的方式让`go-cqhttp`和小派蒙一起运行。

如果选择了该方式，请在启动小派蒙后，在浏览器访问链接 **`http://127.0.0.1:13579/go-cqhttp`**
> 如果是云服务器，需开放13579端口，将`127.0.0.1`换成你的公网ip进行访问

该链接为插件提供的**网页控制台**，在控制台中**添加bot账号**，添加完成后需**重启**小派蒙使账号生效。

### 方式二 `go-cqhttp`本体
如果你的服务器没有公网IP，或插件版使用时出现问题不能解决，可使用 **`go-cqhttp`** 本体版。

本体版需要你在启动小派蒙时，额外启动`go-cqhttp`
- Windows: 双击`go-cqhttp.exe`，按指引运行
- Ubuntu(Linux): 在其目录下使用命令`./go-cqhttp`运行


> 如果你在`nb paimon create`创建派蒙时已经选择了插件版，想换成本体版，可以进行以下操作：
> - 1. 编辑小派蒙目录中的`pyproject.toml`文件， 找到`"nonebot_plugin_gocqhttp"`，将它和它后面的逗号删除，保存文件。
> - 2. 找一个合适的目录(例如小派蒙目录的上层)，运行`nb paimon create -g`，下载和配置`go-cqhttp`本体

### 账号登录不上
如果在云服务器上登录qq时有类似`有风险，请使用同一网络`、`验证失败`、`账号被冻结或密码错误`等提示而登录不上，
可以先在你的**本地电脑**下载go-cqhttp，登录同一账号，登录成功后，将`device.json`和`session.token`这两个文件上传到云服务器，**替换掉云服务器上的同名文件**，再次启动bot即可。

> 如果是gocq本体，那就是替换gocq所在目录的这两个文件。
> 
> 如果是gocq插件，那就是替换`小派蒙目录/accounts/你的qq号/`下的这两个文件。

## 后台运行

### Windows
需要保持命令行窗口一直运行，不能关闭(如果使用的是`go-cqhttp`本体，那它窗口也不能关闭)

### Ubuntu
推荐使用`screen`命令来管理后台运行。
::: tip 如果系统没有自带screen，可以使用命令 apt install screen 来安装
:::

在小派蒙所在目录，使用screen来后台运行小派蒙：
```shell
screen -S paimon nb paimon run
```
运行后，会新开一个终端窗口来运行派蒙，按 **`Ctrl+A+D`** 即可让它退到**后台**。

使用以下命令即可让它重新回到**前台**：
```shell
screen -r paimon
```
---

`go-cqhttp`本体版同理：
```shell
screen -S gocq ./go-cqhttp  # 运行
screen -r gocq  # 调回前台
```
---
关于`screen`的详细使用方法请参考[Linux screen命令 菜鸟教程](https://www.runoob.com/linux/linux-comm-screen.html)。

此外，你还可以使用`nohup`、`pm2`、`supervisor`等命令，请自行搜索。

## 其他
以下为之前使用Poetry来安装的老教程，供老用户参考：
- [环境配置](guide/environment-install.md)
- [安装小派蒙](guide/paimon-install.md)