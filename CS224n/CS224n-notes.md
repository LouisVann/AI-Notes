# 斯坦福 CS224n 学习笔记
## 资源链接
b站上 cs224n 资源众多，强烈安利这个系列，双语字幕可选 [2019斯坦福公开课CS224N（可选字幕版）](https://www.bilibili.com/video/BV1r4411f7td?from=search&seid=3191173693102486488)  

课程官网 [CS224n: Natural Language Processing with Deep Learning](http://web.stanford.edu/class/cs224n/index.html)  

> NEU 大佬 徐啸 https://looperxx.github.io/ 的笔记：  
**[CS224n-2019 笔记列表](https://zhuanlan.zhihu.com/p/68502016)**  
https://github.com/LooperXX/CS224n-Resource  
https://github.com/LooperXX/CS224n-Reading-Notes  

## 学习计划
* 学习笔记无需费力整理，可参考 looperxx 的笔记进行学习
* 对于每个 lecture，电子资源包括：
   * Video && Lecture slides
   * Demo code
   * Supplementary notes
   * Suggested readings
   * Assignment  
* 打算在 round 1 学习 Video && Lecture slides 和 Demo code，其余部分留到 round 2 进行仔细学习

## 打卡
日期 | 内容 | 课程主题
:-- | :-- | :--
2020.06.18 | Lecture 01 Video | NLP introduction, word vectors
2020.06.20 | Lecture 02 Video, SVD, LSA | word vectors, polysemy
2020.06.25 | Lecture 03 Video | word window classification, neural networks, matrix calculus
2020.06.26 | Lecture 04 Video | BP, computation graphs
2020.06.28 | Lecture 05 Video | context-free grammar (CFG), dependency parsing, transition-based parsing
2020.06.29 | Lecture 06 Video, MRF, CRF | language models, RNNs
2020.06.30 | Lecture 07 Video | vanishing/exploding gradient problem, LSTM and GRU, Bidirectional RNNs, Multi-layer RNNs
2020.07.02 | Lecture 08 Video | machine translation (SMT statistical & NMT neural), attention

## Appendix
### 1. SVD 矩阵分解
> 参考网址：  
https://blog.csdn.net/zpalyq110/article/details/86751064  
https://blog.csdn.net/zpalyq110/article/details/86751064  
https://www.cnblogs.com/marsggbo/p/10155801.html  

特征值分解 EVD eigenvalue decomposition  
奇异值分解 SVD singular value decomposition  
任意方阵，不同特征值对应的特征向量必然线性无关，但是不一定正交。  
对称矩阵，不同特征值对应的特征向量不仅线性无关，而且是相互正交的。  
针对维度为 mxn 矩阵的分解方法，就是 SVD。  
$$
A_{m*n} = U_{m*m} \Sigma_{m*n} {V^T}_{n*n}
$$
可以进行降维，提取最大的k个特征，得到：
$$
A_{m*n} \approx U_{m*k} \Sigma_{k*k} {V^T}_{k*n}
$$ 

### 2. LAS latent semantic analysis 潜在语义分析
> [通俗理解潜在语义分析LSA](https://www.jianshu.com/p/9fe0a7004560)  
LSA和传统向量空间模型(vector space model)一样使用向量来表示词(terms)和文档(documents)，并通过向量间的关系(如夹角)来判断词及文档间的关系；不同的是，LSA 将词和文档映射到潜在语义空间，从而去除了原始向量空间中的一些“噪音”，提高了信息检索的精确度。

### 3. 训练算法
1. BGD (batch gradient descent)
2. SGD (stochastic gradient descent)
3. MBGD (mini-batch gradient descent)
4. SGD-M (Momentum)
5. NAG (Nesterov accelerated gradient)
6. Adagrad
7. AdaDelta/RMSprop ??
8. Adam
9. NAdam (Adam + Nesterov)

https://zhuanlan.zhihu.com/p/32230623  
https://zhuanlan.zhihu.com/p/32626442  
https://blog.csdn.net/fishmai/article/details/52510826  

### 4. 概率图模型
> [概率图之马尔可夫随机场（Markov Random Field，MRF）](https://blog.csdn.net/hohaizx/article/details/82868843)  
根据图是有向还是无向，**概率图模型**可以分为两类：  
第一类使用有向无环图表示变量之间的因果关系，称为**有向图模型**或**贝叶斯网络**（Bayesian network）；  
另一类使用无向图表示变量之间的相关关系，称为**无向图模型**或马尔可夫网（Markov network），**马尔可夫随机场**（Markov Random Field，**MRF**）。

生成式 generative 模型，探索概率联合分布，$P(Y, R, O)$;  
判别式 discriminative 模型，探索概率的条件分布，$P(Y,R|O)$；

MRF 具有：全局马尔科夫性、局部马尔科夫性、成对马尔科夫性

**CRF conditional random field 条件随机场**：  
定义 **转移特征函数 transition feature function** 和 **状态特征函数 status feature function**。  
CRF 的公式推导：[CRF 条件随机场 概述](https://www.jianshu.com/p/5d6a03c1f83f)

### 5. Network Models
#### 5.1 ResNet
Residual connections aka **ResNet**, also known as **skip-connections**  
核心是增加了一个 identity connection，即 $F(x)+x$