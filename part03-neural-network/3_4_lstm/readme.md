## 长短时记忆网络(LSTM)


### Sequence Prediction

> 序列预测包括预测给定输入序列的下一个值 
  Input Sequence: 1, 2, 3, 4, 5
  Output Sequence: 6


一些序列预测问题的例子包括：

 * 天气预报。根据一段时间内对天气的一系列观察，预测明天的天气。
 * 股市预测。 给定安全性随时间推移的一系列运动，请预测安全性的下一个运动。
 * 产品推荐。 给定客户过去的购买顺序，请预测客户的下一次购买。

### Sequence Classification
> 序列分类涉及到预测给定输入序列的类标签。例如:
  Input Sequence: 1, 2, 3, 4, 5
  Output Sequence: "good"

分类问题的例子包括:

 * DNA序列分类。给定a、C、G和T值的DNA序列，预测该序列是编码区还是非编码区。
 * 异常检测。 给定一系列观察结果，请预测该序列是否异常。
 * 情感分析。 给定一系列文本（例如评论或推文），预测文本的情绪是正面还是负面。

### Sequence Generation
序列生成包括生成与语料库中的其他序列具有相同一般特征的新输出序列。例如:

> Input Sequence: [1, 3, 5], [7, 9, 11]
Output Sequence: [3, 5 ,7]

序列生成问题的例子包括：

 * 文字生成。 给定一个文本语料库（例如莎士比亚的作品），生成新的句子或文本段落，阅读它们可能是从该语料库中提取的。
 * 手写预测。 给定一个手写示例的语料库，为具有语料库中笔迹特性的新短语生成笔迹。
 * 音乐生成。 给定一个音乐实例集，生成具有该音乐集特性的新音乐作品。 
 * 图像标题生成。 给定图像作为输入，生成描述图像的单词序列 
 > 序列的产生也可以指代给定单个观察作为输入的序列的产生
 
### Sequence-to-Sequence Prediction
序列到序列的预测涉及到给定输入序列的输出序列的预测。例如:

Input Sequence: 1, 2, 3, 4, 5
Output Sequence: 6, 7, 8, 9, 10

序列间问题的一些示例包括：

多步时间序列预测。 给定一个时间序列的观测值，可以预测一系列未来时间步长的观测值序列。
文字摘要。 给定一个文本文件，该文件描述了源文件的重要部分。
程序执行。 给定文本描述程序或数学方程式，可以预测描述正确输出的字符序列。


LSTM Weights
记忆单元（memory cell）具有用于输入，输出以及通过暴露于输入时间步长而建立的内部状态的权重参数。

输入权重。用于对当前时间步长的输入进行加权。
输出权值。用于对最后一个时间步的输出进行加权。
内部状态（Internal State）。内部状态用于计算此时间步长的输出。
1.4.2 LSTM Gates
记忆单元的关键是门（gate）。这些都是加权函数，进一步控制单元中的信息流。有三个门:

Forget Gate（遗忘门）：决定从单元中丢弃哪些的信息。
Input Gate（输入门）：决定哪些输出的值去更新记忆状态。
Outut Gate（输出门）：根据输入和记忆单元确定输出什么。
遗忘门和输入门用于内部状态的更新。输出门是单元实际输出内容的最终限制器。这些门和被称为constant error carrousel（CEC）的一致的数据流使每个单元保持稳定(既不爆炸也不消失)。

LSTMs的三个主要优点：

 * 克服了训练RNN的技术问题，即梯度消失和爆炸。
 * 具有记忆，以克服长期时间依赖与输入序列的问题。
 * 按时间步长处理输入序列和输出序列，允许可变长度的输入和输出。

### LSTMs的应用

1. Automatic Image Caption Generation 自动图像字幕
2. Automatic Translation of Text 自动文本翻译
3. Automatic Handwriting Generation 手写识别


### 有关LSTM的必读文章。
 
Sequence on Wikipedia.
https://en.wikipedia.org/wiki/Sequence

On Prediction Using Variable Order Markov Models, 2004 .

Sequence Learning: From Recognition and Prediction to Sequential Decision Making, 2001 .

Chapter 14, Discrete Sequence Classification, Data Classification: Algorithms and Applications,2015.
http://amzn.to/2tkM723

Generating Sequences With Recurrent Neural Networks, 2013.
https://arxiv.org/abs/1308.0850

Show and Tell: A Neural Image Caption Generator, 2015 .
https://arxiv.org/abs/1411.4555

Multi-task Sequence to Sequence Learning, 2016 .
https://arxiv.org/abs/1511.06114

Sequence to Sequence Learning with Neural Networks, 2014 .
https://arxiv.org/abs/1409.3215

Recursive and direct multi-step forecasting: the best of both worlds, 2012. 

Show and Tell: A Neural Image Caption Generator, 2 0 1 4 .
https://arxiv.org/abs/1411.4555

Sequence to Sequence Learning with Neural Networks, 2 0 1 4 .
https://arxiv.org/abs/1409.3215

Generating Sequences With Recurrent Neural Networks, 2 0 1 4 .
https://arxiv.org/abs/1308.0850

