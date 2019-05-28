**运行级别**

运行级别就是操作系统**当前正在运行**的功能级别。级别是从0到6，具有不同的功能。这些级别定义在 /ect/inittab 文件中，也可以打开此文件查看和修改当前的运行级别（最末尾）。这个文件是init程序寻找的主要文件，最先运行的服务是那些放在/etc/rc.d目录下的文件。

运行级别：

- 0  关机
- 1  单用户 
- 2  不完全多用户，无网络服务
- 3  多用户，有网络服务
- 4  未分配
- 5  图形界面
- 6  重启

切换运行级别：**init [0123456]**

如:我们在图形界面下打开终端输入： **init 3** ，通过init 来切换到了多用户无网络服务的级别，并且没有图形界面只有命令行，再输入 **init 5** ，回到了图形界面。

**问题**

如果我们忘记了root密码，怎么找回？

思路：**进入单用户模式，单用户模式下修改root密码。**因为进入单用户模式，root不需要输入密码就可以登陆。

\1. 启动CentOS

\2. 进入到下方时，按Enter键

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWj74dJicxibQlQexkp4knfe5sXOuthxSNgBBIblLmPuwO4JgSS3lzzB1NiccNdOUS9eJzOpIv3tnjwsw/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\3. 进入下方界面，输入 **e** 编辑命令

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWiawb0KNf8jzzro8E5ZHAByeNr8Dz1I92Eeqdib4xUchiaod2cctibvldCIoZT9ULVgjfMPZnVae31erQ/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\4. 进入下方页面，把高亮跳的第二行，再输入 **e** 

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWiawb0KNf8jzzro8E5ZHAByeOU4wd4cYHeQfm2ctdDBXsRN0sQ0icFpY4WZWR4n7dAld9CqAOkWnFpw/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\5. 进入下方界面，按一下**空格**和 **1**

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWiawb0KNf8jzzro8E5ZHAByeIPmBicrEIMVKSez1o9xsVHCZQ96Lo9eP9I4e03LXf0diaSLerVkopgXw/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

注：1就是让我们进入单用户模式，即第二个运行级别

\6. 输入Enter 键盘，进入下方界面

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWiawb0KNf8jzzro8E5ZHAByeUV9vbWEb40OquToAIO4ibABRFWicrFicSrianjXY67x6bZ9xEjn7HOFkpg/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\7. 输入 **b** 开始启动，会以root身份进入单用户模式

\8. 输入 **passwd root** 命令

\9. 输入新的 root 密码

\10. 完成修改密码，重启即可

**安全问题**

问题来了，这样不就是谁都可以修改此系统的密码了吗？为什么还说Linux操作系统比较安全？

答：如果想通过上方方式修改密码是不可以通过远程操作的，也就是说必须在Linux操作系统上进行操作，即实际公司中进入机房操作。

既然你有能进入机房修改密码的权力，就可默认为你是Linux的主人，修改密码还不行？总之，想修改Linux系统的密码，主机得在你旁边，所以任何人都可以修改系统密码不成立。