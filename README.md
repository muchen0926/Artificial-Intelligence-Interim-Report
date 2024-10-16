# Google Colab 部署自己的机器学习项目

目录

1. 介绍

2.准备工作

3.步骤

  3.1 进入 google driver：https://drive.google.com

  3.2 右键上传项目所在的文件夹：

  3.3 进入 colab：点击左上角 “新建” --> “更多” --> “Colaboratory”

  3.4 “Edit” --> “Notebook settings” -->

  3.5 代码段里面输入

  3.6 代码段里面输入

  3.7 代码段里面输入

4 注意事项

  3.1 进入 google driver：https://drive.google.com
  
  3.2 右键上传项目所在的文件夹：
  
   ![image]()
   ![image]()
   ![image]()
   我这里简单地上传了一个名为 test 的文件夹，里面只有一个 main.py 的文件，代码也很简单，但是可以简单测试 Pytorch 的使用。
  3.3 进入 colab：点击左上角 “新建” --> “更多” --> “Colaboratory”
   ![image]()
   ![image]()
  3.4 “Edit” --> “Notebook settings” -->
   ![image]()
   这里我选择的 Python3 （根据自己代码依赖的环境） 和 GPU，如果要用 GPU 这一步必须调整好。每次调整这里的设置，后面的步骤都要再次进行。所以推荐这里设置好
   ![image]()
  3.5 代码段里面输入

       from google.colab import drive
       drive.mount(’/content/drive/’)
   
   然后点击左侧的运行图标，或者 Ctrl + Enter 运行。这时候会出现
   ![image]()
   点击 URL 进入，授权 Google 用户，然后复制授权码粘贴到输入框，Enter。这个时候回显示挂载成功
   ![image]()
   这里可以输入

       !ls

   ![image]()
   可以看到此目录下文件。
  3.6 代码段里面输入

       import os
       os.chdir(“drive/My Drive/test”)

   最后一个 test 是其实是自己的项目名。这个时候没有任何提示信息，因为是 Linux 内核，所以按照 Linux 的思想：没有消息就是最好的消息。说明一切顺利。
这里可以输入

       !ls
   
   ![image]()
  可以看到我们写的 main.py 文件。

  3.7 代码段里面输入

      !python main.py

![image]()

成功搞定~
  
4 注意事项

1. 介绍
Google Colab提供的是免费Tesla K80 GPU，可以玩Keras、Tensorflow、PyTorch或者Mxnet等。Tesla K80还是一块比较高性能的GPU。主要是免费，免费，免费 ！！！ 好像这次真的薅资本主义羊毛了，个人试了几天，感觉还不错。刚入手的时候稍微有点麻烦，大部分的网上教程都是在 Colab 上手动写代码玩玩儿，但是我是自己在本地写好了一个小的项目，然后相互之间 import 有点麻烦，最后自己摸索总结出了一套最简单的上传自己项目，用 colab 跑出结果的方法。

2.准备工作
谷歌一系列，所以先得出去
注册一个谷歌账号
用自己的谷歌账号使用 google driver
自己的项目在本地调试通过，放在一个文件夹里面（包含数据集，最好是英文名字）

3.步骤
3.1 进入 google driver：https://drive.google.com
3.2 右键上传项目所在的文件夹：

3.3 进入 colab：点击左上角 “新建” --> “更多” --> “Colaboratory”
3.4 “Edit” --> “Notebook settings” -->
3.5 代码段里面输入
3.6 代码段里面输入
3.7 代码段里面输入
4 注意事项
1.虽然是 Linux 内核，但是每次类似于 Linux 的语句之前要多一个 “!” 。比如步骤 3.6， 3.7
2.步骤 3.6 第二个语句最后一个路径名称根据自己上传到 Google Driver 的文件夹的名字而定，我上传的是 “test ”，所以最后一个路径是“test”。

