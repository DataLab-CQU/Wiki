# ubuntu 16.04 install Tensorflow(CPU)

1. 安装pip

    打开终端输入命令： sudo apt-get install python-pip python-dev

2. 安装tensorflow1.2.0

   sudo pip install tensorflow==1.2.0 -i https://pypi.doubanio.com/simple

   遇到的问题：

   1.超时错误

   ![timeout](/home/jy/Pictures/timeout.png)

​           ![timeout1](/home/jy/Pictures/timeout1.png)

- 解决办法

  ​	用以下语句修改超时时间，命令中999999999999是我设置的超时时间

  ​	pip --default-timeout=999999999999 install -U pip

  ​        修改之后安装过程

  ![timeout2](/home/jy/Pictures/timeout2.png)	

  ![tensorflow1](/home/jy/Pictures/tensorflow1.png)

  ![tensorflow2](/home/jy/Pictures/tensorflow2.png)

  ![tensorflow3](/home/jy/Pictures/tensorflow3.png)

  下载完成

3.测试tensorflow

进入Python模式

输入以下语句

![tensorflow_test](/home/jy/Pictures/tensorflow_test.png)

测试完成。

