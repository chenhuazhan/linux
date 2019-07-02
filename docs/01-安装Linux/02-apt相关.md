## 更新升级

apt-get update：更新索引文件（相当于检查更新）

apt-get upgrade：更新全部软件包文件（相当于一键更新）

apt-get dis-upgrade：sudo apt dist-upgrade    #本机系统软件更新，debian版本大升级

重复执行多次



## 安装软件失败

### apt进程被占用：

报错信息：

```
E: 无法获得锁 /var/lib/dpkg/lock-frontend - open (11: 资源暂时不可用)
E: 无法获取 dpkg 前端锁 (/var/lib/dpkg/lock-frontend)，是否有其他进程正占用它？
```

解决方法：

+ 关闭其他下载任务/关闭终端

+ 杀死apt进程

    ```bash
    ps -e|grep apt-get
    # ps -e|grep apt
    # 显示:6965 ?        00:00:01 apt-get
    sudo kill 6965
    ```

    

+ 强制解锁：

    ```bash
    sudo rm /var/cache/apt/archives/lock
    sudo rm /var/lib/dpkg/lock
    ```

    

































































