#  神经网络 Neural Network

早期的神经网络，称之 感知机 Perceptron, 拥有输入层，输出层，隐含层。输入的特征向量通过隐含层变换达到输出层，在输出层得到分类结果

神经网络核心组件
神经网络看起来很复杂，节点很多，层数多，参数更多, 但核心部分或组件不多
1. 层：神经网络的基本结构，将输入张量转换为输出张量。
2. 模型：层构成的网络。
3. 损失函数：参数学习的目标函数，通过最小化损失函数来学习各种参数。
4. 优化器：如何使得损失函数最小，这就涉及到优化器。

> 核心组件不是独立的，它们之间、以及它们与神经网络其他组件之间有密切关系

## 3.2实现神经网络实例

使用Pytorch构建神经网络使用的主要工具（或类）及相互关系

```
            定义网络层            -->       构建网络     -->     前向传播    -->  反向传播                   -->  优化参数

            |-> Module               ________________
            |  |->   Linear          | nn.Sequential |       ________
            |  |->   Conv*      -->  | nn.ModuleList | -->  | forward |
            |  |->   *Norm           | nn.ModuleDict |      | Model() |  -->  torch.autograd.backward  -->  torch.optims.step
torch.nn -> |  |->   Adaptive*       |_______________|      | Loss()  |
            |  |->   *Loss
            |  ^
            |-> fuctional
            |-> parallel
            |-> init
```

nn中的大多数层（layer）在functional中都有与之对应的函数。nn.functional中函数与nn.Module中的layer的主要区别是后者继承Module类，会自动提取可学习的参数。而nn.functional更像是纯函数。两者功能相同，性能也没有很大区别

* 像卷积层、全连接层、dropout层等因含有可学习参数，一般使用nn.Module
* 而激活函数、池化层不含可学习参数，可以使用nn.functional中对应的函数


## Hub模块

[Github](http://github.com/pytorch/hub)
[模型](http://pytorch.org/hub/research-models)
