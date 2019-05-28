**Vim编辑器**

Linux系统会内建 vi 文本编辑器，Vim具有程序编程的能力，可以看作是Vi的增强版本，可以主动的以字体颜色辨别语法的正确性，方便程序设计、补充代码、编译及错误跳转等方便编程的功能丰富，被使用者广泛使用。

**vi / vim三种模式**

**正常模式**

正常模式下我们可以使用快捷键，用vim打开一个档案就直接进入一般模式，也就是默认模式。此模式你可以使用上下左右按键来移动光标；使用删除字符或删除整行来处理档案内容。同样可以使用复制、粘贴来处理文件数据。

**编辑模式**

按需 i，I，o，O，a，A，r，R等任何一个字母进入编辑模式，常使用 i 键。

**命令行模式**

命令行模式中提供相关的指令，用来完成读取、存储、替换、离开、显示行号等等。

**起步**

\1. 打开Xshell，键入 **vim jujidi.java** 命令

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWgwVhZzz6QBVXfJ0zVNReZeClGUzFpadSCDgjynOoCTQ4DicH6U48Wt8OFOPnp35jBBRSnyMe6H77g/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\2. 进入下方**默认模式**，无法输入

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWgwVhZzz6QBVXfJ0zVNReZeJX7ZEh4kxcI1zE8aH48CLlviauGjL4KySDTOrVJl72ZYAggDkPniba7g/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\3. 键入 **i** 进入**编辑模式**，可编辑。

![img](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

\4. 我们写一个类

![img](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

\5. 编辑完毕，输入**ESC**，退出编辑模式，进入**命令模式**

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWgwVhZzz6QBVXfJ0zVNReZeBh51iamT3iceicEgzQaBEGcarMIKyz1OE65LaDftNRQ02YBvoISO8mibwg/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\6. 键入 **:wq** 保存退出

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWgwVhZzz6QBVXfJ0zVNReZeVadgt9wUUbnqv8BBDqH9hCDtWia7S2oMQ1d3xJj343HReBBpom64R2g/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\7. 出现了 **jujidi.java** 文件

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWgwVhZzz6QBVXfJ0zVNReZeO4HWKm713LruVeGYdHEtardf36e655dFcnA4B6XIf2jh6QSOSGoVjw/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**模式切换**

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWgwVhZzz6QBVXfJ0zVNReZeibSWw3wSbBuHLOS990vnaL8WNUhicKHhcsTBe6gA8BfP3pk1VTvoqia7g/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**命令解释**

**命令模式**下也就是编辑模式按下esc后有3个常用的用来保存或者退出的命令：

- **：q！**直接退出，不保存。
- **：q**   只是打开看看不做任何修改时使用此命令， 如果修改了想要退出会提示没有保存，必须加上 **！** 强制执行。
- **：wq** 打开后做了修改，而且想要保存使用此命令。

**实操**

**复制粘贴**

- **yy** 拷贝当前行
- **5yy** 拷贝当前行向下的5行
- **p** 粘贴

\1. 创建文件 web.java

![img](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

 \2. 按下 **i** 进入编辑模式输入 3 行语句

 \3. 按下**esc**进入命令行模式

![img](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

\4. 光标移到最后一行，按下 **yy**  再按下 **p** 命令后就会复制一行

![img](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

\5. 光标移到此处，输入 **4yy** 复制4行

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWgwVhZzz6QBVXfJ0zVNReZeCStmOhQdJHxXqGNmVlhBpeliatdEVfMx3QibVnWeD0SR7GpXk2WYdu4g/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

\6. 光标移动此处按下 **p** 把刚刚的4行进行粘贴

![img](https://mmbiz.qpic.cn/mmbiz_png/e1jmIzRpwWgwVhZzz6QBVXfJ0zVNReZericHyAOfeSRL7KU5BfE1EpKhKMBicTWXKmyqvh6uuSRrAicXQOy5nY1oA/640?tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**删除**

- **dd**  删除当前行
- **5dd**  删除当前行向下的5行（命令模式下执行）

**查找**

在文件中查找某个单词：进入命令行模式，**/关键字** 回车即可。输入 **n** 查找匹配的下一个。

比如：**/hello**  查找文件中hello字段，按下n会一个个的查找。

**行号**

- 命名 **：set nu** 显示行号
- 命令**：set nonu** 取消显示行号（命令行模式下执行）

**首末行**

- 在**默认模式**下，输入**G**命令会跳的末尾
- 输入**gg**回到首行

**撤销**

- 在默认模式下，输入**u**命令

**移动指定行**

1. 显示行号 **：set nu** ，命令行模式下执行
2. 输入 目标行号
3. 输入 **shift + g**

**总结**

关于vim的命令还有很多，我们只是入门讲解，关于Vim编辑器的相关命令可以移步：www.cnblogs.com/yangjig/p/6014198.html，此处不再罗列出来。