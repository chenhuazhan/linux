Linux是我们开发人员必不可少的系统，也是经常接触到的。然而，Linux命令比较多，有些不常用也难记住。那么，我们如何更高效的使用Linux命令，而又不必全面地学习呢？今天就给大家分享一下我在开发过程中，比较常用、也比较实用的Linux命令。



01 查看文件或日志

查看文件内容或日志文件， 相信几乎所有人都会接触到。其中，用得最多的就是head、tail和cat命令。

**1、head**

表示头部，查看最前面几行数据。

| 命令                 | 说明                             |
| -------------------- | -------------------------------- |
| head test.log        | 查看test.log文件前几行日志内容   |
| head -n 20 test.log  | 查看test.log文件前20行日志内容   |
| head -n -20 test.log | 查看test.log除了最后20行日志内容 |

**2、tail**

表示尾部，查看最后几行或实时日志。

| 命令                   | 说明                                 |
| ---------------------- | ------------------------------------ |
| tail -f test.log       | 实时查看test.log文件最后几行日志内容 |
| tail -f -n 20 test.log | 实时查看test.log文件最后20行日志内容 |
| tail -n 20 test.log    | 查看test.log文件最后20行日志内容     |
| tail -n +20 test.log   | 查看test.log文件20行后的所有日志内容 |

**3、cat**

用于查看文件内容。

| 命令         | 说明                     |
| ------------ | ------------------------ |
| cat test.log | 查看test.log文件所有内容 |





02 本地复制

同一台服务器不同目录之间复制文件或目录也是经常用到的。

**1、复制文件**

| 命令                                      | 说明                                                         |
| ----------------------------------------- | ------------------------------------------------------------ |
| cp test.log /home/geshan/logs             | 复制test.log文件到/home/geshan/logs/目录下                   |
| cp test.log  /home/geshan/logs/cptest.log | 复制test.log文件到/home/geshan/logs/目录下并重新命名为cptest.log |

**2、复制文件夹**

| 命令                               | 说明                                                         |
| ---------------------------------- | ------------------------------------------------------------ |
| cp -r logs/ /home/geshan/          | 复制 logs目录及目录下所有文件到/home/geshan/目录下，此时该目录会有logs目录 |
| cp -r logs/ /home/geshan/testlogs/ | 复制 logs目录及目录下所有文件到/home/geshan/testlogs/目录下，并把logs目录重新命名为testlogs，前提是/home/geshan/目录没有testlogs目录 |



**注：-r或-R表示循环，循环目录下所有文件和目录。下面所有命令也是如此。**



03 远程复制

当我们需要从远程服务器复制某个文件或目录到本地登录的服务器时，大部分人想到先登录远程服务器下载该文件，然后再登录本地服务器再上传文件。这样是比较麻烦，效率也不高。

**1、本地服务器复制到远程服务器**

**(1)复制文件**

|       | 命令格式                                               |
| ----- | ------------------------------------------------------ |
| 命令1 | scp local_file remote_username@remote_ip:remote_folder |
| 命令2 | scp local_file remote_username@remote_ip:remote_file   |
| 命令3 | scp local_file remote_ip:remote_folder                 |
| 命令4 | scp local_file remote_ip:remote_file                   |

第1,2个指定了用户名，命令执行后需要输入用户密码，第1个仅指定了远程的目录，文件名字不变；

第2个指定了文件名 ；

第3,4个没有指定用户名，命令执行后默认与当前服务器用户名并需要输入用户密码，第3个仅指定了远程的目录，文件名字不变，第4个指定了文件名。



**实例1：** 从本地服务器复制test.log至192.168.130.130服务器的/home/geshan/目录，并重新命名为20190125.log

**命令：**

```
scp test.log root@192.168.130.130:/home/geshan/20190125.log
```



**实例2：** 从本地服务器复制test.log至192.168.130.130服务器的/home/geshan/目录

**命令：**

```
scp test.log root@192.168.130.130:/home/geshan/
```

 

**(2) 复制目录**

|       | 命令格式                                                    |
| ----- | ----------------------------------------------------------- |
| 命令1 | scp -r local_folder remote_username@remote_ip:remote_folder |
| 命令2 | scp -r local_folder remote_ip:remote_folder                 |

第1个指定了用户名，命令执行后需要输入用户密码； 

第2个没有指定用户名，命令执行后需要输入用户名和密码。



**实例：**从本地服务器/home/appuser/目录下的tomcat目录复制到192.168.130.130服务器的/home/geshan/目录

**命令：**

```
scp -r /home/appuser/tomcat root@192.168.130.130:/home/geshan/
```



**2、从远程服务器复制到本地服务器**

从远程复制到本地的scp命令与上面的命令雷同，只要将从本地复制到远程的命令后面2个参数互换顺序就行了。

**(1)复制文件**

**实例：**从192.168.130.130远程服务器的/home/geshan/路径下test.log文件复制到本地服务器/home/appuser/路径

**命令：**

```
scp root@192.168.130.130:/home/geshan/test.log  /home/appuser/
```

**(2)复制目录**

**实例：**从192.168.130.130远程服务器的/home/geshan/路径下tomcat文件夹复制到本地服务器/home/appuser/路径

**命令：**

```
scp -r root@192.168.130.130:/home/geshan/tomcat/  /home/appuser/
```



**注：ip地址和路径之间（即冒号之间）没有任何空格，否则会报错。当第一次和另外一台服务通信（如复制文件），会提示是否信任，输入yes即可。**





04 压缩和解压

压缩和解压文件也是经常遇到的。如果下载一个目录下的所有文件，可以直接下载这个目录，但是直接下载目录的话，文件一旦很多，下载过程中很容易丢失文件，下载速度也比较慢。一般情况下是先压缩文件夹再下载。下面给大家介绍四种压缩和解压命令。



**1、tar命令**

解压：

```
tar zxvf fileName.tar
```

压缩：

```
tar czvf fileName.tar folder/
```



**实例：**

解压一个log.tar文件：

```
tar zxvf log.tar
```

压缩log目录并命名为log.tar：

```
tar czvf log.tar log/
```



**2、gz命令**

压缩：

```
gzip FileName
```

**注：压缩为 .gz 文件 源文件会消失**

如果想保留源文件，使用下面命令

```
gzip -c 源文件 > 压缩文件
```

解压：

```
gunzip FileName.gz
或者 gzip -d FileName.gz
```



**.tar.gz 和 .tgz**

解压：

```
tar zxvf FileName.tar.gz
```

压缩：

```
tar zcvf FileName.tar.gz DirName
```

压缩多个文件：

```
tar zcvf FileName.tar.gz DirName1 DirName2 DirName3 ...
```

**实例：**

解压tomcat.tar.gz文件

```
tar zxvf tomcat.tar.gz
```

压缩tomcat目录，并命名为tomcat.tar.gz文件

```
tar zcvf tomcat.tar.gz tomcat/
```



**3、zip命令**

解压：

```
unzip fileName.zip
```

压缩：

```
   zip -r fileName.zip folder/
或者 zip -r fileName.zip folder1/ folder2/ .....
或者 zip -r fileNamezip file1 file2 ...
```



**注：压缩目录时，需加 -r ，表示循环该目录下所有文件和目录。压缩多个文件或目录时，文件或目录之间需要空格。**



**实例：**

解压一个log.zip文件：

```
unzip log.zip
```

压缩log文件目录并命名为log.zip：

```
zip -r log.zip log/
```

压缩log1和log2目录并命名为log.zip：

```
zip -r log.zip log1/ log2/
```

 压缩test1.log和test2.log文件并命名为log.zip：

```
zip  log.zip test1.log test2.log
```



**4、rar命令**

同理，和zip命令类似，只需把zip改为rar即可。





05 修改权限

Linux系统中文件和目录访问权限是不同的，通过些方式可以确定谁可以对该文件和目录进行相应的操作。

其中，文件或目录的访问权限分为只读，只写和可执行三种，分别代表可读、可写和可执行。

**1、chgrp命令**

改变文件或目录所属的组。

命令：

```bash
chgrp groupName fileName
或者 chgrp -R groupName dirName/
```



**实例：**

把test.log文件所属的组修改为geshan组

```
chgrp geshan test.log
```

把logs目录及该目录下所有文件所属的组修改为geshan组

```
chgrp -R geshan logs/
```

**2、chown命令**

更改某个文件或目录所属的用户。

命令：

```
chown userName fileName
或者 chown -R userName dirName/
```


**实例：**

把test.log文件所属用户修改为geshan用户

```
chown geshan test.log
```

把logs目录及该目录下所有文件所属用户修改为geshan用户

```
chown -R geshan logs/
```



**3、chmod命令**

用于改变文件或目录的访问权限。用户用它控制文件或目录的访问权限。

命令：

```
chmod mode fileName
或者 chmod -R mode dirName/
```

其中，mode有很多种表示含义，下面只对数字说明。

大部分人看到mode有777或776等权限，这些表示什么呢？



为了方便，把mode改为abc，其中a,b,c各为一个数字，分别表示user、group及other的权限。r=4，w=2，x=1，r表示Read读，w表示Write写，x表示eXecute。

- 若要rwx属性则4+2+1=7；
- 若要rw-属性则4+2=6；
- 若要r-x属性则4+1=5。



**实例：**

把test.log文件修改可读写执行（即777）操作。

```
chmod 777 test.log
```

把logs目录及目录下所有文件修改为读写（666）操作。

```
chmod -R 666 logs/
```

在Linux系统中输入ll(两个小写LL)，如果文件或目录为777（读写执行）权限，可看到最前面为-rwxrwxrwx。如果为666（读写）权限，可看到最前面为-rw-rw-rw。



**注：一般修改文件或目录权限需要超级用户（root）进行修改，否则可能会报权限不足。**



这些Linux命令是比较常用实用的命令，肯定会有用得到的时候，记得收藏并转发给有需要的人哦。