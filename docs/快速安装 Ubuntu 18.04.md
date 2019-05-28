内容列表



1.准备工作：安装前的准备

2.快速安装及认识界面：安装并认识 Ubuntu，知道最常规操作

3.系统设置：添加中文支持，设置系统时区

4.安装常用软件：选择国内的镜像服务器，安装常用软件



1、准备工作



目标：做好安装前的准备工作

1.访问https://www.ubuntu.com/download/desktp下载 Ubuntu 18.04 桌面版

2.在操作系统上安装 VMWare Fusion 虚拟机软件

提示：选择使用虚拟机，既不需要准备额外的电脑，又可以大胆尝试，不用担心造成不可逆的破坏。



2、快速安装及认识界面

##  

快速安装 Ubuntu

认识 Ubuntu 界面



**2.1快速安装 Ubuntu**

目标：在虚拟机中快速安装 Ubuntu。

(1)打开 VMWare Fusion，在菜单中选择 文件 | 新建...

(2)将步骤 1 下载的 ISO 文件拖拽到从光盘或映像中安装，如下图所示：

![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4PtLibqwjchpQXWPFtDEdgmdNRXqQxIkfoicVL7icthSHcuxEM1AbQHFzuKA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

(3)点击继续按钮，在 Linux 快捷安装界面，输入显示名称、账户名、密码及确认密码，并且勾选在虚拟机中访问个人文件夹，如下图所示：

![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4PtNFJ1xPXEyBobYhood6x95ch5W45GYKXGV60c6b37skcibc3ICOco5xw/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

勾选在虚拟机中访问个人文件夹，可以在个人电脑和虚拟机之间共享数据，包括：复制、粘贴等操作。



(4)点击继续，然后点击完成按钮，等待系统安装。

此时你可以去喝杯咖啡或者做点其他什么别的事情



**2.2认识 Ubuntu 界面**

目标：认识 Ubuntu 界面组成，知道最常规操作。

  **2.2.1退出新特性应用**

安装结束并重新启动后，输入之前设置的用户密码，可以登录进入 Ubuntu 的桌面并看到新特性应用的界面。

![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4PtIllan2Pckjt3E0avSia6EKTficjFEw7B9stvDwcb8wdicdU3AjvdUCsKQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

点击左上角的 Welcome to Ubuntu，然后选择 Quit 可以退出 Ubuntu 新特性，如下图所示：

![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4Ptjuoalw82hHiaVvPTLSgT5XbRMvekib3FR6xtLiaPXIk48pyaibSHibiaEoibg/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)



  **2.2.2Ubuntu 界面组成**

**界面组成**

Ubuntu 的图形界面由三部分组成：

❶桌面

❷任务栏

❸系统菜单栏

##### 系统菜单栏

❶最左边 Activities（活动） 点击可以查看当前正在运行的程序，或者搜索软件

❷中间显示当前的系统时间，点击可以显示日历

❸右侧的四个按钮，无论点击哪一个都可以显示系统设置菜单，以方便执行常用的系统设置操作，如下图所示：

![img](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)



##  

##  

3、系统设置

添加中文支持

设置系统时区

**3.1 添加中文支持**

目标：添加中文支持以显示中文界面。

(1)点击右上角，然后点击系统设置菜单中的系统设置按钮，打开设置程序

(2)选择 Region & Language，如下图所示：

![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4PtBowuU3eyQMt2aaSEujjRuf1Gibl2duK8hG3ib8DHMoYJO9ibrGzVXpeyA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

(3)点击 Manage Installed Languages（管理已安装的语言） ，会出现要求安装语言的窗口，如下图所示：

![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4PtCyDvic9Kt6MkZVgGJIKFBRC10CWotthP5SMfmyn8QMOJlYLuFlwlHaw/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

(4)点击 Install 按钮，会被提示输入密码，输入之后稍等片刻，会出现Language Support（语言支持）窗口，然后按下图步骤操作：

> a、点击 Install / Remove Language
>
> b、在 Installed Lanages 窗口中找到并勾选 Chinese(simplified) 简体中文
>
> c、 点击 Apply，会被提示输入密码，之后会自动下载简体中文相关的文件，最后会返回到 Language Support 窗口
>
> ![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4Ptn7z3ibdYvmnLdRLambKKX3dIh2oexVwuZJNfjyZwszlV36B3k9TAkpw/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)



(5)回到 Language Support 窗口后，按下图步骤操作：

> a、找到汉语(中国)，按住鼠标左键不放向上拖动
>
> b、拖动到所有其他语言的上方后放手
>
> c、点击 Close 按钮，关闭电脑，并重新启动系统
>
> 提示：修改语言后必须重新启动系统才能生效。
>
> ![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4Pt9YJP5PBy9xCWwEDNmMDg6UZmOckDITv3PkItqpQUlMtbxEYCZ19g2A/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)



(6)重启系统并登录后，出弹出一个窗口询问是否修改标准文件夹的名称，按下图步骤操作：

▲勾选不要再次询问我

▲点击保留旧的名称

提示：如果选择更改名称，会把 Desktop 修改为 桌面，这样不方便后续在终端中切换目录。

**![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4PtmWBmFUyuOjCiaJn9XxPjMkPgUKoI7SVzXFDc97zruE66jtw76YAXP1Q/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)**



**3.2 设置系统时区**

目标：设置系统时区以显示中国时间，并设置时间显示格式。

(1)点击右上角，然后点击系统设置菜单中的系统设置按钮，打开设置程序

(2)选择最下方的详细信息，然后选择日期和时间，如下图所示：

![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4PtHiaMBolgxBeunI7eibfqk7NUDWCy5gbU03W4EjSKZ2R44kibCGu0Scklw/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

(3)点击右侧的时区，然后在弹出的窗口中将系统时区设置为中国 上海（UTC+08），如下图所示：

![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4PtSneiaWHY1KnhAicvAytSdPHnyYj6J37MzDgAsoAzpC98ibHyibCL6iaahhQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)



(4)关闭时区选择窗口，点击详细信息左侧的返回按钮，选择区域和语言，然后将格式修改为中国，如下图所示：

![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4Pt3POy0wyqdRNg0EVIdAlkqL95U4Ha9ah5gYk6YwsVCqa7myibXEI2VZQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\4. 安装常用软件

##  

配置下载服务器

将终端添加至任务栏

软件更新

安装常用软件

卸载不使用的软件

**4.1 配置下载服务器**

目标：选择国内的软件下载服务器，以提高软件安装速度。

(1）点击系统菜单栏左上角的活动，在弹出的搜索框中输入 soft，然后选择软件和更新，如下图所示：

![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4PtM7B8VOdSJn2ibh5ibfAWnRpRkICeibVFohrj4KyZ2WKtwup94CukCTdUA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)



在软件和更新窗口，按下图步骤操作：

> a、点击下载自右侧的美国的服务器，然后选择其他站点...
>
> b、在弹出的选择下载服务器窗口中，点击选择最佳的服务器
>
> 提示：Ubuntu 会自动搜索速度最快的下载服务器，这个过程需要耐心等待几分钟
>
> ![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4PtKdPdUSUpevemjMqAdIXqjuluPoNvoPicoiaicR5BVh66pGuejP5uzyRtg/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)



(3)选择好下载服务器后，按下图步骤操作：

> a、点击选择服务器返回到软件和更新窗口
>
> b、点击关闭按钮，会弹出一个提示框，提示更改服务器后，必须重新载入可用软件包列表
>
> c、点击重新载入按钮，并稍等片刻，更新完成后会关闭窗口并返回到桌面

4.2 将终端添加至任务栏

目标：将常用的**终端图标**添加到任务栏，以方便日常使用。

按下图步骤操作：

▲在桌面的空白区域点击右键，然后在**右键菜单**中选择**打开终端**

▲在任务栏的**终端**图标上点击右键，然后在**右键菜单**中选择**添加到收藏夹**（也就是任务栏）

![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4PtJenWcVrPBQ9cJB8j8Sh9O60b2TWIvjZm6iaTxicXHwWtXDcUar5ib71Fw/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

  4.2.1 【扩展】调整终端字体大小

(1)**放大字体**：`CTRL + SHIFT + =` 也就是 `CTRL + 加号`

(2)**缩小字体**：`CTRL + 减号`

### 4.3 软件更新

目标：更新可用软件包列表并升级更新系统。

```

```

![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4PtXV6xygJTRlmD2xtl23HS1qTIqslLFGVXjrWVaM3AsEo9UJ6ibruhc0Q/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

####   4.3.1 apt

- `apt`（Advanced Packaging Tool），是 Ubuntu 下的**安装包管理工具**
- Ubuntu 中**很多**软件的**安装/更新/卸载**都是利用 `apt` 命令来实现的
- 在终端中输入 `apt` 可以查看帮助信息
- 除了 `update` 和 `upgrade` 之外，`apt` 的常用命令如下：

```

```

![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4Pt7XQdaicf156FicicKyjH6arzBtyWmBibFuyKeJ6wsDmxkhXM7hfYAicWIXw/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

####   4.3.2 【扩展】apt 和 apt-get

- `apt` 和 `apt-get` 都是 Ubuntu 下常用的安装软件的命令
- 早期使用 `apt-get`，从 Ununtu 16 开始，官方建议使用 `apt`

### 4.4 安装常用软件

> 目标：安装常用软件，此处仅列出几类，有其他需求的朋友可以根据实际情况自行上网搜索。

####   **4.4.1 常用工具**

![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4Pt4aicCXG97YWoicDPjpaIogvpYp7W9ENYEIxrvE0e6n1P1wR9kPD6f2IQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

####   **4.4.2 谷歌浏览器**



![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4Ptc5L6bd2AJOBst1zibBCTnDcZzC30OjjW4HE1vVVUiaicibn6OIfls8jJibQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

> 提示：启动之后，可以将**谷歌浏览器的图标**添加到任务栏，方便下次使用。

##### 【扩展】deb 安装格式

deb 是 Debian Linux 的安装格式，在 Ubuntu 中同样可以使用。使用 `dpkg` 可以安装 deb 安装包，格式如下：

![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4PtewBpEQFXMproKVJgLVBjFIqcWhz5ibdKC5zT7FqDyG9eSgvd9wg126g/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

####   **4.4.3 搜狗输入法**

访问 http://pinyin.sogou.com/linux/ 下载搜狗输入法的 deb 格式安装包，然后在终端输入以下命令：

![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4PtWT4XNz94AKNYAEFtregGUbB2iaCVLyIJKCjwdQxyEDjGn8ichPVWr9XQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

####   4.4.4 Python 工具

##### 命令行工具

![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4Pt6o8g7pf08TSKYXXuPeaTbnVzSfs6FLgNOuuUPmLnSR9U8gicCMicLfjg/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

##### PyCharm

访问 http://www.jetbrains.com/pycharm/ 下载 PyCharm 的安装包，然后在终端输入以下命令：

![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4PtRswepibya0IhmCtKXAcMDWicJEA0iaL2IXyta00WZeGoZvf8NxicvfCxkw/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

###### 将 PyCharm 图标添加到任务栏

> a、启动 PyCharm 后，选择菜单中的 **Tools** | **Create Desktop Entry...**，如下图所示：
>
> ![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4PtK5NiaKvbGqMD7DicdMX0v6FZWiaeSJUVA5kwicribvPeDM4JkcQROM5xWew/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
>
> b、在任务栏的 **PyCharm** 图标上点击右键，然后在**右键菜单**中选择**添加到收藏夹**（也就是任务栏）

###### 调整虚拟机配置

> 为保证 PyCharm 运行的更加流畅，需要调整一下虚拟机的设置：CPU和内容。
>
> a、**关闭虚拟机**（提示：虚拟机运行时无法修改）
>
> b、在 VMWare 的菜单中选择**虚拟机** | **设置**，然后选择**处理器和内存**
>
> c、如下图所示，修改虚拟机使用的**处理器数量**和**内存大小**
>
> ![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4PtNEy6KGfTicePkgd7Rrj5Lk4S67EIIAS14gNIpzp5yls97kb5vTUkruQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

####   4.4.5 Go

##### Go 1.11

![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4PtqG9KysIucuddbChCzwHf5cSEz4Bsia0684sLQxnGz2X3iblOn7aCD16g/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**GoLand**

访问 http://www.jetbrains.com/go/ 下载 GoLand 的安装包，然后在终端输入以下命令：

### ![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4PtxJqHWuc4u41so1bIlXPYt99r0NtYrxk8lCFeuyJOkvicMJd1ktIfEJg/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

> 提示：将 GoLand 图标添加到任务栏的方法与 PyCharm 基本一样，不再赘述。

### 4.5 卸载不使用的软件

### ![img](https://mmbiz.qpic.cn/mmbiz_png/OvnShhIvBxSBJErJsibNHmCAzicd1Gl4PtiaoXF4U2d977peZ8yblfPicICTxYVXjictNMJEgT0HXv0Y2HZuH97OGGg/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

小结



## 至此，您已经拥有了一个可用于 Python 或 Go 语言开发的 Ubuntu 虚拟机环境。 

本文共包含以下 4 部分内容：

(1)**准备工作**：准备 VMWare 虚拟机环境和 Ubuntu 的安装包

(2)**快速安装及认识界面**：

> 提示：安装时不要忘记勾选**在虚拟机中访问个人文件夹**，这样可以在**个人电脑**和**虚拟机**之间共享数据

(3)**系统设置**：添加中文支持，设置系统时区

> 提示：添加中文支持后，需要将中文拖动到所有语言的最上方，并重新启动才能生效

(4)**安装常用软件**：选择国内的镜像服务器，安装常用软件

1. 1. 选择国内的镜像服务器可以让软件的安装下载更加快速
    2. 介绍了一些常用软件的安装，另外还介绍了谷歌浏览器、搜狗输入法、PyCharm 和 Goland 的安装