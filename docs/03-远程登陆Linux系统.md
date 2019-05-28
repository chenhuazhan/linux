**远程登陆**

既然在虚拟机上面安装了CentOS操作系统，直接在虚拟机操作不就可以，为什么还需要远程登陆呢？在公司中每个程序员都有一个电脑，但是我们需要操作的Linux服务器不是安装在自己电脑上，而是放在机房里。

结合实际开发，Linux服务器时开发小组共享的，正式上线的项目运行在公网上，因此需要开发者用远程登陆到Linux进行项目的管理和开发。这个时候，我们就需要安装XShell软件进行远程登陆并操作Linux。除了XShell软件外还有一款软件用来远程上传下载文件：XFtp。

**下载软件**

Xshell是目前最好的远程登陆到Linux操作的软件，速度流畅，完美解决中文乱码等问题，我们可以在Windows平台安装Xshell来操作Linux：

http://www.netsarang.com/download/free_license.html「复制浏览器打开」



打开上方网站：点击Download

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjuasrNIuMvySHliaEyHDYokChwbDia2icgKuyFzRTP0TIfGB6GaMuNIclicwXDyfF1jfVWbvNwjlzDOg/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

填写相关信息，尤其是邮箱

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjuasrNIuMvySHliaEyHDYok4YYI8H3WucBq5ucOics8yRBJHPlrGCcd8TGF0e29Updb9hjgINm9bqQ/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

打开邮箱，点击链接即可下载家庭&学校版

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjuasrNIuMvySHliaEyHDYokKXtP6EGxQCMKrdXKB1Prjk3jUdymhy9QTlD4sa7wFRWN0Zg8JmNjZw/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**启动sshd服务**

安装Xshell非常简单，只需要一直点击下一步即可，在远程链接Linux之前我们需要确定Linux系统是否开启sshd服务，此服务用来监听22号端口。这样才可以通过Xshell连接到Linux，怎么查看是否开启了此服务？

**1.** setup命令->输入密码：

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWiaeBrCjxxkbjE2PxKWR32ngpZWBVNULMYWR7qhO4GialCUl5a28iaqrIsjTMu1ZDuFu2ic96ddN9IA6g/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**2.** 系统服务

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWiaeBrCjxxkbjE2PxKWR32ngalrFOKH7ibRz51pa7icWYP6Pib3ndQFH68O5eZt6rlzR7F99LtVhPfIog/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**3.** 下翻找到sshd服务，前面带星号说明是开启状态

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWiaeBrCjxxkbjE2PxKWR32ngVWut53ic5Q7BAveEwyw1P4ia2iaFCoIBzZLsiaz5eQY5UyUIWWib6ZnY3XA/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)



**XShell的配置**

**1.** 点击新建:

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjuasrNIuMvySHliaEyHDYok7tYbqm9ia2OazEtGQ7ia2g9WBT6ALPuPX57GibTqK8LTicraNiby8rVJRMg/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**2.** 回到Linux，键入：**ifconfig** 查看IP地址为：192.168.144.129

![img](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

注：查看ip地址时一定保证有网络，即右上角红色箭头图标存在，否则查不到

**3.** 回到Xshell，主机填写Linux的IP地址

![img](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

**4.** 接受并保存

![img](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)**5.** 输入用户名：root

 ![img](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

**6.** 输入Linux系统root用户的密码

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjuasrNIuMvySHliaEyHDYokqMNXHMFrau2CZK8AEicX4UDdFsLIp5XqrmAEsDmASJkeQrgGDTAhRcw/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**7.** 登陆成功

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjuasrNIuMvySHliaEyHDYok4ibxWgcTo54tOib0Q361Uib51AGNg98IPb08B1KTxUzffibcslwibColfbQ/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**8.** 修改样式

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjuasrNIuMvySHliaEyHDYoklcuF2RxcBibjXLF0xJsKHEl4uRs0yJ2MH7KiblicE1ByCOYRZVjovu70A/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**XFtp的配置**

Xftp的下载方式同Xshell，同样xftp的安装也是非常简单， 点击下一步即可，安装后进行配置：

**1.** 新建

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjuasrNIuMvySHliaEyHDYokk0T3uHSKhJKpQIerT1qKrhrD3Xz6xT7n0ic4spFwAOGicytMdX0Rp0Wg/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**2.** 填入相应参数

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjuasrNIuMvySHliaEyHDYokZXO1iaoavb4Il8zjjolc7iaHWSPRH6pIMJwQOxsCvYiaLe7AISdUztxJQ/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**3.** 输入密码

![img](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

**4.** 链接成功

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjuasrNIuMvySHliaEyHDYokU1Euoun9sdTW1FCB9MblB8l8auwbGzt8P2YKK8mdcHf2C7b89VPzMA/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

注：你用什么用户登陆，会自动登陆到此用户的home目录，这里直接是/root目录。

**解决乱码问题：**

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjuasrNIuMvySHliaEyHDYok1ZiapevEl7LM10Jb1NuCibUuNicc5GibCgzZFjlicJg4cDlP3mRyLXVxsQA/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**上传文件：**

**1.** 左侧Windows文件拖到Linux目录中

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjuasrNIuMvySHliaEyHDYokqnNnfL9o90cScx8KTWP9Dv0LEQcI24ib052cxicJEuNNNm1iciaSWfWnbg/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**2.** 成功！

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjuasrNIuMvySHliaEyHDYokp9ONibsOmgTibfg93xA2B1hDrIOkyA6wQHLJQ7poic7a9muniaGUucSEZw/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

