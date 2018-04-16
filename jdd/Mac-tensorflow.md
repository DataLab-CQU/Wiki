# Mac 安装Tensorflow(CPU,python3.6)

## 安装anaconda

安装好Anaconda后，需要创建一个虚拟工作环境，使用Anaconda能创建自己的计算环境，相当于将tensorflow的环境与其他环境做了隔离，这样你就可以随便玩tensorflow也不用担心破坏之前的环境！ 

```
$ conda create -n tensorflow python=3.6
```

创建了tensorflow的隔离环境后，要做的是激活tensorflow环境，然后用pip安装TensorFlow

```
$ source activate tensorflow 
```

## 安装TensorFlow

虽然TensorFlow支持从conda直接安装，但是google同时也声明，conda并没有得到官方的支持，Google还是推荐通过pip来安装，因为我已经用了python3.6 所以需要安装 pip3， 在安装pip3的过程中遇到了一些问题，anaconda中安装的pip的确是最新的，但是后面如果使用pip安装tensorflow，就会选择自动适配Python2.7，这里也是耽误我最多时间的过程，随后找到了一个解决方案，与大家分享一下：http://vinyll.scopyleft.fr/install-python3-and-pip-on-a-mac-os/ 也就是说,anaconda 并没有pip3的引用，你需要自己创建一个pip3的软连接，这样你就可以使用pip3了。后面也的确证实，只有pip3才能够适配Python3.6来安装tensorflow。

```
$ ln -s /Users/xa/anaconda3/bin/pip /Users/xa/anaconda3/bin/pip3
```

我安装的pip版本相对较高，Google安装文档建议使用pip3命令来安装TensorFlow TensorFlow需要的所有包进入被激活的Virtualenv环境:

```
$ pip3 -V
```

结果显示：

pip 9.0.1 from /Users/weijun/anaconda3/lib/python3.6/site-packages (python 3.6)

 

```
$ pip3 install --upgrade tensorflow

 $ pip3 install --upgrade \
 https://storage.googleapis.com/tensorflow/mac/cpu/tensorflow-1.0.1-py3-none-any.whl
```

 接下来就是等待了，如果你有代理，亦或者足够幸运的话，2分钟就可以搞定tensorflow的安装过程。

## 测试一下我们安装的Tensorflow

1.首先保证你是在激活的虚拟环境中，也就是我们第一步骤中提及的

2.启动python3.6

3.输入以下代码进行测试

```
>>>import tensorflow as tf

>>>node1 = tf.constant(3.0, tf.float32)

>>>node2 = tf.constant(4.0)

>>>print(node1, node2)
```

结果显示：Tensor("Const:0", shape=(), dtype=float32) Tensor("Const_1:0", shape=(), dtype=float32)

```
>>> sess = tf.Session()
```

结果显示：W tensorflow/core/platform/cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use SSE4.1 instructions, but these are available on your machine and could speed up CPU computations.
W tensorflow/core/platform/cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use SSE4.2 instructions, but these are available on your machine and could speed up CPU computations.
W tensorflow/core/platform/cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use AVX instructions, but these are available on your machine and could speed up CPU computations.
W tensorflow/core/platform/cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use AVX2 instructions, but these are available on your machine and could speed up CPU computations.
W tensorflow/core/platform/cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use FMA instructions, but these are available on your machine and could speed up CPU computations.

```
>>> print(sess.run([node1, node2]))
```

结果显示：[3.0, 4.0] 

**至此tensorflow 基于Python3.6就算安装成功了！**

