# 函数秘密共享

函数秘密共享（Function Secret Sharing，FSS）是[Elette Boyle](https://cs.idc.ac.il/~elette/)等人在2015年提出的密码学原语，其将函数作为秘密分发的对象，使得参与方获得函数秘密份额，之后参与方便在本地函数秘密份额评估，获得结果的秘密份额。函数秘密共享是同态秘密共享的对偶过程，二者在不同的应用中均获得良好的性能。

## 0. 函数秘密共享学习路线

以下是学习函数秘密共享的相关学习路线，需要的前置知识有：加性秘密共享、完全二叉树、伪随机数生成器的基本概念。

+ 第一阶段：首先需要阅读函数秘密共享的相关论文及其参考资料（所涉及的论文见“1. 函数秘密共享相关论文”）
  + 阅读论文BGI15
    + 了解和掌握函数秘密共享的定义和安全性定义，可以参考Boyle在BIU作的报告 ([Video](https://www.youtube.com/watch?v=fAXlOOs2t88)、[Slide](http://cyber.biu.ac.il/wp-content/uploads/2021/11/FSS-2022-BIU-WinterSchool_Elette.pdf)中Part1)
    + 了解基于伪随机数生成器的分布式点函数的FSS构造，可以参考Boyle在EruoCrypto2015上的PPT材料（[Slide](https://www.iacr.org/conferences/eurocrypt2015/cosic.esat.kuleuven.be/eurocrypt_2015/presentations/SecretSharing.zip)-Function Secret Sharing），注意这部分比较复杂，掌握思想就好
    + 了解函数秘密共享和安全多方计算的联系
  + 阅读论文BGI6
    + 了解和掌握函数秘密共享的定义和安全性定义
    + 了解和掌握基于伪随机数生成器的分布式点函数的函数秘密共享构造，可以参考Boyle在BIU作的报告 ([Video](https://www.youtube.com/watch?v=Zm-MUVve2_w)中的前半部分、[Slide](http://cyber.biu.ac.il/wp-content/uploads/2021/11/FSS-2022-BIU-WinterSchool_Elette.pdf)中Part2)
    + 了解决策树的函数秘密共享构造方案

## 1. 函数秘密共享相关论文
+ [GI14]Distributed Point Functions and Their Applications
  + 分布式点函数及其在PIR上的应用（函数秘密共享本质上是分布式点函数更泛化的表示）
  + 发表在EuroCrypto 2014，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-642-55220-5_35)、[ePrint](https://www.iacr.org/conferences/eurocrypt2014/37)
+ [BGI15]Function Secret Sharing
  + 函数秘密共享的开山之作，首次提出了DPF的FSS构造
  + 发表在EuroCrypto 2015，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-662-46803-6_12)
  + BGI15提出了分布式点函数、区间函数的函数秘密共享构造方案
+ [BGI16]Function Secret Sharing: Improvements and Extensions
  + 函数秘密共享的进一步研究，优化了DPF的FSS构造，并首次提出针对决策树的FSS构造
  + 发表在CCS 2016，论文链接见[ACM CCS](https://dl.acm.org/doi/10.1145/2976749.2978429)、[ePrint](https://eprint.iacr.org/2018/707)
  + BGI16提出了分布式点函数、决策树的函数秘密共享构造方案
+ [BGI19]Secure Computation with Preprocessing via Function Secret Sharing
  + 利用函数秘密共享实现了预处理模型下的安全计算协议
  + 发表在TCC 2019，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-030-36030-6_14)、[ePrint](https://eprint.iacr.org/2019/1095)
  + BGI19提出了Zero Test、Equality、整数比较、Interval Membership和Spline函数的函数秘密共享构造方案
+ [BCG+21]Function Secret Sharing for Mixed-Mode and Fixed-Point Secure Computation
  + BGI19的进一步优化，提出了针对更多非线性函数的FSS构造方案
  + 发表在EuroCrypto 2021，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-030-77886-6_30)、[ePrint](https://eprint.iacr.org/2020/1392)
  + [Vedio: Mayank Rathee presented at Eurocrypt 2021](https://www.youtube.com/watch?v=22BfFkP_Hbk&t=280s)
  + BCG+21提出了Zero Test、整数比较、ReLU、Spline、算术移位和逻辑移位、比特分解函数的函数秘密共享构造方案
+ [RTPB22]ARIANN: Low-Interaction Privacy-Preserving Deep Learning via Function Secret Sharing
  + 基于函数秘密共享的隐私保护深度学习，提出了针对于Equality Test、比较函数的函数秘密共享构造方案
  + 发表在PoPETs2022上，论文链接见[arXiv](https://arxiv.org/abs/2006.04593)、[PETS](https://petsymposium.org/popets/2022/popets-2022-0015.php)，代码链接见[GitHub](https://github.com/LaRiffle/ariann)
+ [Wagh2022]Pika: Secure Computation using Function Secret Sharing over Rings
  + 基于函数秘密共享的安全两方计算协议
  + 发表在PoPETs2022上，论文链接见[eprint](https://eprint.iacr.org/2022/826)
+ [GKCG22]LLAMA: A Low Latency Math Library for Secure Inference
  + 基于函数秘密共享的数学库，可用于安全隐私推理
  + 发表在PoPETs2022上，论文链接见[eprint](https://eprint.iacr.org/2022/793)


## 2. 函数秘密共享相关视频、阅读材料
+ [The 12th BIU Winter School on Cryptography: Advances in Secure Computation](https://cyber.biu.ac.il/event/the-12th-biu-winter-school-on-cryptography/)
  + 第12届BIU密码学冬令营中有Elette Boyle讲述的关于函数秘密共享的相关内容([Slide](http://cyber.biu.ac.il/wp-content/uploads/2021/11/FSS-2022-BIU-WinterSchool_Elette.pdf))
    + Function Secret Sharing: Definition ([Video](https://www.youtube.com/watch?v=fAXlOOs2t88))
    + Function Secret Sharing: Core Constructions of DPF and DCF ([Video](https://www.youtube.com/watch?v=Zm-MUVve2_w))
    + Function Secret Sharing: Extensions & Applications ([Video](https://www.youtube.com/watch?v=ORBLeo3lB4U&t=9s))
+ Elette Boyle在[TPMPC 2019](https://www.multipartycomputation.com/tpmpc-2019)上的演讲
  + 主要是基于[BGI19]Secure Computation with Preprocessing via Function Secret Sharing的讲述，介绍了基于函数秘密共享的预处理模型下安全两方计算协议
  + [Slide](https://u.cs.biu.ac.il/~lindell/TPMPC2019/Elette_Boyle_TPMPC2019.pdf)
+ Mayank Rathee在EuroCrypto 2021上关于论文Function Secret Sharing for Mixed-Mode and Fixed-Point Secure Computation所作的报告
  + [Vedio](https://www.youtube.com/watch?v=22BfFkP_Hbk&list=PLeeS-3Ml-rprwuVrOTYyYWkXuJLSu4fbu&index=82)


## 3. 函数秘密共享研究：函数秘密共享的构造和应用

目前的研究主要关注于函数秘密共享的构造和应用：前者是指针对分布式点函数、分布式比较函数的函数秘密共享构造方案，及函数秘密共享相关随机性生成方案；后者是指基于函数秘密共享的实际应用，例如隐私数据访问、安全多方计算等。

### 3.1 函数秘密共享的构造方案

在函数秘密共享的发展过程中，出现了许多面向不同运算的函数秘密共享方案。已有的工作可总结如下：
+ **分布式点函数（Distributed Point Functions）**：GI14提出了（两方）分布式点函数的构造及其在隐私信息检索中的应用，BGI15提出了基于伪随机数生成器的分布式点函数构造，并引入函数秘密共享的概念，优化了GI14的构造。BGI16则进一步优化了BGI15的构造，这也是当前最好的结果。而对于**多方**的情况，最好的结果是BGI15提出的构造方案。
+ **比较函数（Comparison Functions）和区间函数（Interval Functions）**：BGI16和BCG+21都实现了比较函数和区间函数的函数秘密共享方案，通常来说区间函数的函数秘密共享方案可以通过调用两个比较函数的函数秘密共享方案来实现。在BGI19和BCG+21中，还基于比较函数和区间函数的函数秘密共享方案实现了RELU函数和Spline函数（即分段函数）的函数秘密共享构造方案
+ **决策树（Decision Tree）**：BGI16针对决策树提出了有效的基于伪随机数生成器的两方函数秘密共享方案。
+ **Zero Test/Equality**：
+ **比特分解（Bit Decomposition）**：
+ **算术移位和逻辑移位（Arithmetic and Logical Shift）**：


### 3.2 函数秘密共享相关随机性生成方案



### 3.3 函数秘密共享的应用

