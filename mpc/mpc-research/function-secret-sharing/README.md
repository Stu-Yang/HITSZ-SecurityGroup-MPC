# 函数秘密共享

函数秘密共享（Function Secret Sharing，FSS）是[Elette Boyle](https://cs.idc.ac.il/~elette/)等人在2015年提出的密码学原语，其将函数作为秘密分发的对象，使得参与方获得函数秘密份额，之后参与方便在本地函数秘密份额评估，获得结果的秘密份额。函数秘密共享是同态秘密共享的对偶过程，二者在不同的应用中均获得良好的性能。

## 0. 函数秘密共享学习路线

以下是学习函数秘密共享的相关学习路线，需要的前置知识有：加性秘密共享、完全二叉树、伪随机数生成器的基本概念。

+ 第一阶段：首先需要阅读函数秘密共享的相关论文及其参考资料，掌握相关理论（所涉及的论文见“1. 函数秘密共享相关论文”）
  + 阅读论文BGI15
    + 了解和掌握函数秘密共享的定义和安全性定义，可以参考Boyle在BIU作的报告 ([Video](https://www.youtube.com/watch?v=fAXlOOs2t88)、[Slide](http://cyber.biu.ac.il/wp-content/uploads/2021/11/FSS-2022-BIU-WinterSchool_Elette.pdf)中Part1)
    + 了解基于伪随机数生成器的分布式点函数的FSS构造，可以参考Boyle在EruoCrypto2015上的PPT材料（[Slide](https://www.iacr.org/conferences/eurocrypt2015/cosic.esat.kuleuven.be/eurocrypt_2015/presentations/SecretSharing.zip)-Function Secret Sharing），注意这部分比较复杂，掌握思想就好
    + 了解函数秘密共享和安全多方计算的联系
  + 阅读论文BGI6
    + 了解和掌握函数秘密共享的定义和安全性定义
    + 了解和掌握基于伪随机数生成器的分布式点函数的函数秘密共享构造，可以参考Boyle在BIU作的报告 ([Video](https://www.youtube.com/watch?v=Zm-MUVve2_w)中的前半部分、[Slide](http://cyber.biu.ac.il/wp-content/uploads/2021/11/FSS-2022-BIU-WinterSchool_Elette.pdf)中Part2)
    + 了解决策树的函数秘密共享构造方案
  + 阅读论文BGI19
    + 了解和掌握基于函数秘密共享如何实现安全两方计算
  + 阅读论文BCG+21
    + 了解和掌握DCF构造
    + 了解其他函数的函数秘密共享构造
+ 第二阶段：了解和掌握基于函数秘密共享的安全计算，及其在实际场景中的应用（所涉及的论文见“1. 函数秘密共享相关论文”）
  + 阅读论文[RTPB22]
    + 了解和掌握基于函数秘密共享的隐私保护机器学习
  + 阅读论文[GKCG22]
    + 了解和掌握基于函数秘密共享的数学库
+ 第三阶段：开始函数秘密共享的相关研究
  + 确立自己的目标任务，将该任务分解成一个一个子任务，子任务可以不断往下细分，直到你自己可以直接解决

## 1. 函数秘密共享领域的相关大牛

+ [Elette Boyle](https://cs.idc.ac.il/~elette/)：函数秘密共享学派开创人
+ [Niv Gilboa](https://www.bgu.ac.il/~gilboan/publications.html)：系统研究分布式点函数，为函数秘密共享的创立打下基础
+ [Yuval Ishai](https://www.cs.technion.ac.il/~yuvali/)：Boyle的老师，其和Niv Gilboa一起系统研究分布式点函数，为函数秘密共享的创立打下基础
+ [Nishanth Chandran](https://www.microsoft.com/en-us/research/people/nichandr/publications/)：[BCG21+]中的C
+ [Geoffroy Couteau](https://geoffroycouteau.github.io/publications/)：近几年和Boyle多有合作
+ [Mayank Rathee](https://mayank0403.github.io/)：近几年多有研究函数秘密共享及其应用

## 2. 函数秘密共享相关论文
<details>
<summary>相关论文，请点击展开</summary>

+ **[SDFY94]How to share a function securely**
  + 首次提出函数秘密共享概念，并构造了函数分发和重构方案
  + 发表在STOC94，论文链接见[ACM](https://dl.acm.org/doi/abs/10.1145/195058.195405)
+ **[GI14]Distributed Point Functions and Their Applications**
  + 分布式点函数及其在PIR上的应用（函数秘密共享本质上是分布式点函数更泛化的表示）
  + 发表在EuroCrypto 2014，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-642-55220-5_35)、[ePrint](https://www.iacr.org/conferences/eurocrypt2014/37)
+ **[BGI15]Function Secret Sharing**
  + 函数秘密共享的开山之作，首次提出了DPF的FSS构造
  + 发表在EuroCrypto 2015，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-662-46803-6_12)
  + BGI15提出了分布式点函数、区间函数的函数秘密共享构造方案
+ **[BGI16]Function Secret Sharing: Improvements and Extensions**
  + 函数秘密共享的进一步研究，优化了DPF的FSS构造，并首次提出针对决策树的FSS构造
  + 发表在CCS 2016，论文链接见[ACM CCS](https://dl.acm.org/doi/10.1145/2976749.2978429)、[ePrint](https://eprint.iacr.org/2018/707)
  + BGI16提出了分布式点函数、决策树的函数秘密共享构造方案
+ **[BGI19]Secure Computation with Preprocessing via Function Secret Sharing**
  + 利用函数秘密共享实现了预处理模型下的安全计算协议
  + 发表在TCC 2019，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-030-36030-6_14)、[ePrint](https://eprint.iacr.org/2019/1095)
  + BGI19提出了Zero Test、Equality、整数比较、Interval Membership和Spline函数的函数秘密共享构造方案
+ **[BCG+21]Function Secret Sharing for Mixed-Mode and Fixed-Point Secure Computation**
  + BGI19的进一步优化，提出了针对更多非线性函数的FSS构造方案
  + 发表在EuroCrypto 2021，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-030-77886-6_30)、[ePrint](https://eprint.iacr.org/2020/1392)
  + [Vedio: Mayank Rathee presented at Eurocrypt 2021](https://www.youtube.com/watch?v=22BfFkP_Hbk&t=280s)
  + BCG+21提出了Zero Test、整数比较、ReLU、Spline、算术移位和逻辑移位、比特分解函数的函数秘密共享构造方案
+ **[RTPB22]ARIANN: Low-Interaction Privacy-Preserving Deep Learning via Function Secret Sharing**
  + 基于函数秘密共享的隐私保护深度学习，提出了针对于Equality Test、比较函数的函数秘密共享构造方案
  + 发表在PoPETs2022上，论文链接见[arXiv](https://arxiv.org/abs/2006.04593)、[PETS](https://petsymposium.org/popets/2022/popets-2022-0015.php)，代码链接见[GitHub](https://github.com/LaRiffle/ariann)、视频链接见[Youtube-vedio](https://www.youtube.com/watch?v=ztCptCgqZBs)
+ **[Wagh22]Pika: Secure Computation using Function Secret Sharing over Rings**
  + 基于函数秘密共享的安全两方计算协议
  + 发表在PoPETs2022上，论文链接见[eprint](https://eprint.iacr.org/2022/826)
+ **[GKCG22]LLAMA: A Low Latency Math Library for Secure Inference**
  + 基于函数秘密共享的数学库，可用于安全隐私推理
  + 发表在PoPETs2022上，论文链接见[eprint](https://eprint.iacr.org/2022/793)，视频链接见[bilibili](https://www.bilibili.com/video/BV1hU4y1Q7w2?p=2&vd_source=45400e58cd0ed58d7605745553c0f81e)(其中，FSS的内容在视频18:00)
+ **[CP22]Lightweight, Maliciously Secure Verifiable Function Secret Sharing**
  + 恶意安全的函数秘密共享
  + 发表在EuroCrypto2022上，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-031-06944-4_6)
+ **[BKO22]CNF-FSS and Its Applications**
  + 多方函数秘密共享构造方案
  + 发表在PKC 2022上，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-030-97121-2_11)
+ **[APR+22]Communication Efficient Secure Logistic Regression**
  + 结合基于函数秘密共享的MPC协议和基于非函数秘密共享的MPC协议，设计了安全逻辑回归协议
  + 论文链接见[eprint](https://eprint.iacr.org/2022/866)，视频链接见[youtube](https://www.youtube.com/watch?v=HkFML4TJqYc&list=PLEn8f3ymo4LDqD_m9pVgkpFBvTrDKnBmF&index=16)
+ **[AMO+22]Memory and Round-Efficient MPC Primitives in the Pre-Processing Model from Unit Vectorization**
  + BGI19和BCG+21的优化
  + 论文发表在ASiaCCS 2022，论文链接见[ACM](https://dl.acm.org/doi/pdf/10.1145/3488932.3517407)
+ **[BGIK22]Programmable Distributed Point Functions
  + 提出了一种新方法来构造DPF（之前构造DPF的方法是基于树的）
  + 论文发表在Crypto 2022，论文链接见[eprint](https://eprint.iacr.org/2022/1060)

## 2.1 相关阅读材料
+ **[DNNR17]The TinyTable protocol for 2-Party Secure Computation, or: Gate-scrambling Revisited**
  + 利用真值表来实现所有函数的预处理模型下安全计算，该方法针对布尔电路
  + 发表在Crypto 2017
+ **[DKS17]Pushing the Communication Barrier in Secure Computation using Lookup Tables**
  + 利用查找表来实现安全计算
  + 发表在NDSS 2017上，NDSS页面[Pushing the Communication Barrier in Secure Computation using Lookup Tables](https://www.ndss-symposium.org/ndss2017/ndss-2017-programme/pushing-communication-barrier-secure-computation-using-lookup-tables/)
  + 论文链接见[eprint](https://eprint.iacr.org/2018/486)
+ **[CZ22]Non-Interactive Secure Computation of Inner-Product from LPN and LWE**
  + 详见[eprint](https://iacr.org/cryptodb/data/paper.php?pubkey=32405)
+ **[CZW+21]When Homomorphic Encryption Marries Secret Sharing: Secure Large-Scale Sparse Logistic Regression and Applications in Risk Control**
  + 结合秘密共享和同态加密实现稀疏数据的逻辑回归
  + 发表在KDD 2021，文章链接见[ACM](https://dl.acm.org/doi/10.1145/3447548.3467210)，[arXiv](https://arxiv.org/pdf/2008.08753.pdf)
+ **[DGH+21]MPC-Friendly Symmetric Cryptography from Alternating Moduli: Candidates, Protocols, and Applications**
  + 介绍了许多密码学协议，其中包括一些对FSS的讨论
  + 发表在Crypto 2021，文章链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-030-84259-8_18)
+ **[ACH20]The Usefulness of Sparsifiable Inputs: How to Avoid Subexponential iO**
  + 基于iO实现了许多密码学协议，其中就包括利用iO实现一种用于所有电路的加性函数秘密共享方案(但是在该论文中未找到相关构造)
  + 发表在PKC 2020，文章链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-030-45374-9_7)、[eprint](https://eprint.iacr.org/2018/470)
+ **[DHRW]Spooky Encryption and Its Applications**
  + 提出了Spooky Encryption的概念，并提出了它的应用，其中一个应用就是函数秘密共享(见6.3 Function Secret Sharing)，不过该论文没有提出有效表示函数f的方案
  + 发表在Crypto 2016，文章链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-662-53015-3_4)、[eprint](https://eprint.iacr.org/2016/272)

</details>

## 2.2 函数秘密共享相关视频、阅读材料
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
+ [TPMPC 2022](https://www.multipartycomputation.com/tpmpc-2022)上的一些报告，完整视频链接见[bilibili](https://www.bilibili.com/video/BV1hU4y1Q7w2)和[youtube](https://www.youtube.com/playlist?list=PLEn8f3ymo4LDqD_m9pVgkpFBvTrDKnBmF)
  + [Concretely efficient secure comparison](https://www.bilibili.com/video/BV1hU4y1Q7w2?p=28)
  + [New MPC Techniques for Secure Machine Learning](https://www.bilibili.com/video/BV1hU4y1Q7w2?p=2)，该报告对应上述论文[APR+22]Communication Efficient Secure Logistic Regression

</detail>

## 3. 函数秘密共享研究：函数秘密共享的构造和应用

目前的研究主要关注于函数秘密共享的构造和应用：前者是指针对分布式点函数、分布式比较函数的函数秘密共享构造方案，及函数秘密共享相关随机性生成方案；后者是指基于函数秘密共享的实际应用，例如隐私数据访问、安全多方计算等。

### 3.1 函数秘密共享的构造方案

#### 3.1.1 构造方法

基于GGM-style树，利用伪随机生成器进行生成。

### 3.1.2 已有的函数秘密共享构造方案

在函数秘密共享的发展过程中，出现了许多面向不同运算的函数秘密共享方案。已有的工作可总结如下：
+ **分布式点函数（Distributed Point Functions）**：GI14提出了（两方）分布式点函数的构造及其在隐私信息检索中的应用，BGI15提出了基于伪随机数生成器的分布式点函数构造，并引入函数秘密共享的概念，优化了GI14的构造。BGI16则进一步优化了BGI15的构造，这也是当前最好的结果。而对于**多方**的情况，最好的结果是BGI15提出的构造方案。
+ **比较函数（Comparison Functions）和区间函数（Interval Functions）**：BGI16和BCG+21都实现了比较函数和区间函数的函数秘密共享方案，通常来说区间函数的函数秘密共享方案可以通过调用两个比较函数的函数秘密共享方案来实现。在BGI19和BCG+21中，还基于比较函数和区间函数的函数秘密共享方案实现了RELU函数和Spline函数（即分段函数）的函数秘密共享构造方案
+ **决策树（Decision Tree）**：BGI16针对决策树提出了有效的基于伪随机数生成器的两方函数秘密共享方案。
+ **Zero Test/Equality**：
+ **比特分解（Bit Decomposition）**：
+ **算术移位和逻辑移位（Arithmetic and Logical Shift）**：




### 3.2 函数秘密共享相关随机性生成方案



### 3.3 函数秘密共享的应用



[回到顶部](#readme)
