## 1  查看文件或日志

> 查看文件内容或日志文件，用得最多的就是cat、head、tail命令。



### 1.1  cat

用于查看文件内容。

| eg           | 说明                     |
| ------------ | ------------------------ |
| cat test.log | 查看test.log文件所有内容 |



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



## 2  复制文件/目录

### 2.1  复制文件

| eg                                   | 说明                                                        |
| ------------------------------------ | ----------------------------------------------------------- |
| cp test.log /home/logs               | 复制test.log文件到/home/logs/目录下                         |
| cp test.log  /home/logs/test.new.log | 复制test.log文件到/home/logs/目录下并重新命名为test.new.log |



### 2.2  复制文件夹

| eg                         | 说明                                                         |
| -------------------------- | ------------------------------------------------------------ |
| cp -r logs/ /home/         | 复制 logs目录及目录下所有文件到/home/目录下，此时该目录会有logs目录 |
| cp -r logs/ /home/newlogs/ | 复制 logs目录及目录下所有文件到/home/newlogs/目录下，并把logs目录重新命名为newlogs，前提是/home/目录没有newlogs目录 |



**注：-r或-R表示循环，循环目录下所有文件和目录。下面所有命令也是如此。**



### 2.3  远程复制

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









