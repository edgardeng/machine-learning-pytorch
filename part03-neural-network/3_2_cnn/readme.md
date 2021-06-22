# 卷积神经网络(Convolutional Neural Network)
> CNN 是深度学习技术中极具代表的网络结构之一，在图像处理领域取得了很大的成功，在国际标准的ImageNet数据集上，许多成功的模型都是基于CNN的。

卷积神经网络CNN的结构一般包含这几个层：

 * 输入层：用于数据的输入
 * 卷积层：使用卷积核进行特征提取和特征映射
 * 激励层：由于卷积也是一种线性运算，因此需要增加非线性映射
 * 池化层：进行下采样，对特征图稀疏处理，减少数据运算量。
 * 全连接层：通常在CNN的尾部进行重新拟合，减少特征信息的损失
 * 输出层：用于输出结果

### 示例: MNIST 手写数字识别

```python
import torch.nn as nn
import torch.nn.functional as F
class Net(nn.Module):
    def __init__(self):
        super(Net, self).__init__()
        # 输入1通道，输出10通道，kernel 5*5
        self.conv1 = nn.Conv2d(1, 10, kernel_size=5)
        self.conv2 = nn.Conv2d(10, 20, kernel_size=5)
        self.poll = nn.MaxPool2d(2)
        self.fc = nn.Linear(320, 10) # fully connect

    def forward(self, x): 
        x = F.relu(self.mp(self.conv1(x))) # x: 64*10*12*12
        x = F.relu(self.mp(self.conv2(x))) # x: 64*20*4*4 
        x = x.view(x.size()[0], -1) # 64*320 flatten the tensor
        x = self.fc(x) # x: 64*10
        return F.log_softmax(x)
```
