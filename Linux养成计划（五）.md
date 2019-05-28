**系统的关机和重启**

**shutdown**

- shutdown -h now ：立即关机
- shutdown -h 1：1分钟后关机
- shutdown -r now：立即重启

**halt**

直接使用，键入命令关机

**reboo****t**

键入此命令来**重启系统**

**sync**

内存数据同步到磁盘，**关机前应使用此命令，把内存中的数据写到磁盘中，防止数据丢失。**

**用户的登陆和注销**

非必需时尽量少用root用户登陆，因为它是系统的超级管理员，这里的系统管理员root和Windows中的administrator还不一样，Linux中的root才是绝对的管理员。root有最大的权限，避免操作错误，照成无法返回的后果，这里我想到了一个段子：

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjznYvGcMDdI9dnLLKibo4wiacg9YShcuELbPw9pDEVurhsQsexAh40a2ick0UeB0Ve4TRjYSZSAxwcw/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjznYvGcMDdI9dnLLKibo4wiaTIKnzwxChQyqD3uQUQDlSibpzMRwe3yDzMAN0Bws8WpGNLHy2Uftwwg/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

经常会在IT交流群可以看到，在用户询问命令相关的问题时，个别想整恶作剧的朋友会回答执行  **rm -rf /\*** 这个命令就行了 ，若不了解这个命令，可能导致整个Linux系统文件全部被删除。

这个删除命令只有 root 权限的帐号才可以执行，其它未取得 root 权限的帐户只能删除属于自己用户或用户组内的文件。

![img](https://mmbiz.qpic.cn/mmbiz_jpg/e1jmIzRpwWgwVhZzz6QBVXfJ0zVNReZejJSq0KGzlAnaaIPDE5TbXK0Aldu6ACa8eZuECxSP1ianMNISdayur6w/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

Linux的目录是使用 **/** 之类的目录形式存放，**rm  是Linux的删除命令**，后面带的 **-rf** ，**-r** 指的是 递归删除（意思是删除当前目录下所有文件和文件夹），而 **-f** 指的是 强制删除 。后方的 /* 指的是 根目录" / "下的所有文件。

那么，如果在 / 目录下执行 强制递归删除，命令就会在无任何提示下将/下包括/home 、 /sbin等所有系统目录均删除掉。

请不要随意执行  **rm -rf** **/\*** 命令，否则会导致整个Linux系统被删除。

**建议**

因此为了避免操作失误，可以利用普通用户登陆在使用 "**su - 用户名**" 命令切换成系统管理员身份进行重要操作，然后退回普通用户。同样可利用**logout**来注销用户,使用的是图形界面**logou**t是无法注销root的只会退出终端。





参考：http://www.kwx.gd/VpsPrimary/CentOS-rm-rf.html