# 机器学习
> 给你一个全新的数据，通过对以往的数据的认识，对这个全新的数据进行预测

## 机器学习流程

 * 数据获取
   
 * 特征工程
   
 * 建立模型
   
 * 评估与应用

### 特征提取方法

## 学习目录

1. [Linear Regression](2_1_linear_regression.ipynb)

2. [Logistic Regression](2_2_logistic_regression.ipynb)
   
3. [K Nearest Neighbours](2_3_KNN.ipynb)

4. [SVM](2_6_svm.ipynb)

5. [Naive Bayes](2_3_naive_bayes.ipynb)

6. [Decision Trees ](2_4_decision_trees.ipynb)

7. [Random Forest](2_5_random_forest.ipynb)

8. [K-Means](2_7_kmeans.ipynb)

9. [Perceptron 感知机](2_9_perceptron.ipynb)

10. [GBDT 梯度提升树](2_10_gbdt.ipynb) Gradient Boosting Decision Tree

11. [XGBoost  极度梯度提升树](2_11_xgboost.ipynb) eXtreme Gradient Boosting 

##  十大经典机器学习算法
[](https://blog.csdn.net/jrunw/article/details/79205322)

1. 决策树
 > 根据一些 feature（特征） 进行分类，每个节点提一个问题，通过判断，将数据分为两类，再继续提问。这些问题是根据已有数据学习出来的，再投入新数据的时候，就可以根据这棵树上的问题，将数据划分到合适的叶子上。

2. 随机森林
 > 在源数据中随机选取数据，组成几个子集,M个子集得到 M 个决策树：将新数据投入到这M个树中，得到M个分类结果，

3. 逻辑回归
 > 当预测目标是概率这样的，值域需要满足大于等于0，小于等于1的，这个时候单纯的线性模型是做不到的，因为在定义域不在某个范围之内时，值域也超出了规定区间。

 > 这个模型需要满足两个条件 “大于等于0”，“小于等于1” 。大于等于0 的模型可以选择绝对值，平方值，这里用指数函数，一定大于0；小于等于1 用除法，分子是自己，分母是自身加上1，那一定是小于1的了。
 再做一下变形，就得到了 logistic regressions 模型：

4. 支持向量机
 > 将两类分开，想要得到一个超平面，最优的超平面是到两类的 margin 达到最大，margin就是超平面与离它最近一点的距离

5. 朴素贝叶斯 
   
6. K近邻算法
   
7. K均值算法
   
8. Adaboost
 > Adaboost 是 Boosting 的方法之一。Boosting就是把若干个分类效果并不好的分类器综合起来考虑，会得到一个效果比较好的分类器。

9. 神经网络
 > Neural Networks适合一个input可能落入至少两个类别里：NN由若干层神经元，和它们之间的联系组成。 第一层是input层，最后一层是output层。在hidden层和output层都有自己的classifier。

10. 马尔科夫
 > Markov Chains由state（状态）和transitions（转移）组成。
 

## 监督与非监督学习

#### 监督学习：
> 给定一个包含正确答案的数据集，通过此数据集预测出另一个参数对应的正确答案。

  * 回归问题，即有连续的预测数值输出。例：房价与面积关系。
  * 分类问题，预测离散值输出。例：肿瘤是良性还是恶性。 
  * 监督学习：结构化信息即有定义的信息如年龄面积广告数等。

#### 无监督学习

> 数据集没有标签，或都具有相同标签，我们不知道数据集是什么，用来干什么，能在其中自动找到某种结构吗？
> 无监督算法可能判定数据集包含不同的簇，即聚类算法

 * 基于概率密度函数估计的直接方法
 * 基于样本间相似性度量的简洁聚类方法

