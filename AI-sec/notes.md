# AI security 笔记
## 知识点
* 黑盒攻击，白盒攻击  
机器学习模型的内部构造
* 攻击的迁移性  
想对付 A 模型，只需要先用白盒攻击在 B 模型里找到一个对抗样本，再直接拿到 A 模型里使用，很多时候都能直接起效。
* 对抗训练  
提前用各种“对抗攻击”算法把自己的模型调教一遍，尽可能找出所有“对抗样本”，再把这些对抗样本扔进模型里，进行专项训练。
* 数据增强（训练过程）  
训练的时候就加入一些随机的噪声、噪点
* 特征挤压（运行过程）  
在识别一些数据时，人为给数据进行取整，这样就能避免掉一些小数位上的扰动

安全界四大顶会：
* USENIX Security
* IEEE Symposium on Security and Privacy
* ACM Conference on Computer and Communications Security
* The Network and Distributed System Security Symposium

## 学习计划
### 潘博 task
AI隐私中比较著名的攻击（大概的想法就是说怎么从各种DL的中间计算结果中窃取有用的情报）
1. model inversion attack: https://www.cs.cmu.edu/~mfredrik/papers/fjr2015ccs.pdf  
2. membership inference attack: https://www.cs.cornell.edu/~shmat/shmat_oak17.pdf  
3. property inference attack: http://seclab.illinois.edu/wp-content/uploads/2018/08/ganju2018property.pdf  
4. data reconstruction attack: https://arxiv.org/pdf/1904.01067.pdf / https://arxiv.org/abs/1906.08935 /   

AI安全的攻击（主要是让模型在训练过程中和预测过程中发生异常行为，从而误判）：
1. backdoor attack: Targeted Backdoor Attacks on Deep Learning Systems Using Data Poisoning （这篇是比较早的一篇探索如何给人脸识别用的神经网络加后门，让戴红色眼镜的人被分类成奇怪的物体的工作）  
2. Byzantine attack: https://arxiv.org/abs/1802.07927 (我们之前做的一篇拜占庭防御相关的工作就是发在安全的四大会议上，这篇是首次发现这种攻击方法的文章)  
3. Data poisoning attack:  https://arxiv.org/pdf/1703.04730.pdf （这个是一种给狗加上奇怪的噪声丢到训练集里导致模型把其他狗误判成鱼的方法）  
4. Adversarial Example: https://arxiv.org/abs/1412.6572 (对抗样本的最经典的工作)  

## Links
* AI-Security-Learning 下面两个资源同步更新：  
http://mang0.me/archis/eed6fa1/  
https://github.com/0xMJ/AI-Security-Learning

* Bridging Adversarial Robustness and Semi/Self/Un-supervised Learning  
一篇综述 https://zdhnarsil.github.io/files/submission_for_queer.pdf  
从 semi/self/un-supervised learning 的角度介绍增强对抗鲁棒性的训练方法。

* AI研究方向：对抗攻击研究前景怎么样？  
https://www.zhihu.com/question/359151065  
有很多的 topic paper 推荐。