# 基本概念

**在Linux中一切皆文件**，包括它的硬件，声卡、硬盘等等都会映射成一个文件来管理。在 Linux 或 Unix 操作系统中，所有的文件和目录都被组织成以一个根节点开始的倒置的树状结构。

文件系统的最顶层是由根目录开始的，系统使用 / 来表示根目录。在根目录之下的既可以是目录，也可以是文件，而每一个目录中又可以包含子目录文件。如此反复就可以构成一个庞大的文件系统。

在Linux文件系统中有两个特殊的目录，一个用户所在的工作目录，也叫**当前目录**，可以使用一个点 **.** 来表示；另一个是当前目录的**上一级目录**，也叫父目录，可以使用两个点 **..** 来表示。在以后学习切换目录相关命令的时候还会接触到。

如果一个目录或文件名以一个点 **.** 开始的，表示这个目录或文件是一个**隐藏目录或文件**(如：**.**bashrc)。即以默认方式查找时，不显示该目录或文件。



# 目录结构

![img](https://mmbiz.qpic.cn/mmbiz_jpg/e1jmIzRpwWiaeBrCjxxkbjE2PxKWR32ngl5uHdQ1u0QaZafotNAKXzA9FSPib9KdVWOiaZ4r5IxyoGc5UuO5ibg3Sg/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

常用目录讲解

/bin ：存放常用指令：cp cat ...

/opt：额外安装软件

/boot：启动Linux使用的核心文件

/dev ：管理设备，把硬件映射成文件，硬件文件如：cpu disk等

/var：不断扩充的东西，日志等等

/lib： 开机需要的基本链接共享库

/media ：U盘等插入，media就会多出文件

/mnt ：挂载别的文件系统

/root：root用户的相关文件

/sbin：高级用户使用的指令

/selinux：安全目录，危机系统安全时触发

/proc：尽量不修改，存放内核相关文件

/home ：创建一个普通用户，会在home下生成对应文件，文件的名就是用户名

/srv：服务启动之后需要提取的相关数据，尽量不修改此文件信息

/etc：系统管理需要的配置文件和子目录

/user：用户安装的应用程序，类似Windows中的program files目录



### 注意

在linux系统中，有几个目录是比较重要的，平时需要注意不要误删除或者随意更改内部文件。

**/etc：** 上边也提到了，这个是系统中的配置文件，如果你更改了该目录下的某个文件可能会导致系统不能启动。

**/usr/bin, /usr/sbin,/bin, /sbin:** 这是系统预设的执行文件的放置目录，比如 ls 就是在/bin/ls 目录下的。

值得提出的是，/bin, /usr/bin 是给系统用户使用的指令（除root外的通用户），而/sbin, /usr/sbin 则是给root使用的指令。

**/var：** 这是一个非常重要的目录，系统中扩充的文件存在这里。系统上跑了很多程序，那么每个程序都会有相应的日志产生，而这些日志就被记录到这个目录下，具体在/var/log 目录下，另外mail的预设放置也是在这里。



## 0  基本目录操作

### 0.1  查看目录内容：ls

.ls [选项] [目录名 | 列出相关目录下的所有目录和文件，ls最常用的参数有三个： -a -l -F。

ls –a

Linux上的文件以.开头的文件被系统视为隐藏文件，仅用ls命令是看不到他们的，而用ls -a除了显示一般文件名外，连隐藏文件也会显示出来。



ls –l

列出格式化后的列，该参数显示更详细的文件信息。



ls –F

使用这个参数表示在文件的后面多添加表示文件类型的符号，例如*表示可执行，/表示目录，@表示连结文件，这都是因为使用了-F这个参数。但是现在基本上所有的Linux发行版本的ls都已经内建了-F参数，也就是说，不用输入这个参数，我们也能看到各种分辨符号。

```bash
-a  列出包括.a开头的隐藏文件的所有文件
-A  通-a，但不列出"."和".."
-l  列出文件的详细信息
-c  根据createdtime排序显示
-t  根据文件修改时间排序
---color[=WHEN] 用色彩辨别文件类型 WHEN 可以是'never'、'always'或'auto'其中之一
   白色：表示普通文件
   蓝色：表示目录
   绿色：表示可执行文件
   红色：表示压缩文件
   浅蓝色：链接文件
   红色闪烁：表示链接的文件有问题
   黄色：表示设备文件
   灰色：表示其它文件
```



### 0.2  切换目录：cd

| eg       | 说明                                           |
| -------- | ---------------------------------------------- |
| cd /     | 切换到根目录                                   |
| cd -     | 命令后跟一个减号，则会退回到切换前的目录       |
| cd ~     | 当前用户的 home 目录                           |
| cd       | 命令后不指定目录，会切换到当前用户的 home 目录 |
| cd ..    | 切换到上一级目录                               |
| cd /etc/ | 切换到根目录下的etc目录                        |
| cd etc   | 切换到当前目录下的etc目录                      |

### 0.3  显示用户当前工作目录：pwd

basename 和 dirname**

basename用于查看文件不含路径的名字，dirname则用于查看文件路径，使用效果我们测试一下便知：

\> basename /home/hj/1.txt

1.txt

\> dirname  /home/hj/1.txt

/home/hj

\> basename 1.txt

1.txt

\> dirname 1.txt



### 0.4  输入输出

#### 管道：

利用Linux所提供的管道符“|”将两个命令隔开，管道符左边命令的输出就会作为管道符右边命令的输入。连续使用管道意味着第一个命令的输出会作为第二个命令的输入，第二个命令的输出又会作为第三个命令的输入，依此类推。

注意：管道左边命令的输入作为管道右边命令的输入(命令的输入是一定的)，不是参数，并不是所有命令都支持管道

例子：ls | grep a  查看当前目录下名称包含a的文件或文件夹

#### 清屏

clear命令是用来清除当前屏幕显示的，不需任何参数，和dos下的cls命令功能相同。

## 1  查看文件或日志

> 查看文件内容或日志文件，用得最多的就是cat、head、tail命令。



### 1.1  cat

cat [选项] [文件]..| 一次显示整个文件或从键盘创建一个文件或将几个文件合并成一个文件

用于查看文件内容。cat命令的功能是显示或连结一般的ascii文本文件。cat是concatenate的简写，类似于dos下面的type命令。

```bash
-n  编号文件内容再输出
-E  在结束行提示$
```



| eg                      | 说明                                                        |
| ----------------------- | ----------------------------------------------------------- |
| cat test.log            | 查看test.log文件所有内容                                    |
| cat file1 file2         | 依次显示file1,file2的内容                                   |
| cat file1 file2 > file3 | 把file1, file2的内容结合起来写入（覆盖写入）到file3文件中。 |

**注：tac | 反向显示**

### 1.2  head

表示头部，查看最前面几行(默认最多10行）数据。

| eg                   | 说明                             |
| -------------------- | -------------------------------- |
| head test.log        | 查看test.log文件前几行日志内容   |
| head -n 20 test.log  | 查看test.log文件前20行日志内容   |
| head -n -20 test.log | 查看test.log除了最后20行日志内容 |



### 1.3  tail

表示尾部，查看最后几行(默认最多10行）或实时日志。

| eg                     | 说明                                               |
| ---------------------- | -------------------------------------------------- |
| tail -f test.log       | 查看test.log文件最后几行日志内容                   |
| tail -f test.log       | 实时查看（会自动刷新）test.log文件最后几行日志内容 |
| tail -f -n 20 test.log | 实时查看test.log文件最后20行日志内容               |
| tail -n 20 test.log    | 查看test.log文件最后20行日志内容                   |
| tail -n +20 test.log   | 查看test.log文件20行后的所有日志内容               |



### `more` - 在显示器上阅读文件的过滤器,用于分页显示,`less`提供了`more`的模拟并做了增强

这两个命令用于查看文件，如果一个文件太长，显示内容超出一个屏幕，用cat命令只能看到最后的内容，用more和less两个命令可以分页查看。more指令可以使超过一页的文件内容分页暂停显示，用户按键后才继续显示下一页。而less除了有more的功能以外，还可以用方向键往上或往下的滚动文件，更方便浏览阅读。

less的常用动作命令：

回车键 向下移动一行；

y 向上移动一行；

空格键 向下滚动一屏；

b 向上滚动一屏；

d 向下滚动半屏；

h less的帮助；

u 向上洋动半屏；

w 可以指定显示哪行开始显示，是从指定数字的下一行显示；比如指定的是6，那就从第7行显示；

g 跳到第一行；

G 跳到最后一行；

p n% 跳到n%，比如 10%，也就是说比整个文件内容的10%处开始显示；

/pattern 搜索pattern ，比如 /MAIL表示在文件中搜索MAIL单词；

v 调用vi编辑器；

q 退出less

!command 调用SHELL，可以运行命令；比如!ls 显示当前列当前目录下的所有文件；



### wc命令

该命令用于统计指定文件中的字节数、字数、行数。该命令各选项含义如下：

-l 统计行数

-w 统计字数

-c 统计字节数

这些选项可以组合使用。输出列的顺序和数目不受选项的顺序和数目的影响。总是按下述顺序显示并且每项最多一列。



行数、字数、字节数、文件名

如果命令行中没有文件名，则输出中不出现文件名。

例如：

oracle@hjtest:~> wc 1.txt 2.txt

  460  1679 16353 1.txt

  300  1095 10665 2.txt

  760  2774 27018 总用量

oracle@hjtest:~> wc -l 1.txt

460 1.txt

缺省参数为-lcw，即wc file1 file2命令的执行结果与上面一样。

## 2  复制文件/目录

cp [选项] 源文件或目录 目录或多个源文件 | 将源文件复制至目标文件，或将多个源文件复制至目标目录。

```bash
-r -R 递归复制该目录及其子目录内容
-p  连同档案属性一起复制过去
-f  不询问而强制复制
-s  生成快捷方式
-a  将档案的所有特性都一起复制
```



### 2.1  复制文件：cp

| eg                                   | 说明                                                         |
| ------------------------------------ | ------------------------------------------------------------ |
| cp 1.log 1.txt                       | 复制1.log文件到本目录下并命名为1.txt（前提是本目录下不存在1.txt目录） |
| cp test.log /home/logs               | 复制test.log文件到/home/logs/目录下（前提是/home/logs/目录存在） |
| cp test.log  /home/logs/test.new.log | 复制test.log文件到/home/logs/目录下并重新命名为test.new.log（前提是 /home/logs/test.new.log目录不存在） |



### 2.2  复制文件夹：cp -r

| eg                         | 说明                                                         |
| -------------------------- | ------------------------------------------------------------ |
| cp -r logs/ /home/         | 复制 logs目录及目录下所有文件到/home/目录下，此时该目录会有logs目录 |
| cp -r logs/ /home/newlogs/ | 复制 logs目录及目录下所有文件到/home/newlogs/目录下，并把logs目录重新命名为newlogs，前提是/home/目录没有newlogs目录 |



**注：-r或-R表示循环，循环目录下所有文件和目录。下面所有命令也是如此。**



### 2.3  远程复制：scp

scp [参数] [原路径] [目标路径] | 在Linux服务器之间复制文件和目录

```bash
-v  详细显示输出的具体情况
-r  递归复制整个目录
(1) 复制文件：  
命令格式：  
scp local_file remote_username@remote_ip:remote_folder  
或者  
scp local_file remote_username@remote_ip:remote_file  
或者  
scp local_file remote_ip:remote_folder  
或者  
scp local_file remote_ip:remote_file  
第1,2个指定了用户名，命令执行后需要输入用户密码，第1个仅指定了远程的目录，文件名字不变，第2个指定了文件名  
第3,4个没有指定用户名，命令执行后需要输入用户名和密码，第3个仅指定了远程的目录，文件名字不变，第4个指定了文件名   
(2) 复制目录：  
命令格式：  
scp -r local_folder remote_username@remote_ip:remote_folder  
或者  
scp -r local_folder remote_ip:remote_folder  
第1个指定了用户名，命令执行后需要输入用户密码；  
第2个没有指定用户名，命令执行后需要输入用户名和密码；
eg:
   从 本地 复制到 远程
   scp /home/daisy/full.tar.gz root@172.19.2.75:/home/root 
   从 远程 复制到 本地
   scp root@/172.19.2.75:/home/root/full.tar.gz /home/daisy/full.tar.gz
```



#### 2.3.1  本地服务器复制到远程服务器

| 命令格式                                               | 说明                                                         |
| ------------------------------------------------------ | ------------------------------------------------------------ |
| scp local_file remote_username@remote_ip:remote_folder | 复制本地文件到指定远程目录，指定了用户名，命令执行后需要输入用户密码 |
| scp local_file remote_username@remote_ip:remote_file   | 复制本地文件并重命名为指定远程文件名，指定了用户名，命令执行后需要输入用户密码 |
| scp local_file remote_ip:remote_folder                 | 复制本地文件到指定远程目录，没有指定用户名，命令执行后默认为当前服务器用户名并需要输入用户密码 |
| scp local_file remote_ip:remote_file                   | 复制本地文件并重命名为指定远程文件名，没有指定用户名，命令执行后默认为当前服务器用户名并需要输入用户密码 |



| eg                                                   | 说明                                                         |
| ---------------------------------------------------- | ------------------------------------------------------------ |
| scp test.log root@192.168.130.130:/home/             | 从本地服务器复制test.log至192.168.130.130服务器的/home/目录  |
| scp test.log root@192.168.130.130:/home/20190527.log | 从本地服务器复制test.log至192.168.130.130服务器的/home/目录，并重新命名为20190527.log |

复制目录：加-r参数即可



#### 2.3.2  从远程服务器复制到本地服务器

从远程复制到本地的scp命令与上面的命令雷同，只要将从本地复制到远程的命令后面2个参数互换顺序就行了。

| eg                                                           | 说明                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| scp root@192.168.130.130:/home/geshan/test.log  /home/appuser/ | 从192.168.130.130远程服务器的/home/geshan/路径下test.log文件复制到本地服务器/home/appuser/路径 |
| scp -r root@192.168.130.130:/home/geshan/tomcat/  /home/appuser/ | 从192.168.130.130远程服务器的/home/geshan/路径下tomcat文件夹复制到本地服务器/home/appuser/路径 |

**注：ip地址和路径之间（即冒号之间）没有任何空格，否则会报错。当第一次和另外一台服务通信（如复制文件），会提示是否信任，输入yes即可。**



## 3  压缩和解压



### 3.1  .tar格式

```bash
# 压缩folder文件夹为folder.tar
tar czvf folder.tar folder/
# 压缩file1文件为file1.tar
tar czvf file1.tar file1
# 解压file2.tar文件
tar xzvf file2.tar
```



### 3.2  .gz格式

```bash
# 压缩file1文件为file1.gz,源文件会消失
gzip file1
# 压缩file2文件为file2.gz,保留源文件
gzip -c file2 > file2.gz
# 解压file1.gz,file1.gz会消失
gunzip file1.gz
```



### 3.3  .tar.gz 和 .tgz格式

```bash
# 压缩单个文件/目录
tar czvf FileName.tar.gz FileName
# 压缩多个文件/目录
tar czvf FileName.tar.gz FileName1 FileName2 DirName3 ...
# 解压
tar zxvf FileName.tar.gz
```



### 3.4  .zip格式

```bash
# 压缩
zip fileName.zip fileName
zip -r fileName.zip folder/
# 或者 zip -r fileName.zip folder1/ folder2/ .....
# 或者 zip -r fileName.zip file1 file2 ...
# 解压
unzip fileName.zip
```

**注：压缩目录时，需加 -r 参数，否则压缩进去的是空目录。压缩多个文件或目录时，文件或目录之间需要空格。**



### 3.5  .rar格式

和zip命令类似，只需把zip改为rar即可。



## 4  文件/目录权限

文件或目录的访问权限分为只读，只写和可执行三种，分别代表可读、可写和可执行。

### 4.1  chmod

用于改变文件或目录的访问权限。用户用它控制文件或目录的访问权限。

```bash
chmod mode fileName
# 或者 
chmod -R mode dirName/
```

其中，mode有很多种表示含义

#### 数字设定法

大部分人看到mode有777或776等权限，这些表示什么呢？

用数字表示属性的含义 :

+ 0表示没有权限

- 1表示可执行权限
- 2表示可写权限
- 4表示可读权限

为了方便，把mode改为abc，其中a,b,c各为一个数字，分别表示user、group及other的权限。r=4，w=2，x=1，r表示Read读，w表示Write写，x表示eXecute。

- 若要rwx属性则4+2+1=7；
- 若要rw-属性则4+2=6；
- 若要r-x属性则4+1=5。



| eg                 | 说明                                     |
| ------------------ | ---------------------------------------- |
| chmod 777 test.log | 把test.log文件修改可读写执行操作         |
| chmod -R 666 logs/ | 把logs目录及目录下所有文件修改为读写操作 |

#### 文字设定法

- u 表示“用户（user）”，即文件或目录的所有者。
- g 表示“同组（group）用户”，即与文件属主有相同组ID的所有用户
- o 表示“其他（others）用户”。
- a 表示“所有（all）用户”。它是系统默认值。

eg:文件 a.txt的访问权限为 rwx-r-xr-x, 要去掉所有用户的执行权限并增加同组用户的写权限,命令是:

```bash
chmod a-x,g+w a.txt
```



注：一般修改文件或目录权限需要超级用户（root）进行修改，否则可能会报权限不足。**



### 4.2  chgrp

改变文件或目录所属的组。

```bash
chgrp groupName fileName
# 或者 
chgrp -R groupName dirName/
```



| eg                    | 说明                                               |
| --------------------- | -------------------------------------------------- |
| chgrp geshan test.log | 把test.log文件所属的组修改为geshan组               |
| chgrp -R geshan logs/ | 把logs目录及该目录下所有文件所属的组修改为geshan组 |



### 4.3  chown

更改某个文件或目录所属的用户。

```bash
chown userName fileName
# 或者 
chown -R userName dirName/
```



| eg                    | 说明                                                 |
| --------------------- | ---------------------------------------------------- |
| chown geshan test.log | 把test.log文件所属用户修改为geshan用户               |
| chown -R geshan logs/ | 把logs目录及该目录下所有文件所属用户修改为geshan用户 |



## 5  写入文件

">"是右重定向符，表示将左边命令结果当成右边命令的输入，注意：如果右侧文件是一个已存在文件，其原有内容将会被清空，而变成左侧命令输出内容。如果希望以追加方式写入，请改用">>"重定向符。



如果">"左边没有指定文件，如： cat >file1，将会等用户输入，输入完毕后再按[Ctrl]+[c]或[Ctrl]+[d]，就会将用户的输入内容写入file1。



**echo命令**

echo命令的使用频率不少于ls和cat，尤其是在shell脚本编写中。

语法：echo [-ne][字符串]

功能：echo会将输入的字符串送往标准输出，输出的字符串间以空白字符隔开， 并在最后加上换行符。

参数：

-n 显示字串时在最后自动换行

-e 支持以下格式的转义字符， -E 不支持以下格式的转义字符

/a 发出警告声；

/b 删除前一个字符；

/c 最后不加上换行符号；

/f 换行但光标仍旧停留在原来的位置；

/n 换行且光标移至行首；

/r 光标移至行首，但不换行；

/t 插入tab；

/v 与/f相同；

// 插入/字符；

/nnn 插入nnn（八进制）所代表的ASCII字符；

 

示例：

Oracle@hjtest:~/hgd> echo "123" "456"

123 456

oracle@hjtest:~/hgd> echo "123/n456"

123/n456

oracle@hjtest:~/hgd> echo -e "123/n456"

123

456

oracle@hjtest:~/hgd> echo -E "123/n456"

123/n456

oracle@hjtest:~/hgd> echo -E "123///456"

123//456

oracle@hjtest:~/hgd> echo -e "123///456"

123/456

oracle@hjtest:~/hgd> echo -e "123/100456"

123@456

 

注意事项：

在Linux使用的bash下，单引号’’和双引号是有区别的，单引号忽略所有的转义，双引号不会忽略以下特殊字符：

Dollar signs ($)，Back quotes (`)，Backslashes (/)，Excalmatory mark(!)



示例如下：

oracle@hjtest:~> echo "`TEST`"

-bash: TEST: command not found

oracle@hjtest:~> echo '`TEST`'

```
TEST
```

oracle@hjtest:~> echo "$TEST"

​        

oracle@hjtest:~> echo '$TEST'

$TEST

oracle@hjtest:~> echo "//TEST"

/TEST

oracle@hjtest:~> echo '//TEST'

//TEST

oracle@hjtest:~> echo "Hello!"

echo "Hello"

Hello

oracle@hjtest:~> echo 'Hello!'

Hello!





## 6  移动/重命名文件/目录

移动文件规则类似复制文件，移动目录时不需要-r参数

mv [选项] 源文件或目录 目录或多个源文件 | 移动或重命名文件

```bash
-b  覆盖前做备份
-f  如存在不询问而强制覆盖
-i  如存在则询问是否覆盖
-u  较新才覆盖
-t  将多个源文件移动到统一目录下，目录参数在前，文件参数在后
eg:
   mv a /tmp/ 将文件a移动到 /tmp目录下
   mv a b 将a命名为b
   mv /home/zenghao test1.txt test2.txt test3.txt
```



## 7  创建/删除文件/目录

touch file 新建文件,touch [选项] 文件 | 创建空文件或更新文件时间

```bash
-a  只修改存取时间
-m  值修改变动时间
-r  eg:touch -r a b ,使b的时间和a相同
-t  指定特定的时间 eg:touch -t 201211142234.50 log.log 
   -t time [[CC]YY]MMDDhhmm[.SS],C:年前两位
```



mkdir dir 新建目录

```bash
-p  递归创建目录，若父目录不存在则依次创建
-m  自定义创建目录的权限  eg:mkdir -m 777 hehe
```



mkdir -p 1/2/3 若指定路径的父目录不存在则一并创建

rmdir dir 删除空目录

```bash
-p  若自父母删除后父目录为空则一并删除
```



rm file 删除文件,rm [选项] 文件… | 一个或多个文件或目录

```bash
-r  删除文件夹
-f  删除不提示
-i  删除提示
-v  详细显示进行步骤
```



rm -r dir 递归删除目录

rm -rf dir 递归删除目录并自动忽略确认提示

rm -d  删除空目录

**linux下删除的文件是不能恢复的**



## 8  匹配/查找

### grep 匹配文件字符

grep是（global search regular expression(RE) and print out the line的缩写，用于从文件面搜索包含指定模式的行并打印出来，它是一种强大的文本搜索工具，支持使用正则表达式搜索文本。grep的工作方式是这样的，它在一个或多个文件中搜索字符串模板。如果模板包括空格，则必须被””引用，模板后的所有字符串被看作文件名。搜索结果送到屏幕，不影响原文件内容。

grep可用于shell脚本，因为grep通过返回一个状态值来说明搜索的状态，如果模板搜索成功，则返回0，如果搜索不成功，则返回1，如果搜索的文件不存在，则返回2。我们利用这些返回值就可进行一些自动化的文本处理工作。



示例：

$ ls -l | grep '^a'

通过管道过滤ls -l输出的内容，只显示以a开头的行。

$ grep 'test' d*

显示所有以d开头的文件中包含test的行。

$ grep 'test' aa bb cc

显示在aa，bb，cc文件中匹配test的行。

$ grep '[a-z]/{5/}' aa

显示所有包含每个字符串至少有5个连续小写字符的字符串的行。

$ grep 'w/(es/)t.*/1' aa



如果west被匹配，则es就被存储到内存中，并标记为1，然后搜索任意个字符（.*），这些字符后面紧跟着另外一个es（/1），找到就显示该行。如果用egrep或grep -E，就不用"/"号进行转义，直接写成'w(es)t.*/1'就可以了。

 

### `find` - 在目录层次结构中搜索文件



## 9  查看当前目录路径

pwd



## 10  检查目标是文件/目录

test - 检查文件类型并比较

+ -d 检查此file是否是一个目录

- -e 检查此file是否存在
- -f 检查此file是否为一般的文件







