# 实验二 From GUI to CLI

## 一、实验目的
- 通过vimtutor学习并掌握vim的基本用法
- 掌握asciinema终端录屏方法

## 二、实验环境
- windows10 
- Virtualbox
ubuntu18.04-server-amd64
- 使用putty连接到虚拟机 方便复制粘贴


## 三、实验过程

```
sudo apt-get install asciinema #安装asciinema
asciinema auth #生成token
asciinema rec #开始录制
vimtutor 
crtl+D #结束录制
enter #录屏内容上传至网站
```

- [Lesson1](https://asciinema.org/a/B6XJtiGHWpnEnmTsExFh1TQSW)
- [Lesson2](https://asciinema.org/a/7fNYdbx5U4V1DRbAiYQto66ZN)
- [Lesson3](https://asciinema.org/a/ldaoE83HdGMu4i0fuPGgQjKcn)
- [Lesson4](https://asciinema.org/a/PEFRNIibgn7auQoG6YqMq44cH)
- [Lesson5](https://asciinema.org/a/KDutmW40GjiIUgOMPXe7fGL2s)
- [Lesson6](https://asciinema.org/a/KU5ShPWXvH2KxxOAtFaFICxjd)
- [Lesson7](https://asciinema.org/a/fP561PbYN0pz9KTwTYUjOviFs)

## 四、自查清单


- ##### 你了解vim有哪几种工作模式？
    - normal 
    - insert
    - visual
    
- ##### Normal模式下，从当前行开始，一次向下移动光标10行的操作方法？如何快速移动到文件开始行和结束行？如何快速跳转到文件中的第N行？
    - 一次向下移动光标10行:```j10 ```
    - 移动到开始行：```gg```
    - 移动到结束行：```G```
    - 跳转到第N行：```NG```，行号N通过```CRTL+G```来确定
- ##### Normal模式下，如何删除单个字符、单个单词、从当前光标位置一直删除到行尾、单行、当前行开始向下数N行？
    - 删除单个字符：```x```
    - 删除单个单词：```dw```
    - 当前光标位置删除到行尾:```d$```
    - 单行：```dd```
    - 向下数N行：```dNd```
- ##### 如何在vim中快速插入N个空行？如何在vim中快速输入80个-？
    - 插入到下方：```No```
    - 插入到上方：```NO```
    - 快速输入80个-：```80i-ESC```

- ##### 如何撤销最近一次编辑操作？如何重做最近一次被撤销的操作？
    - 撤销最近一次：```u```
    - 重做最近一次：```CRTL+R```
- ##### vim中如何实现剪切粘贴单个字符？单个单词？单行？如何实现相似的复制粘贴操作呢？
    - 单个字符：```x```
    - 单个单词：```de```
    - 单行:```dd```
    - 实现相似的复制粘贴操作：删除相当于剪切，会存在于缓冲区内，删除后按```p```即可粘贴
- ##### 为了编辑一段文本你能想到哪几种操作方式（按键序列）？
    - ```i/o/O```插入
    - ```a```添加
    - ```R```替换
    - 删除或复制粘贴
- ##### 查看当前正在编辑的文件名的方法？查看当前光标所在行的行号的方法？
    - ```CTRL+G```
- ##### 在文件中进行关键词搜索你会哪些方法？如何设置忽略大小写的情况下进行匹配搜索？如何将匹配的搜索结果进行高亮显示？如何对匹配到的关键词进行批量替换？
    - 从前往后查找：```/[关键词]```，按下```n```继续向下查找；从后往前查找：```?[关键词]```
    - 设置忽略大小：```:set ic```
    - 设置高亮显示：```:set hlsearch```
    - 批量替换：```s/[旧关键词]/[新关键词]/g```
- ##### 在文件中最近编辑过的位置来回快速跳转的方法？
    - 回到上一次的位置: ```Ctrl-I```
    - 去到下一次的位置: ```Ctrl-O```

- ##### 如何把光标定位到各种括号的匹配项？例如：找到(, [, or {对应匹配的),], or }
    - 光标移到某一括号，按下```%```
- ##### 在不退出vim的情况下执行一个外部程序的方法？
    - ```:![外部程序]```
- ##### 如何使用vim的内置帮助系统来查询一个内置默认快捷键的使用方法？如何在两个不同的分屏窗口中移动光标？
    - 查询内置快捷键: ```:help [快捷键]```
    - 移动光标： ```Ctrl-W```


## 五、参考

- [实验二指导](http://sec.cuc.edu.cn/huangwei/course/LinuxSysAdmin/chap0x02.exp.md.html#/title-slide)
- [asciinema-docs](https://asciinema.org/docs/how-it-works)

