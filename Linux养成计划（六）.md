Linux是一个**多用户多任务**的操作系统，任何需要使用系统资源的用户必须向系统管理员申请账号，以账号的身份进入系统。

非必需时尽量少用root用户登陆，因为它是系统的超级管理员，这里的系统管理员root和Windows中的administrator还不一样，Linux中的root才是绝对的管理员。root有最大的权限，所以非必需时尽量少用root用户登陆，避免操作错误，造成无法返回的后果。

Linux操作系统可以有很多用户，root 用户是最高管理员。除了用户之外还有组的概念，每个用户至少属于一个组。**根目录下有一个home目录，称为家目录，这个目录下有各个创建的对应的目录，当用户登陆时会自动进入自己的家目录****。**比如：有一个用户叫 tom，就会有 /home/tom 目录。

**添加用户**

语法：**useradd [选项] 用户名**  

如：输入命令： **useradd tom** 

**1.**  输入上方命令，没有指定tom在哪个组里，就会创建一个和tom同名的组，并且把tom放到了这个组里，后面详细讲解如何切换组等命令。

**2.**  **cd /home/** 命令，表示切换到 /home/目录，c：change，d：directory。接着输入 **ls** 命令，home目录中多了tom目录。

**3.** 通过 **useradd -d 指定目录 新的用户名**，给新创建的用户指定家目录，这里的**指定目录不要提前创建**，这点很重要，否则无法登陆新用户。

**4.** 使用 **passwd tom** 指定tom用户的密码

**5.** 命令 **useradd -g jujidi jack**  增加用户jack，直接指定到jujidi分组

**修改密码**

**passwd 用户名**  给用户指定或者修改密码，必须是root用户才有指定密码修改密码的权限。

**删除用户**

**userdel 用户名** 删除指定用户，必须是root用户才有删除用户的权限。

**1.** 删除用户 tom ，保留它的家目录

**userdel tom**  此时 /homt/tom 目录依然存在

**2.**  删除用户 tom ，以及它的家目录

**userdel -r tom**  此时 tom用户家目录也被删除

该不该保留家目录呢？

实际开发中是保留家目录的，就好像一个人离开但是他造成的影响以及他遗留的东西还在，所以删除用户时，尽量保留家目录。

**查询用户**

**id 用户名** 如：**id root** 查询 root 用户的信息，查询结果如下：

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWgwVhZzz6QBVXfJ0zVNReZec9rNyvYcLANVsdwmibiaQudua05icDaczrFjE3CKop5bTB1Gtk0QdXkbw/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

uid为用户的id号，gid为用户所在组的id号，它属于root组。

**whoami** 查看当前登陆用户

**切换用户**

操作Linux中，如果当前用户权限不够，我们可以通过 **su - 用户名**，切换到高权限的用户，比如：**su - root** 

**1.** 使用 **su - 用户名** 进行切换用户

**2.** 高权限到低权限用户切换时不需要输密码。

**3.** 普通用户无法进入 root 目录，权限不够。

**4.** 使用 **exit** 命令回到切换前的用户

**用户组详解**

用户组的概念类似于角色，系统可以**对****有共性的多个用户进行统一的管理**，比如公司中，你是研发组还是测试组，把职责相同的同事放到一个分组，方便管理。

创建组

- **groupadd 组名** 创建一个组

删除组

- **groupdel 组名** 删除一个组

增加用户指定组

- **useradd -g jujidi jack**  增加用户jack，并指定到jujidi分组   

![img](https://mmbiz.qpic.cn/mmbiz_jpg/e1jmIzRpwWj74dJicxibQlQexkp4knfe5szNGS6IadicLDSIEfzkcvCDQbkibibiaFLJyUO0nfmqdOZApZibnBNvdMYOg/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

修改组

- **usermod -g 用户组 用户名**
- 如：**usermod -g xiaozhan jack** 将用户jack分组修改为小詹

**用户配置文件**

对于用户而言，有一个用户配置文件：/etc/passwd，用户信息就会放到这个文件：

命令：**vim /etc/passwd** 查看文件

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWj74dJicxibQlQexkp4knfe5s7tRxWfdFy28mJibh9GBrsPzVMOazgdxz2ykognMCo3OibEylia3wNLogQ/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

解释：

tom：x：1002：1002：：/home/tom：/bin/bash

- tom:用户名
- x：密码，加密的
- 1002：用户id
- 1002：用户所在组id
- /home/tom：用户的家目录
- /bin/bash用户对应的shell

**组配置文件**

对于分组而已，有一个分组配置文件：/etc/group，分组 的信息就会放到这个文件：

命令: **vim /etc/group** 查看文件:

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWj74dJicxibQlQexkp4knfe5sYYC2VHlh79SKiaLBb8xOv7oLwDxXs2pVB6JReg2FvXv7PXWK69shQsQ/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

解释：

jujidi：x：1002

- jujidi：组名
- x：密码，加密放在shadow文件
- 1002：组的id号

**口令配置文件**

密码和登陆的相关信息也会存储在一个文件里，口令配置文件：/etc/shadow，这个文件是加密的：

命令：**vim /etc/shadow**  查看文件

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWj74dJicxibQlQexkp4knfe5sKvjXibiclE1s2htVrdYUT2SibuiblZvzn7Z966jFyw2JwuoB5PPNIfFVQw/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

密码和登陆的相关信息都会存储在shadow文件里，可以看出是加密保存的。