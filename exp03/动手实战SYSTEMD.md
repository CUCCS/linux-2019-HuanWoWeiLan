# 实验三 动手实战SYSTEMD


## 一、实验目的
- 学习理解Systemd基本用法并实践
## 二、实验环境
- windows10 
- Virtualbox
ubuntu18.04-server-amd64
- 使用putty连接到虚拟机 方便复制粘贴
## 三、实验过程

#### 1.命令篇
- [Start](https://asciinema.org/a/MUgOrWUUnl0SpdZKoXlKEdkxq)
- [Unit](https://asciinema.org/a/m96CxPmJomSmgCh41iRF8a9ZW)
- [Target](https://asciinema.org/a/XSb2aYl8AQQGRUIALfHLXYlKJ)
- [Journal](https://asciinema.org/a/ZcDpisJv0q6q4a8g3o7KrMhMj)


#### 2.实战篇

- [Actual_combat](https://asciinema.org/a/GKf9M0JUfo22Gi0QH5AzPoosN)


## 四、自查清单
- ##### 如何添加一个用户并使其具备sudo执行程序的权限？
```bash
#添加一个用户
sudo adduser username

#将其加入sudo组中
sudo usermod -a -G sudo username
```
- ##### 如何将一个用户添加到一个用户组？
```
sudo usermod -a -G usergroup username
```

- ##### 如何查看当前系统的分区表和文件系统详细信息？
```bash
#查看分区表
sudo fdisk -l

#查看文件系统详情
df -a
```
- ##### 如何实现开机自动挂载Virtualbox的共享目录分区？
```bash
#虚拟机中创建共享目录
mkdir /mnt/share

#挂载
mount-t vboxsf share_file_name /mnt/share

#进入/etc/fstab进行编辑
share_file_name /mnt/share vboxsf default 0 0
```

- ##### 基于LVM（逻辑分卷管理）的分区如何实现动态扩容和缩减容量？
```bash
#安装lvm2包
sudo apt install lvm2

#切换至root用户
sudo su

#查看逻辑卷
lvdisplay

#动态扩容
lvextend --size +<大小>m <逻辑卷>

#缩减容量
lvreduce --size -<大小>m <逻辑卷>
```
- ##### 如何通过systemd设置实现在网络连通时运行一个指定脚本，在网络断开时运行另一个脚本？
    - 编辑其配置文件的```service```区块：
        - ```ExecStartPost=网络连通时运行的指定脚本```
        - ```ExecStopPost=网络断开时运行脚本```
- ##### 如何通过systemd设置实现一个脚本在任何情况下被杀死之后会立即重新启动？实现杀不死？
    - 编辑其配置文件的```service```区块：```Restart```字段修改为```always```

## 五、参考

- [Systemd 入门教程：命令篇](http://www.ruanyifeng.com/blog/2016/03/systemd-tutorial-commands.html)

- [Systemd 入门教程：实战篇](http://www.ruanyifeng.com/blog/2016/03/systemd-tutorial-part-two.html)

- [VirtuablBox共享文件夹设置](https://blog.csdn.net/ysh198554/article/details/73335844)
- [linux-2019-xaZKX
](https://github.com/CUCCS/linux-2019-xaZKX/blob/hw3/chap03/%E5%AE%9E%E9%AA%8C%E6%8A%A5%E5%91%8A3.md)