Linux是一个**多用户多任务**的操作系统，任何需要使用系统资源的用户必须向系统管理员申请账号，以账号的身份进入系统。

非必需时尽量少用root用户登陆，因为它是系统的超级管理员，这里的系统管理员root和Windows中的administrator还不一样，Linux中的root才是绝对的管理员。root有最大的权限，所以非必需时尽量少用root用户登陆，避免操作错误，造成无法返回的后果。

Linux操作系统可以有很多用户，root 用户是最高管理员。除了用户之外还有组的概念，每个用户至少属于一个组。**根目录下有一个home目录，称为家目录，这个目录下有各个创建的对应的目录，当用户登陆时会自动进入自己的家目录****。**比如：有一个用户叫 tom，就会有 /home/tom 目录。



## 1  创建/删除用户/用户组

useradd [-u UID] [-g 初始群组] [-G 次要群组] [-c 说明栏] [-d 家目录绝对路径] [-s shell] 使用者账号名

```bash
-M  不建立用户家目录！(系统账号默认值)
-m  建立用户家目录！(一般账号默认值)
-r  建立一个系统的账号，这个账号的 UID 会有限制 
-e  账号失效日期，格式为『YYYY-MM-DD』
-D  查看useradd的各项默认值
```



useradd username：没有指定用户在哪个组里，就会创建一个和用户名同名的组，并且把用户放到了这个组里，后面详细讲解如何切换组等命令。通过 **useradd -d 指定目录 新的用户名**，给新创建的用户指定家目录，这里的**指定目录不要提前创建**，这点很重要，否则无法登陆新用户。

useradd -g groupname username： 增加用户到指定分组

userdel username：删除指定用户，保留它的家目录，必须是root用户才有删除用户的权限。

userdel -r username：删除指定用户以及它的家目录。实际开发中是保留家目录的，就好像一个人离开但是他造成的影响以及他遗留的东西还在，所以删除用户时，尽量保留家目录。

usermod -g groupname  username：修改用户所在用户组



用户组详解

用户组的概念类似于角色，系统可以**对****有共性的多个用户进行统一的管理**，比如公司中，你是研发组还是测试组，把职责相同的同事放到一个分组，方便管理。

groupadd [-g gid] 组名 | 添加组

```bash
-g  设定添加组的特定组id
```

groupdel [groupname] | 删除群组

groupadd groupname

groupdel groupname

groupmod [-g gid] [-n group_name] 群组名 | 修改组信息

```bash
-g  修改既有的 GID 数字
-n  修改既有的组名
```



gpasswd | 群组管理员功能

```bash
root管理员动作：
   -gpasswd groupname 设定密码
   -gpasswd [-A user1,...] [-M user3,...] groupname
       -A  将 groupname 的主控权交由后面的使用者管理(该群组的管理员)
       -M  将某些账号加入这个群组当中
   -gpasswd [-r] groupname
       -r  将 groupname 的密码移除
群组管理员动作：
   - gpasswd [-ad] user groupname 
       -a  将某位使用者加入到 groupname 这个群组当中
       -d  将某位使用者移除出 groupname 这个群组当中
```

chfn修改个人信息



## 2  查询用户



users：显示当前登录系统的用户名

whoami：查看当前登陆用户名

who 登录在本机的用户与来源

```bash
-H或--heading 　显示各栏位的标题信息列。
```

`who` - 显示当前已注册到系统的所有用户名、所用终端名和注册到系统的时间

w：登录在本机的用户及其运行的程序

```bash
-s 　使用简洁格式列表，不显示用户登入时间，终端机阶段作业和程序所耗费的CPU时间。
-h 　不显示各栏位的标题信息列。
```

finger [选项] [使用者] [用户@主机] | 查看用户信息



```
-s 显示用户的注册名、实际姓名、终端名称、写状态、停滞时间、登录时间等信息
-l 除了用-s选项显示的信息外，还显示用户主目录、登录shell、邮件状态等信息，以及用户主目录下的.plan、.project和.forward文件的内容。
-p 除了不显示.plan文件和.project文件以外，与-l选项相同
```

id [username] | 查看用户相关的id信息，还可以用来判断用户是否存在

id username：如：**id root** 查询 root 用户的信息，uid为用户的id号，gid为用户所在组的id号，它属于root组。



用户配置文件：对于用户而言，有一个用户配置文件：/etc/passwd，用户信息就会放到这个文件

配置文件选项解析：

tom：x：1002：1002：：/home/tom：/bin/bash

- tom:用户名
- x：密码，加密的
- 1002：用户id
- 1002：用户所在组id
- /home/tom：用户的家目录
- /bin/bash用户对应的shell

组配置文件：对于分组而已，有一个分组配置文件：/etc/group，分组 的信息就会放到这个文件：

配置文件选项解释：

jujidi：x：1002

- jujidi：组名
- x：密码，加密放在shadow文件
- 1002：组的id号



口令配置文件：密码和登陆的相关信息也会存储在一个文件里，口令配置文件：/etc/shadow，这个文件是加密的

groups 查看登陆用户支持的群组， 第一个输出的群组为有效群组

newgrp 切换有效群组

## 3  切换运行等级

`init [OPTIONS...] {COMMAND}`



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

## 4  关机/重启

关机

+ `halt`  直接使用，键入命令关机

- `shutdown -h <time>`
    - shutdown -h now ：立即关机
    - shutdown -h 1：1分钟后关机
    - shutdown -r now：立即重启
- `poweroff`
- `init 0`



重启

+ `reboot`

- `shutdown -r <time>`
- `init 6`



退出

+ ``

    




**sync**

内存数据同步到磁盘，**关机前应使用此命令，把内存中的数据写到磁盘中，防止数据丢失。**





## 登陆和注销

`logout` 注销当前用户

切换用户：su [user]切换到其他用户，但是不切换环境变量，su - [user]则是完整的切换到新的用户环境。su不加参数默认切换到root

切换到root用户需要输入root用户密码，普通用户无法进入 root 目录，权限不够。

高权限到低权限用户切换时不需要输密码。root用户切换到普通用户不需要密码

使用 **exit** 命令回到切换前的用户，如果已回到最初用户，按exit 退出当前shell 

## 修改密码：passwd

passwd：修改当前用户密码

```bash
-l  使密码失效
-u  与-l相对，用户解锁
-S  列出登陆用户passwd文件内的相关参数
-n  后面接天数，shadow 的第 4 字段，多久不可修改密码天数
-x  后面接天数，shadow 的第 5 字段，多久内必须要更动密码
-w  后面接天数，shadow 的第 6 字段，密码过期前的警告天数
-i  后面接『日期』，shadow 的第 7 字段，密码失效日期
使用管道刘设置密码：echo "zeng" | passwd --stdin zenghao
```

chage [-ldEImMW] 账号名 | 修改用户密码的相关属性

```bash
-l  列出该账号的详细密码参数；
-d  后面接日期，修改 shadow 第三字段(最近一次更改密码的日期)，格式YYYY-MM-DD
-E  后面接日期，修改 shadow 第八字段(账号失效日)，格式 YYYY-MM-DD
-I  后面接天数，修改 shadow 第七字段(密码失效日期)
-m  后面接天数，修改 shadow 第四字段(密码最短保留天数)
-M  后面接天数，修改 shadow 第五字段(密码多久需要进行变更)
-W  后面接天数，修改 shadow 第六字段(密码过期前警告日期)
```



### 重置root密码

```bash
sudo passwd root
# 输入当前用户密码
# 密码已更新
```



## 查询用户登陆记录

last 查看用户的登陆日志

lastlog 查看每个用户最后的登陆时间



## 修改用户的相关属性

usermod [-cdegGlsuLU] username | 修改用户的相关属性

```bash
-c  后面接账号的说明，即 /etc/passwd 第五栏的说明栏，可以加入一些账号的说明。
-d  后面接账号的家目录，即修改 /etc/passwd 的第六栏；
-e  后面接日期，格式是 YYYY-MM-DD 也就是在 /etc/shadow 内的第八个字段数据啦！
-f  后面接天数为 shadow 的第七字段。
-g  后面接初始群组，修改 /etc/passwd 的第四个字段，亦即是GID的字段！
-G  后面接次要群组，修改这个使用者能够支持的群组
-l  后面接账号名称。亦即是修改账号名称， /etc/passwd 的第一栏！
-s  后面接 Shell 的实际档案，例如 /bin/bash 或 /bin/csh 等等。
-u  后面接 UID 数字啦！即 /etc/passwd 第三栏的资料；
-L  冻结密码
-U  解冻密码
```



## sudo | 以特定用户的权限执行特定命令

```
-l  列出当前用户可执行的命令
-u username#uid 以指定用户执行命令
```

