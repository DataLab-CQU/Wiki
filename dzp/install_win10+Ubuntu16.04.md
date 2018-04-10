# 双系统安装 win10 + Ubuntu16.04

配置：华硕笔记本 Nvidia950 

目标：win10 + Ubuntu16.04

参考链接：

1. 安装教程参考 https://zhuanlan.zhihu.com/p/31271077 

  注意：

  - 该安装教程中BIOS设置中缺少一项，除了将Fast Boot关闭，还必须将Secure Boot设置为Disabled


  - 在进行Linux分区完准备安装时，一定要注意 **安装启动引导的设备 是否是你的boot分区**

2. 解决显卡安装问题参考 https://blog.csdn.net/kilotwo/article/details/79258107

**请务必先仔细阅读完参考链接1和2才进行具体安装**



## 关于安装Linux分区的几个解释

- /boot           Ext4 逻辑分区    *该分区主要是用来安装Linux相关的启动程序，一般200M*
- /                   Ext4 主分区        *根分区，类似于Windows下面刚刚装好时在C盘下面的所有文件*
- /home         Ext4 逻辑分区    *该分区下面包含着各种用户*
- swap             Ext4 逻辑分区   *内存不足情况下将其作为虚拟内存使用，一般为内存大小的1.5~2倍之间*