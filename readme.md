# About
《共享噪音》（Noise Maker）是我做的一个基于Tensorflow的自动生成儿歌的作品。

[点此试听Noise Maker生成的音乐](http://v.youku.com/v_show/id_XMzE1MTU3NTUzNg==.html?spm=a2hzp.8244740.0.0)

如果大家觉得我这个程序做的不错，就请多多star+关注+分享哦！

# 程序运行方法
* 安装依赖包
```
pip3 install -r whl_is_sb.txt
```
* 运行前的准备
首先需要新建几个文件夹
```
mkdir Diary
mkdir Diary/Generate
mkdir Diary/Train
mkdir TrainData
mkdir TrainData/TfLog
mkdir TrainData/TfLog/sess
```
* 训练样本并生成一段测试音乐
```
python3 main.py --outputpath=<希望音乐输出的路径和文件名>
```

示例
```
python3 main.py --outputpath=../output096.mid
```
* ```settings.py```里面有一个变量```FLAG_IS_DEBUG```。这个变量为True时，训练时间在十分钟左右，但是有比较高的概率会生成一段很烂的音乐。当这个变量为False时，训练时间在一小时左右，但是生成的音乐质量会稍微高一些。
* 运行结束之后，会发现你输入outputpath的位置多了一个mid文件，这个文件就是生成的音乐哦。
* 另外，```settings.py```里面还有一个变量```GENERATE_WAV```，这个变量是用于控制是否生成wav文件的。不过如果想生成wav文件需要额外安装一些库，比较麻烦，所以建议将这个变量设为False。

# 作品简述

* 生成音乐所使用到的主要算法是LSTM、HMM、K-Means和Naive Bayes。
* 目前的这个版本（0.96）可以生成一个带有主旋律，和弦，同时包含了鼓点、bass、钢琴、弦乐和加花五种音色的伴奏。
* 和前一版本相比，这个版本增加了前奏、间奏，伴奏和主旋律的搭配要更和谐一些，且主旋律有一定的层次感，听起来会更像是一首完整的歌曲，而不是一个简单的段落。
* 关于工程文件：code文件夹里面的是源代码，Diary保存了程序运行时生成的日志，TrainData文件夹保存了训练时生成的中间文件（如Tensorflow生成的文件），以及midi音乐按一定规则编码之后存储的sqlite3数据文件。
* 关于数据：我从网上找了169首儿歌作为训练样本。因为儿歌的midi文件比较好下载到，而且儿歌的主旋律/和弦走向/鼓点等都相对比较简单，所以在这个版本中，我选择了儿歌作为训练样本。
* 这个东西接下来应该会有续作。对它有什么批评意见的话可以联系我，我还是很乐意听到改进意见的。

# Q/A

* 如果程序不能运行出bug怎么办？
    * 跟我反馈。
* 生成的音乐太难听无法忍受怎么办？
    * 当然是选择原谅它。
