# Pytorch 的介绍和应用

## Tensor的使用

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

### 特殊tensor

* torch.zeros
* torch.ones
* torch.arange 根据start与stop指定的范围以及step设定的步长，生成一个array

## Tensor的比较
> Tensor本身就可以进行一些比较, 更详细的资料大家可以去阅读官方文档。

* 等于 torch.equal(tensor1, tensor2) → bool
  > 如果两个张量的尺寸和元素都相同，则返回True，否则返回False。
* 大于 torch.gt(input, other, out=None) → Tensor
* 大于等于 torch.ge(input, other, out=None) → Tensor

## Pytorch的算法实现和应用场景

预训练语言模型 GPT2


