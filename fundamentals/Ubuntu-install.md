# Ubuntu双系统安装
参考了三篇博客，进行第二个系统的安装：  
* [win10下安装Ubuntu16.04双系统](https://blog.csdn.net/s717597589/article/details/79117112/)
* [Windows10安装ubuntu16.04双系统教程](https://www.cnblogs.com/masbay/p/10844857.html)
* [手把手教你安装win10+Ubuntu16.04的双系统（全网最详细）](https://blog.csdn.net/weixin_40787712/article/details/89944144)

## 安装前的准备
使用 软碟通（UltraISO） 进行硬盘的刻录。  
下面是分区的具体参数：（参考 https://www.jianshu.com/p/d79821e9fdbe）  
分区 | 空间
-- | --:
/: 主分区 | 20GB
swap 分区 | 16GB
/boot 分区 | 200MB
/home 分区 | 剩余空间
**总计**| **60GB**

其中，/boot 分区作为安装启动引导器的设备。
> /：存储系统文件，建议10GB ~ 15GB；  
swap：交换分区，即Linux系统的虚拟内存，建议是物理内存的2倍；  
/home：home目录，存放音乐、图片及下载等文件的空间，建议最后分配所有剩下的空间；  
/boot：包含系统内核和系统启动所需的文件，实现双系统的关键所在，建议200M。

建议初始的安装过程中先 skip 一些步骤，然后把下载源替换为 阿里云。  

## 安装后的配置
在 Ubuntu 里面安装 QQ 和 微信，参考：[Ubuntu下安装QQ微信——亲测试有效！](https://blog.csdn.net/wls666/article/details/101977113)  
**安装来源：[星外之神 / deepin-wine-for-ubuntu](https://gitee.com/wszqkzqk/deepin-wine-for-ubuntu)**  
> 2008年出现了一种名为wine的技术，这种技术在Linux平台实现了部分Windows的系统API和库，让用户可以在Linux端无缝使用Windows端的应用程序。  
后来国内深度社区将wine做了很好的封装并且在wine上移植了诸多windows端的软件。包括QQ、微信等等，而且在功能上几乎都可以和windows原版分庭抗礼，给广大Linux桌面版用户提供了极大地便利。  
2019年11月8日旧版的QQ被停止使用，也是同一天，深度就发布了新的Wine版QQ提供支持。在国内的阿里源、清华源等镜像源中也可以下载到最新版本。  
版权声明：本文为CSDN博主「三级狗」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。  
原文链接：https://blog.csdn.net/Three_dog/article/details/103017873

关于开机时 boot manager 的等候时间，可以通过在 Ubuntu 里面设置 GRUB_TIMEOUT 进行调整：`sudo vim /etc/default/grub`  

一些问题的解决方法：（来自 https://blog.csdn.net/weixin_40787712/article/details/89944144）  
> Pro1：安装ubuntu的时候由于分辨率问题，导致安装界面显示不全（如图），没法继续安装
https://zhidao.baidu.com/question/522177686034499645.html?word=Ubuntu安装过程中分辨率不兼容  
Pro2：最后的引导问题：
https://blog.csdn.net/u014422976/article/details/80393841  
Pro3：装Ubuntu老停在ubuntu界面
https://zhidao.baidu.com/question/923767939677091819?g_f=11301026&word=装Ubuntu老停在ubuntu界面  
Pro4：ubuntu 安装完成后重启电脑报错: BUG soft lockup 的解决办法
https://blog.csdn.net/xrinosvip/article/details/80447139  
Pro5: 解決搜狗输入法无法安装的问题：
https://blog.csdn.net/qq_22186119/article/details/70316727  
Pro6: ubuntu搜狗输入法中文无法切换英文：
https://blog.csdn.net/kang_tju/article/details/54630994  
Pro7：装完双系统之后,linux和windows转换最后windows下时间错乱，早了八个小时解决方案
https://blog.csdn.net/qq_40197828/article/details/79334158  
Pro8: Linux（Ubuntu16.04）调节屏幕亮度（亮度控制条消失的问题）：
https://blog.csdn.net/kingthon/article/details/81190898

另外，除了 GNU grub，还可以用 Microsoft 的 EasyBCD 来进行多系统的引导。

最后，附上 [安装Ubuntu后必须要做的几件事](https://blog.csdn.net/gatieme/article/details/44856359) 。