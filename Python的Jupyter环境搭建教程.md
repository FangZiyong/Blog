# Python的Jupyter环境搭建教程

作者：方自雍  QQ：1023597166

## Python安装

1. 从官网下载python安装包。[python下载地址](https://www.python.org/downloads/)，根据自己计算机的系统选择相应的安装包。教程以windows系统为例安装，[Windows x86-64 安装包下载](https://www.python.org/ftp/python/3.7.4/python-3.7.4-amd64.exe)
2. 双击刚刚下载的名为 **python-3.7.4-amd64** 的文件开始安装。

3. 选中最下面的Add Python 3.7 to PATH。
4. 对于熟悉Python安装的用户，可自定义需要安装的组件。对于小白直接点击**Install Now**即可。默认安装位置为：C:\Users\[你的用户名]\AppData\Local\Programs\Python ，如果有修改磁盘权限的确认，直接授予修改磁盘权限即可，点击 **是**，安装结束后关闭窗口。

## python库的安装

由于python默认安装的库不能完全满足需求，下面介绍python库的安装方法。python库有多种安装方法，仅介绍最简单的一种，通过**pip**安装，在之前安装python的时候，由于我们选择的是默认安装，因此已经包括了**pip**，我们直接使用即可。

### 更改python镜像源

python的默认镜像源在国外，用默认源的话下载速度非常慢，为了解决这个问题我们将源的地址更改为国内镜像，这一步操作将大幅度提高我们之后安装库的速度。

直接用户文件夹中创建一个pip文件夹，如：C:\Users\[你的用户名]\pip，在该文件夹中右键，新建文本文件，用记事本打开之后输入以下内容并保存。

```
[global]
index-url = https://pypi.tuna.tsinghua.edu.cn/simple
```

### 安装python库

1. 按下**win+R**键，在左下角打开一个小窗口，在其中输入**cmd**然后回车即可进入命令行窗口。
2. 在命令行输入**pip install 库名**，然后回车即可安装对应的库，下面以安装jupyter为例，输入如下代码之后

```
pip install jupyter
```

​		由于python的很多库都是需要依赖其他库的，所以安装所需要的时间因所有需要安装的库的数目和大小而定，在安装期间会有库的下载的进度条。

3. 当cmd窗口的最后一行变为

   ```
   C:\Users\[你的用户名]>
   ```

   时就代表该库安装完毕，可以使用了。

## Jupyter的使用

Jupyter是个编程环境，名字来源于三个字母，分别是Julia，Python，R，说明它可以为这三种编程语言提供编程环境。

1. 打开jupyter-notebook。jupyter-notebook位于python的安装目录下的Scripts中，如果是默认安装，则应该位于**C:\Users\[你的用户名]\AppData\Local\Programs\Python\Python37\Scripts**中，双击jupyter-notebook后会弹出一个黑色的窗口，不用管，稍等一会在你的默认浏览器打开一个网页，这里就是你的编程环境了。

2. 点击右上角的**New**，并选择**Python 3**，即可生成一个新的笔记本，并打开一个标签，接下来就可以在方格中输入python代码运行程序了。



一些问答：

1. 如何知道自己是否安装了某个库？

   答：最直接的方法，不管安装了没有，直接装就是了，按照上述的流程直接在命令行输入**pip install 库名**就行，没安装就会执行正常安装程序。如果安装了会出现如下信息告诉你已经安装了。

   ```
   Requirement already satisfied: 库名
   ```

2. 我在用别人的代码的时候怎么知道自己是不是因为缺少某个库的原因报错了？

   答：运行之后查看程序的报错。如果出现类似下面的报错就说明你没有安装某一个库。

   ```
   ---------------------------------------------------------------------------
   ModuleNotFoundError                       Traceback (most recent call last)
   <ipython-input-2-38d4b0363d82> in <module>
   ----> 1 import pandas
   
   ModuleNotFoundError: No module named 'pandas'
   ```

   这里的倒数第二行告诉我们，在我们的代码的第一行想要导入一个叫做pandas的库，但是最后一行就告诉我们，没有一个叫做pandas的库，我们就需要自己去按照上面的流程安装pandas库，然后就能正常运行了。

   总结就是，如果是因为缺少某一个库的原因报错，那么肯定会出现**ModuleNotFoundError: No module named '库名'**这样的报错。



