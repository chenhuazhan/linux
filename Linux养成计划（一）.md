**Linux系统安装及网络配置**

这篇文章介绍关于Linux系统的安装以及网络配置，关于虚拟机配置中网络的三个模式区别进行详细讲解。学习Linux对于后端开发人员是很有必要的，结合实际开发，Linux服务器是开发小组共享的，正式上线的项目运行在公网上，因此需要开发者用远程登陆到Linux进行项目的管理和开发。

如果你想在计算机行业深入下去建议去系统学习，因为Windows隐藏了太多的操作系统细节，通过学习linux你会开阔很多眼界，而且就java本身而言，它也更适合linux，因为绝大多数的Java服务器都是linux的。

![img](https://mmbiz.qpic.cn/mmbiz_jpg/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8ECDVNmNNpqZIXDW3EMKYYqEkLwCsAQsDiab4sdicSZEAkic7QAsHY5wkw/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

同样作为学习使用，我们建议安装虚拟机，我们这里选择VMware软件，虚拟机可以使你在一台机器上同时运行多个操作系统。

VWare 是一个“虚拟PC”软件公司.它的产品可以使你在一台机器上同时运行二个或更多Windows、DOS、LINUX系统。安装在VMware操作系统性能上比直接安装在硬盘上的系统低不少，因此，比较适合学习和测试。

![img](https://mmbiz.qpic.cn/mmbiz_jpg/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8JcKibH3WhH2YmO3xcXVUhlnkyaicJ2pzU8qRKiaqe165LFcS8978LhYjQ/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**Linux,VM和Windows的关系：**

VM就是一款软件，安装在我们的母机上（Windows），它可以帮我们虚拟一个操作系统出来。首先通过VM来创建一个虚拟机空间。在虚拟机空间里安装CentOS。

安装后的CentOS系统就是一系列的文件，同样可以把装好后的"一系列文件"移植到别的操作系统上。别的操作系统也必须使用Vm打开，这种移植对测试服务器的压力等非常有帮助。Centos是linux系统的一个发行版本。

**安装CentOS 7：**

关于VMware的安装这里不再介绍，直接点击下一步就可以了。VM软件可以参考历史链接：[连接虚拟机数据库](http://mp.weixin.qq.com/s?__biz=MzUzODcwMDIzOQ==&mid=2247484359&idx=1&sn=405d2d0e7198b63c66e3c79a27c16a7a&chksm=fad2f367cda57a71fba3a0ddd4f518b1b970762a8cc1ceeb4dacad72af4df3a6161eb8a5550f&scene=21#wechat_redirect) 来获取安装包，本教材使用CentOS 7发行版本，下载链接：http://mirrors.163.com/centos/7/isos/x86_64/ ，CentOS 是Linux操作系统的一个发行版本。

1. 打开虚拟机

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8c581icMzHDKwKLMBmsrM2iauD1miaMSTQNRFgrKgL1icqjAUIE7UDxnD3w/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\2. 新建虚拟机，选择典型

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8PbUSmfOQ1GXgw1tqQZSrUrrW6uZxSjLegFDnRuw1Eac9BbiaicNJHDEw/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\3. 选择：稍后安装操作系统

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8Hlm1VR5OLq0CE6XZmcmHPymokC3FfueRFdOEeXRnxFkd828xKmQJ9w/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\4. 选择Linux，版本选择CentOS 64位

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8qdtOap1WfPazndKRAcKTJ8PJJJFQIbv61ZxjibibKnQfiaibJKTlVoibVXQ/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\5. 修改虚拟机名称（任意），虚拟机保存位置

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia86FTryu1IEAhF1avlicLs44LZEqQ23AYckPzjibEWaWonNPp86yGQIpqA/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\6. 指定磁盘容量大小，建议不少于20G。这里分配不是立马吃掉20G，可以根据设置，随着使用慢慢增加到20G。

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8pIdkeCkc76iaQUibGePUmLuFnxia4Z3icmaCDDu0Q1xBYLIQBTEX2FcBibQ/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\7. 完成

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8QmLngtib5JVQMaBfiaJQXqeludKh14UGQAUsWx8R1jrIkGa4CRNn1OXA/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\8. 红色箭头位虚拟机配置

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8CdAI56MPvxicjtnsgeRuae3TFo2mrMtDSHJOgsysQqXnFCuIZtWf5YQ/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\9. 点击编辑虚拟机设置->内存，根据Windows的内存进行适当调高。小编内存是8G，所以虚拟机选择了3G。

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8y6X0pfyuFPsnpAKTSjVib9YhEfZiax90BBwR7qwV0vYvjlweiceFE66Lw/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\10. 选择处理器->更改处理器数量和核数，母鸡的核数配置可以在任务管理器中查看

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8F1lh98DIzia44oQ5Uk1XHibSx69XypUpjqEOibDPQPjjuy3U2vrK1vXRA/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\11. 网络适配器：NAT模式

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8EqxiaXRica9XibtxT0EATUOjC40BRxAyibrkdiaXvKQibiat8GLtzm9icW6c3g/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

关于上方的网络适配器的配置中，**我们为什么选择NAT模式，它和另外的模式有什么区别**，这里详细讲解：

**桥接模式：**

我们假设有一个教室的网络环境，里面有一台小白的电脑：windows操作系统，IP地址为：192.168.0.**10**；在这个教室中还有另外一个人小黑的电脑windows，192.168.0.**20**，他们可以相互通信。 

小黑的Windows装了一个VM虚拟机，并且安装了CentOS系统，网络设置选择了：**桥接模式**，那么安装的CentOS系统的ip地址也是192.168.0.xx。

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8T23SssAWAfCjRa5Lxm70xRZUCZCXh3DuPib9HibRVW73yTESPRsONyQA/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

小白的电脑可以与小黑的电脑通信，小白的电脑还可以与小黑安装的CentOS虚拟机进行通信。

这样固然好，但是我们学习过网络原理的知识明白，192.168.0.xx网段可分配的地址只有200多个，如果网络环境中主机很多，可能会造成ip地址冲突，所以我们不选择桥接模式。

**NAT模式（建议）：**

Linux可以访问外网，不会造成IP冲突。

假设教室网络环境中又多了一个小绿的主机，它在主机上装了CentOS的操作系统，网络配置选择的NAT模式。

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8rysQCia60AC6S0CRKryRTgaQfJd4jkIbKoZATibibicGEs0ZnDWG8PRV7g/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

采用NAT模式后，安装虚拟机的Windows会增加一个ip地址，192.168.100.200。

192.168.100.200和192.168.100.50可以通信，这样小绿的电脑有了两个ip地址，采用NAT模式的话，小绿创建的虚拟机的ip地址不会占用192.168.0.xx这个网段。

这种方式不会出现ip冲突，但是小黑小白是无法和小绿安装的CentOS通信的。但是小绿安装的运用NAT模式的CentOS可以和公网（即：小白和小黑的电脑）通信（小绿另一个ip地址代理）。

**仅主机模式：**

虚拟机CentOS是一个独立的主机，不可以访问外网。

\12. 综上，我们选择：NAT模式

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8EqxiaXRica9XibtxT0EATUOjC40BRxAyibrkdiaXvKQibiat8GLtzm9icW6c3g/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\13. 点击虚拟机-设置

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8xFSdnkDPsNGRQibW6wsJwQvMzUdKibEX3vffNBIFPlRbR1icheTw8iaSDg/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\13. CD/DVD（IDE）->使用ISO镜像文件，选中我们下载的CentOS 7 的镜像

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8PMKaKj3LL5MyEiaQyJCdJXfhm3pV2tWHTDibXCuPRLS35FheHFyMy4YQ/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\14. 配置完成点击开启此虚拟机

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8ibtGj5JC06XZnDAUdibjghwTRHr689A9Y0lm0giaGicK5aHibuclbicU1oUQ/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\15. 打开虚拟机的过程**可能**出现下方的选择，一定选择Skip（Tab建切换）

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8Hor11PAxzU6ibhmUaHa6NmdyiaZgGlEXGPnF3kuKVhtZOPV5Cibrl22qg/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\16. 选择语言：中文

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8TLgN8ONkCF7ia1wVBrFvftNlqXeoc8r7iaQ5Q5PnziaV61kibejMVEgaLw/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\17. 这里需要等半分钟，等待加载完毕后：选择安装位置进行配置

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWhgvOnawwnWOicfymGibslSz7JqhOlbGEbWzkKUjkK2PQ4HibuiaGO20d24pQKKiaXBA1mZORUF1wY1zgw/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\18. 选择：我要配置分区

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8A1JMysiaXz3UO63WEmds7122liaMY3EQ3Y58SYwNyQf9GszZIKuypWCw/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\19. 选择标准分区

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8SFLcyUqKgvGPyntXjheoAtZibHol1ZdYQAIdib98XZbbulo4OUjG2tcg/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\20. 点击"+"号，增加下方的挂载点：/boot ，把容量设置为200 

  /boot：引导分区，Centos启动时的引导文件

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia83ohZibeydhDdiba99DfZliajYc4Wqqx38gibG7H5Jk4r4wicK0HicYY0PyOw/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\21. 再添加一个设置：swap ，期望容量：2048

swap:交换分区，用于系统内存不够用，可用swap暂时的替代系统内存，分配内存的1.5倍-2倍之间。

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8PoibdlrLlNkaPDDibXAsia1FbchA7gal7o3MDGsyljnuiaF8BNWvmQbKGw/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\22. 添加一个分区：/  根分区 ，期望容量不设置，其余的放在根分区。

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8G2gtCvEq3T9bVNye2YVGfZoJlbPAMhK2B1kEtgGdIjJEBCzE5ytW7g/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\23.  分区完成就应该是下方红框中->完成

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8NDu3ZuMoEMWlxzfL1Z86Pw9l4KR9yrkOBQL3uO3LXKOibnJyQS9dVEg/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\24. 接受更改

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8iay3PV7kiberVfpfXaPyhSOorUicwNajicmcvbgWaNvjz3ewknmwPk0yaQ/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\25. 软件选择

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8I6gGTTjicPufNTaKvjPicpZLmqib1dic9iaISbnDTOAs6ViarkibMRqCDHFjg/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\26. 基础设备服务器->兼容性程序库

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8HKZibiaUcG0lmZJagOfPFU9icEaKibtrLdia1ZiaS9MEL5dwFO91tOIEWarQ/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\27. GNOME桌面->把用不到的办公套件取消掉。根据下图勾选上需要用到的选项

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8EPdFXwaMrrR2ibSPH1vrxcRNOGcRj8icCBtZD8dP0XVYkmuyXgFibfK9w/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\28. 选择网络和主机名

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8BOccnKMKYJRicsWnuBWeicshibq5GO3gCcKxScaBBPwxaMIvvB7Z5H7icw/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\29. 图中红框更改主机名

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8yczYlEfK6RttODIuVOibBFIETI4ASIVgUxiavd23XTKnICDyUiaibY1V8g/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\30. ROOT密码：点击设置自己的密码。

ROOT密码：生成环境不能太简单，生成复杂密码。

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia84pCsgd21Ssmd1xTsoqyrHUfvbT50yTWhicaHcd85pJ2Tgb6StujQxbg/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\31. 接下来就是漫长的等待过程：重启，然后就是下图。点击LICENSE .....

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia89JnPpJNQXia1j221poX3blH4srFDG2L9I4wqtLtk9jDAugPfQaibFodw/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\32. 勾选我同意许可

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8DLbvn8fzxDzaFGC4JylxVJqQzbXK5nF3uRCYOamrmnXoOicotPRQMIg/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\33. 中文

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8rCxOmCziaWTHaxc3mFAYkTao004AX0Z57Nv65fGic0ds6mXZM8dSwrlA/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\34. 汉语

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8sFXI9o5ibzU9IjRmIAicdFbpEWpSTGZagj0cNcibo3vkV4pDibCBqGzwQQ/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\35. 可选可不选

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8SL88fCS3ZlmYjGg5m1HnFUGFGdcpVHvv2ibDOHgpcYXpLias4COsbQHA/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\36. 设置时区

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8FKSBicsHeeYiajGZd2qzQ63DPDKNoM1Kx73ZjOBvYpAEmQWG2PcFnjEw/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\37. 可登陆可不登陆

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8OnugAAlQRiboZXF3hVgglGC4mnKvlhchxNAgibx39T216BAY2ia7NLJHA/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\38. 全名，用户名

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8GnNDpAPy65faznvW9jFjsaLlB0dWdZZhx5PVjnj9SSmL6R8JRPxtLQ/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\39. 设置密码

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8CFPbTmM2qP6xFhpXibvG8evzoHBSjicCzzDp2azLicheVmrYvr9a5EyxA/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\40. 完成安装

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8rW03uJlvzyz1bCJEKPTTe2HN23T628vxWuJ4vibqrCqSrLqlJE0iaUyQ/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)



**网络设置**

这时候打开浏览器，是连不上网的，我们需要网络设置。

**![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8OlKT4ReR5dQ5ezmpcZXCtKBJlIFwJmkb9QC2kTicibxmcpH3WuBPRO3g/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)**

\41.  右键屏幕：打开终端

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia86WufJqzuzhsVbKdt2mzN6Kib3UG0lFlEqBKH36IazKM7doFgvDgIHfw/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\42. 键入：**su root**  然后 输入密码，注意密码是不会回显的

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8lEHxaSf57g236OjtJE7tTKH2wCjAPRrqDNrpOdicXvrhcYPRicEFyUFg/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\43. 输入**cd /etc/sysconfig/network-scripts/**

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8KPnP7alMczPZib25pObJAMrsgFAGb43cdtUU6x5mNjsb0Yrwq3fjNng/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\44. 输入命令 ： **ls** 查看文件，找到文件**ifcfg-ens33**（你们可能不一样，只要是 ifcfg-ensxx就可以）

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia84o2r1rulDK7eum7tvjZee7iaPkPGfeCKfXCIBHia4yleRwmlOudmVQKw/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\45. 输入命令  **vi ifcfg-ens33**

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8nn0VxcBwhNryLfYvpHMHS7WhyxMaMU9vx5CCtmhJ2W8zqqZ23ibwyww/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\46. 先输入 **i**  进入编辑模式，找到ONBOOT=no

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8Lsz71SFevicLnnFadlG1WbFuFZnFCbQxMX22FMSqO2abdsZtHx6E8KA/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\47. 把 ONBOOT=no 修改为 ONBOOT=yes

然后ESC退出编辑模式，输入 **：wq！** 回车完成保存

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8Z7kq1OVJL0XnaC5tzQR7yBXOOiazAWZKUQAtibiaZJn5TN4tlB1KpwFsQ/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\48. 重新启动CentOS，就可以上网了。

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia80D8PnezZbuFnYaiaJBicHkDUicsW8vojG60cvgiaq4yNd3PzibHNXlhWgfw/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\49. 这个时候务必保存一下快照。

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWjyQad62A8pd4jt4H2FEeia8XoPjPKcP7NJNXSeaqmUNFjR2C8r9vCE5ziawuuHSt8d4I6TdysrR6Sg/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)