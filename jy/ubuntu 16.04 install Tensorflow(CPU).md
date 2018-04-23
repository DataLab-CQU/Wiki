# ubuntu 16.04 install Tensorflow(CPU)

1. 安装pip

    打开终端输入命令： sudo apt-get install python-pip python-dev

2. 安装tensorflow1.2.0

   sudo pip install tensorflow==1.2.0 -i 

   https://pypi.doubanio.com/simple

   遇到的问题：

   1.超时错误

   ![timeout](https://github.com/DataLab-CQU/Wiki/blob/master/jy/jy_markdown_pic/ubuntu_16.04_install_Tensorflow_CPU/timeout.png?raw=true)

   ​

​    ![timeout1](https://github.com/DataLab-CQU/Wiki/blob/master/jy/jy_markdown_pic/ubuntu_16.04_install_Tensorflow_CPU/timeout1.png?raw=true)



- 解决办法

  ​	用以下语句修改超时时间，命令中999999999999是我设置的超时时间

  ​	pip --default-timeout=999999999999 install -U pip

  ​        修改之后安装过程

  ![timeout2](https://github.com/DataLab-CQU/Wiki/blob/master/jy/jy_markdown_pic/ubuntu_16.04_install_Tensorflow_CPU/timeout2.png?raw=true)	

  ![tensorflow1](https://github.com/DataLab-CQU/Wiki/blob/master/jy/jy_markdown_pic/ubuntu_16.04_install_Tensorflow_CPU/tensorflow1.png?raw=true)

  ![tensorflow2](https://github.com/DataLab-CQU/Wiki/blob/master/jy/jy_markdown_pic/ubuntu_16.04_install_Tensorflow_CPU/tensorflow2.png?raw=true)

  ![tensorflow3](https://github.com/DataLab-CQU/Wiki/blob/master/jy/jy_markdown_pic/ubuntu_16.04_install_Tensorflow_CPU/tensorflow3.png?raw=true)

  下载完成

3.测试tensorflow

进入Python模式

输入以下语句

![tensorflow_test](https://github.com/DataLab-CQU/Wiki/blob/master/jy/jy_markdown_pic/ubuntu_16.04_install_Tensorflow_CPU/tensorflow_test.png?raw=true)

测试完成。

