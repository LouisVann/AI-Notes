# RNN 学习笔记

> [RNN到LSTM详解](https://blog.csdn.net/weixin_41923961/article/details/87885322)  
![RNN结构](https://img-blog.csdnimg.cn/20190222204705112.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyMzk2MQ==,size_16,color_FFFFFF,t_70)  
标准RNN的还有以下特点：  
1、权值共享，图中的W全是相同的，UU和VV也一样。  
2、每一个输入值都只与它本身的那条路线建立权连接，不会和别的神经元连接。</br>  
RNN的训练方法BPTT（back-propagation through time）</br>  
RNN的一个变种：**N vs M**。这种结构又叫**Encoder-Decoder**模型，也可以称之为**Seq2Seq**模型。  
**LSTM**（long short-term memory）。长短期记忆网络是RNN的一种变体，RNN由于梯度消失的原因只能有短期记忆，LSTM网络通过精妙的门控制将短期记忆与长期记忆结合起来，并且一定程度上解决了梯度消失的问题。  
![LSTM结构图](https://pic3.zhimg.com/80/v2-b3db4ade55bc96d6a3ca3d630ded4c22_1440w.jpg)  
这三个门虽然功能上不同，但在执行任务的操作上是相同的。他们都是使用sigmoid函数作为选择工具，tanh函数作为变换工具，这两个函数结合起来实现三个门的功能。  
LSTM 变体之 **GRU**  
![GRU结构图](https://img-blog.csdnimg.cn/20190222210237657.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTkyMzk2MQ==,size_16,color_FFFFFF,t_70)