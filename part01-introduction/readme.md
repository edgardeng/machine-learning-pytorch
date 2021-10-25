# Pytorch 的介绍和应用

 
 1. Pytorch 基础 （张量和向量）
 2. Pytorch 数据集
 3. transform 数据转化
 4. autograd 自动求导
 5. nn.functional 和 nn.Module 
 6. 激活函数 Activation Function


## Tensor的使用

#### PyTorch由4个主要包组成

* torch：类似于Numpy的通用数组库，可将张量类型转换为torch.cuda.TensorFloat，并在GPU上进行计算。
* torch.autograd：用于构建计算图形并自动获取梯度的包。
* torch.nn：具有共享层和损失函数的神经网络库。
* torch.optim：具有通用优化算法（如SGD，Adam等）的优化包。

### Tensor的数据类型

* 32位浮点型：torch.FloatTensor (Tensor默认的数据类型)
* 64位浮点型：torch.DoubleTensor
* 16位整型：torch.ShortTensor
* 32位整型：torch.IntTensor
* 64位整型：torch.LongTensor
* 布尔类型：torch.BoolTensor

###  类型转换

1. 数据类型转换
    * 在Tensor后加 .long(), .int(), .float(), .double()等即可，也可以用.to()函数进行转换，所有的Tensor类型可参考https://pytorch.org/docs/stable/tensors.html
2. 数据存储位置转换
    * CPU张量 ---->  GPU张量，使用data.cuda()
    * GPU张量 ----> CPU张量，使用data.cpu()
3. 与numpy数据类型转换
    * Tensor---->Numpy  使用 data.numpy()，data为Tensor变量
    * Numpy ----> Tensor 使用 torch.from_numpy(data)，data为numpy变量
4. 与Python数据类型转换
    * Tensor ----> 单个Python数据，使用data.item()，data为Tensor变量且只能为包含单个数据
    * Tensor ----> Python list，使用data.tolist()，data为Tensor变量，返回shape相同的可嵌套的list

###  Tensor的创建

|函数|描述|
|:----|:----|
| Tensor | 直接从参数构造一个张量，支持list，ndarray
| eye(row,column) | 创建指定行数，列数的二维单位tensor
| linspace(start,end,step) | 从step到end，均匀切分成 steps份
| logspace(start,end,step) | 10^step 到 10^end，均匀切分steps份
| rand / randn(*size) | 生产[0,1) 均匀分布/标准正态分布数据
| ones(*size) | 返回指定shape的张量，元素初始为1
| zeros(*size) | 返回指定的shape的张量，元素初始为0
| ones_like(t)| 返回t的shape的张量，元素初始为1
| zeros_like(t)| 返回t的shape的张量，元素初始为0
| arrange(start,end,step)| 在区间[start，end]上以间隔step生成一个序列张量
| from_numpy(ndarray) | 从ndarray创建tensor

> 【说明】注意torch.Tensor与torch.tensor的几点区别
1. torch.Tensor是torch.empty和torch.tensor之间的一种混合，但是，当传入数据时，torch.Tensor使用全局默认dtype（FloatTensor），torch.tensor从数据中推断数据类型。
2. torch.tensor(1)返回一个固定值1，而torch.Tensor(1)返回一个大小为1的张量，它是随机初始化的值。


## Tensor的比较
> Tensor本身就可以进行一些比较, 更详细的资料大家可以去阅读官方文档。

* 等于 torch.equal(tensor1, tensor2) → bool
  > 如果两个张量的尺寸和元素都相同，则返回True，否则返回False。
* 大于 torch.gt(input, other, out=None) → Tensor
* 大于等于 torch.ge(input, other, out=None) → Tensor

## Pytorch的算法实现和应用场景

预训练语言模型 GPT2


