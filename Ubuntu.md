# 输入法无法切换中文

## 解决方案

使用搜狗输入法

安装搜狗输入法

```shell
sudo dpkg -i sogoupinyin_4.0.1.2800_x86_64.deb
```

主要是因为缺少包导致的

``` shell
sudo apt-get install libqt5qml5 libqt5quick5 libqt5quickwidgets5 qml-module-qtquick2
sudo apt install libgsettings-qt1
```

## 参考链接

[[1] wonghome. Ubuntu 18.04 安装搜狗输入法 [EB/OL].](https://blog.csdn.net/qq_39779233/article/details/127290795)
[[2] 雨中漫步-99. ubuntu系统安装好搜狗输入法后只能输入英文，无法输入中文的解决方案 [EB/OL]. ](https://blog.csdn.net/yuzhongmanbu99/article/details/127944446)

# 开机遇到grub>

## 双系统开机到grub的解决

1. 先在grub>输入ls，展示的是所有分区

2. 然后再ls (xxx,xxx)/boot/grub注意括号里面的应该填上自己分区名字，这一步是为了检查grub所在的具体分区，如果没有出现没有找到文件位置的提示，就说明找对了

3. 假如找到的分区为(hd1,gpt3)那么就运行set root=(hd1,gpt3)

4. 再输入set prefix=(hd1,gpt3)/boot/grub

5. 输入insmod normal，再输入normal

6. 就会到正常引导了

7. 进入linux系统后sudo update-grub再输入sudo grub-install /dev/sda

PS:出现这种情况的可能原因：win系统更新覆盖了，强制关闭linux，等等

# Linux安装MySQL

## Linux/UNIX 上安装 MySQL

```shell
sudo apt-get install mysql-server #默认最新版
```

当你在Ubuntu上使用sudo apt-get install mysql-server指令安装mysql后，你会发现你登录不上，会出现这样的情况。
