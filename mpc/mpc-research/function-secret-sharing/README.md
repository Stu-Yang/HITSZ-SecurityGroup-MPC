# 函数秘密共享

函数秘密共享（Function Secret Sharing，FSS）是[Elette Boyle](https://cs.idc.ac.il/~elette/)等人在2015年提出的密码学原语，其将函数作为秘密分发的对象，使得参与方获得函数秘密份额，之后参与方便在本地函数秘密份额评估，获得结果的秘密份额。函数秘密共享是同态秘密共享的对偶过程，二者在不同的应用中均获得良好的性能。

## 0. 函数秘密共享学习路线

<details>
<summary>以下是学习函数秘密共享的相关学习路线，请点击展开</summary>

（预备知识：加性秘密共享、完全二叉树、伪随机数生成器）

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
</details>

## 1. 函数秘密共享领域的相关大牛

+ [Elette Boyle](https://cs.idc.ac.il/~elette/)：函数秘密共享学派开创人
+ [Niv Gilboa](https://www.bgu.ac.il/~gilboan/publications.html)：系统研究分布式点函数，为函数秘密共享的创立打下基础
+ [Yuval Ishai](https://www.cs.technion.ac.il/~yuvali/)：Boyle的老师，其和Niv Gilboa一起系统研究分布式点函数，为函数秘密共享的创立打下基础
+ [Nishanth Chandran](https://www.microsoft.com/en-us/research/people/nichandr/publications/)：[BCG21+]中的C
+ [Geoffroy Couteau](https://geoffroycouteau.github.io/publications/)：近几年和Boyle多有合作
+ [Mayank Rathee](https://mayank0403.github.io/)：近几年多有研究函数秘密共享及其应用

## 2. 函数秘密共享相关论文
<details>
<summary>函数秘密共享相关论文和阅读材料，请点击展开</summary>

+ ***[SDFY94]How to share a function securely***
  + 首次提出函数秘密共享概念，并构造了函数分发和重构方案
  + 发表在STOC94，论文链接见[ACM](https://dl.acm.org/doi/abs/10.1145/195058.195405)
+ ***[GI14]Distributed Point Functions and Their Applications***
  + 分布式点函数及其在PIR上的应用（函数秘密共享本质上是分布式点函数更泛化的表示）
  + 发表在EuroCrypto 2014，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-642-55220-5_35)、[ePrint](https://www.iacr.org/conferences/eurocrypt2014/37)
+ :triangular_flag_on_post: ***[BGI15]Function Secret Sharing***
  + 函数秘密共享的开山之作，首次提出了DPF的FSS构造
  + 发表在EuroCrypto 2015，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-662-46803-6_12)
  + BGI15提出了分布式点函数、区间函数的函数秘密共享构造方案
+ :triangular_flag_on_post: ***[BGI16]Function Secret Sharing: Improvements and Extensions***
  + 函数秘密共享的进一步研究，优化了DPF的FSS构造，并首次提出针对决策树的FSS构造
  + 发表在CCS 2016，论文链接见[ACM CCS](https://dl.acm.org/doi/10.1145/2976749.2978429)、[ePrint](https://eprint.iacr.org/2018/707)
  + BGI16提出了分布式点函数、决策树的函数秘密共享构造方案
+ ***[DS17]Scaling ORAM for Secure Computation***
  + 文章中提出了函数秘密共享分布式密钥生成算法，适用于较小域
  + 发表在CCS 2017，论文链接见[CCS](https://dl.acm.org/doi/10.1145/3133956.3133967)，[eprint](https://eprint.iacr.org/2017/827)
+ ***[WYG+17]Splinter: Practical Private Queries on Public Data***
  + 利用函数秘密共享实现隐私数据库查询
  + 发表在USENIX 2017，论文链接见[USENIX 2017](https://www.usenix.org/conference/nsdi17/technical-sessions/presentation/wang-frank)、[ePrint](https://eprint.iacr.org/2016/1148)
+ ***[BCGI18]Compressing Vector OLE***
  + 利用函数秘密共享实现Oblivious linear-function evaluation
  + 发表在CCS 2018，论文链接见[ACM CCS](https://dl.acm.org/doi/abs/10.1145/3243734.3243868)、[eprint](https://eprint.iacr.org/2019/273)
+ :triangular_flag_on_post: ***[BGI19]Secure Computation with Preprocessing via Function Secret Sharing***
  + 利用函数秘密共享实现了预处理模型下的安全计算协议
  + 发表在TCC 2019，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-030-36030-6_14)、[ePrint](https://eprint.iacr.org/2019/1095)
  + BGI19提出了Zero Test、Equality、整数比较、Interval Membership和Spline函数的函数秘密共享构造方案
+ ***[SGRR19]Distributed Vector-OLE-Improved Constructions and Implementation***
  + [BCGI18]的优化
  + 发表在CCS 2019，论文链接见[ACM CCS](https://dl.acm.org/doi/10.1145/3319535.3363228)、[eprint](https://eprint.iacr.org/2019/1084)
  + 该论文的第三作者Leonie Reichert的硕士毕业论文[Multi-Point Function Secret Sharing using Cuckoo Hashing](https://github.com/ReichertL/Masterthesis)用布谷鸟哈希实现了分布式多点函数
+ ***[BCG+20]Efficient Pseudorandom Correlation Generators from Ring-LPN***
  + 基于LPN假设提出了相关随机性生成方案，文章为DPF密钥生成提出了分布式计算协议
  + 发表在Crypto 2020，论文链接见[eprint](https://eprint.iacr.org/2022/1035)
+ ***[BBG+21]Lightweight Techniques for Private Heavy Hitters***
  + 基于BGI16的DPF构造提出了iDPF构造（DPF的拓展），并利用iDPF构造解决了Private Heavy Hitters（隐私频繁项）
  + 发表在S&P 2021，论文链接见[eprint](https://eprint.iacr.org/2021/017)
+ :triangular_flag_on_post: ***[BCG+21]Function Secret Sharing for Mixed-Mode and Fixed-Point Secure Computation***
  + BGI19的进一步优化，提出了针对更多非线性函数的FSS构造方案
  + 发表在EuroCrypto 2021，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-030-77886-6_30)、[ePrint](https://eprint.iacr.org/2020/1392)
  + [Vedio: Mayank Rathee presented at Eurocrypt 2021](https://www.youtube.com/watch?v=22BfFkP_Hbk&t=280s)
  + BCG+21提出了Zero Test、整数比较、ReLU、Spline、算术移位和逻辑移位、比特分解函数的函数秘密共享构造方案
+ ***[DGH+21]MPC-Friendly Symmetric Cryptography from Alternating Moduli:Candidates, Protocols, and Applications***
  + 提出了函数秘密共享的分布式密钥生成算法（但未直接给出算法），相比于与Doerner和shelat[DS17]的黑盒FSS密钥生成协议相比，其计算成本仅随域大小对数递增。
  + 发表在Crypto 2021，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-030-84259-8_18)、[eprint](https://eprint.iacr.org/2021/885)
+ ***[RTPB22]ARIANN: Low-Interaction Privacy-Preserving Deep Learning via Function Secret Sharing***
  + 基于函数秘密共享的隐私保护深度学习，提出了针对于Equality Test、比较函数的函数秘密共享构造方案
  + 发表在PoPETs2022上，论文链接见[arXiv](https://arxiv.org/abs/2006.04593)、[PETS](https://petsymposium.org/popets/2022/popets-2022-0015.php)，代码链接见[GitHub](https://github.com/LaRiffle/ariann)、视频链接见[Youtube-vedio](https://www.youtube.com/watch?v=ztCptCgqZBs)
  + 该论文中所设计的协议还被用于隐私保护医学图像分析，[End-to-end privacy preserving deep learning on multi-institutional medical imaging](https://www.nature.com/articles/s42256-021-00337-8)基于AriaNN提出了将差分隐私的联邦模型训练与模型更新的加密聚合以及加密的远程推理结合起来的PriMIA框架，并应用在深度CNN对儿科胸部X光片进行分类（医学图像分类）中。
+ ***[Wagh22]Pika: Secure Computation using Function Secret Sharing over Rings***
  + 基于函数秘密共享的安全两方计算协议
  + 发表在PoPETs2022上，论文链接见[eprint](https://eprint.iacr.org/2022/826)
+ ***[GKCG22]LLAMA: A Low Latency Math Library for Secure Inference***
  + 基于函数秘密共享的数学库，可用于安全隐私推理
  + 发表在PoPETs2022上，论文链接见[eprint](https://eprint.iacr.org/2022/793)，视频链接见[bilibili](https://www.bilibili.com/video/BV1hU4y1Q7w2?p=2&vd_source=45400e58cd0ed58d7605745553c0f81e)(其中，FSS的内容在视频18:00)
+ ***[CP22]Lightweight, Maliciously Secure Verifiable Function Secret Sharing***
  + 恶意安全的函数秘密共享
  + 发表在EuroCrypto2022上，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-031-06944-4_6)
+ ***[BKO22]CNF-FSS and Its Applications***
  + 多方函数秘密共享构造方案
  + 发表在PKC 2022上，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-030-97121-2_11)
+ ***[APR+22]Communication Efficient Secure Logistic Regression***
  + 结合基于函数秘密共享的MPC协议和基于非函数秘密共享的MPC协议，设计了安全逻辑回归协议
  + 论文链接见[eprint](https://eprint.iacr.org/2022/866)，视频链接见[youtube](https://www.youtube.com/watch?v=HkFML4TJqYc&list=PLEn8f3ymo4LDqD_m9pVgkpFBvTrDKnBmF&index=16)
+ ***[AMO+22]Memory and Round-Efficient MPC Primitives in the Pre-Processing Model from Unit Vectorization***
  + BGI19和BCG+21的优化
  + 论文发表在ASiaCCS 2022，论文链接见[ACM](https://dl.acm.org/doi/pdf/10.1145/3488932.3517407)
+ ***[DRPS22]Waldo- A Private Time-Series Database from Function Secret Sharing***
  + 利用函数秘密共享实现隐私数据库查询
  + 发表在S&P2022，论文链接见[eprint](https://eprint.iacr.org/2021/1661)，[IEEE](https://ieeexplore.ieee.org/document/9833611/)
+ ***[BCG+22]Correlated Pseudorandomness from Expand-Accumulate Codes***
  + 提出基于Expand-Accumulate Codes来生成相关随机性，文章提出了一种放松版本的DCF算法（RDCF），并为RDCF提出了分布式密钥生成算法
  + 发表在Crypto 2022，论文链接见[eprint](https://eprint.iacr.org/2022/1014.pdf)
+ :triangular_flag_on_post: ***[BGIK22]Programmable Distributed Point Functions***
  + 提出了一种新方法来构造DPF（之前构造DPF的方法是基于树的）
  + 论文发表在Crypto 2022，论文链接见[eprint](https://eprint.iacr.org/2022/1060)

  
  
## 2.1 相关阅读材料
+ ***[DHRW16]Spooky Encryption and Its Applications***
  + 提出了Spooky Encryption的概念，并提出了它的应用，其中一个应用就是函数秘密共享(见6.3 Function Secret Sharing)，不过该论文没有提出有效表示函数f的方案
  + 发表在Crypto 2016，文章链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-662-53015-3_4)、[eprint](https://eprint.iacr.org/2016/272)
+ ***[DKS17]Pushing the Communication Barrier in Secure Computation using Lookup Tables***
  + 利用查找表来实现安全计算
  + 发表在NDSS 2017上，论文链接见[NDSS](https://www.ndss-symposium.org/ndss2017/ndss-2017-programme/pushing-communication-barrier-secure-computation-using-lookup-tables/)
  + 论文链接见[eprint](https://eprint.iacr.org/2018/486)
+ ***[DNNR17]The TinyTable protocol for 2-Party Secure Computation, or: Gate-scrambling Revisited***
  + 利用真值表来实现所有函数的预处理模型下安全计算，该方法针对布尔电路
  + 发表在Crypto 2017
+ ***[ACH20]The Usefulness of Sparsifiable Inputs: How to Avoid Subexponential iO***
  + 基于iO实现了许多密码学协议，其中就包括利用iO实现一种用于所有电路的加性函数秘密共享方案(但是在该论文中未找到相关构造)
  + 发表在PKC 2020，文章链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-030-45374-9_7)、[eprint](https://eprint.iacr.org/2018/470)
+ ***[DIL+20]Function Secret Sharing for PSI-CA: With Applications to Private Contact Tracing***
  + 基于函数秘密共享的PSI
  + 论文链接见[eprint](https://eprint.iacr.org/2020/1599)
+ ***[CZ22]Non-Interactive Secure Computation of Inner-Product from LPN and LWE***
  + 详见[eprint](https://iacr.org/cryptodb/data/paper.php?pubkey=32405)
+ ***[DIL+22]Streaming and Unbalanced PSI from Function Secret Sharing]***
  + 基于函数秘密共享的非平衡PSI
  + 发表在SCN 2022，文章链接见[Springer](https://link.springer.com/content/pdf/10.1007/978-3-031-14791-3_25.pdf)
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
  + [Concretely efficient secure comparison](https://www.bilibili.com/video/BV1hU4y1Q7w2?p=28)，该报告对应上述论文[APR+22]Communication Efficient Secure Logistic Regression
  + [New MPC Techniques for Secure Machine Learning](https://www.bilibili.com/video/BV1hU4y1Q7w2?p=2)

</detail>

## 3. 函数秘密共享研究：函数秘密共享的构造和应用

目前的研究主要关注于函数秘密共享的构造和应用：前者是指针对分布式点函数、分布式比较函数的函数秘密共享构造方案，及函数秘密共享相关随机性生成方案；后者是指基于函数秘密共享的实际应用，例如隐私数据访问、安全多方计算等。

### 3.1 函数秘密共享的构造方案

#### 3.1.1 构造方法

目前大多数方案都是**基于伪随机生成器的GGM-style树**方法，其他方法有基于布谷鸟哈希生成DPF[SGRR19]，和其他技术生成DPF[BGIK22]。

#### 3.1.2 已有的函数秘密共享构造方案

在函数秘密共享的发展过程中，出现了许多面向不同运算的函数秘密共享方案。已有的工作可总结如下：
+ **分布式点函数（Distributed Point Functions）**：GI14提出了（两方）分布式点函数的构造及其在隐私信息检索中的应用，BGI15提出了基于伪随机数生成器的分布式点函数构造，并引入函数秘密共享的概念，优化了GI14的构造。BGI16则进一步优化了BGI15的构造，这也是当前最好的结果。而对于**多方**的情况，最好的结果是BGI15提出的构造方案。
+ **比较函数（Comparison Functions）和区间函数（Interval Functions）**：BGI16和BCG+21都实现了比较函数和区间函数的函数秘密共享方案，通常来说区间函数的函数秘密共享方案可以通过调用两个比较函数的函数秘密共享方案来实现。在BGI19和BCG+21中，还基于比较函数和区间函数的函数秘密共享方案实现了RELU函数和Spline函数（即分段函数）的函数秘密共享构造方案。BCG+22提出了一种放松版本的分布式比较函数（RDCF），其比DCF更高效。
+ **决策树（Decision Tree）**：BGI16针对决策树提出了有效的基于伪随机数生成器的两方函数秘密共享方案。
+ **Zero Test/Equality**：通过调用分布式点函数实现，BGI19描述了具体调用方式
+ **比特分解（Bit Decomposition）**：BGI19首次提出比特分解协议，BCG+21对其进行优化。
+ **算术移位和逻辑移位（Arithmetic and Logical Shift）**：BCG+21首次提出移位协议实现算术运算


### 3.2 函数秘密共享相关随机性生成方案

函数秘密共享过程中，算法Gen需要Dealer实现，目前有三种思路来实现实现Dealer：
+ **在离线阶段利用诚实大多数三方计算协议**：**Wagh22**引入诚实第三方来辅助计算离线阶段的函数秘密共享相关随机性。
+ **在离线阶段利用安全两方计算协议**
  + Fast distributed FSS for small domains：**DS17**提出了为DPF函数秘密共享分布式密钥生成算法，但只适合较小输出群（原文只适用于{0,1}）。**BCG+20**基于LPN假设为DPF密钥生成提出了分布式计算协议。**BCG+21**则在提出优化分布式点函数的同时，基于[DS17]给出了安全分布式DCF密钥生成算法（**BCG+21**也简单介绍了如何通过2PC协议来分布式生成DCF密钥），**APR+22**也利用了这一方式来提出了Gen^iDPF。
  + MPC-friendly PRG：**DGH+21**提出了函数秘密共享的分布式密钥生成算法（但未直接给出算法），相比于与Doerner和Shelat[DS17]的黑盒FSS密钥生成协议相比，其计算成本仅随域大小对数递增。**BCG+22**提出基于Expand-Accumulate Codes来生成相关随机性，文章提出了一种放松版本的DCF算法（RDCF），并为RDCF提出了分布式密钥生成算法。**BGIK22**提出了可编程分布式点函数，并为DPF提出了常数轮分布式DPF密钥生成算法。


### 3.3 函数秘密共享的应用
+ **安全计算（MPC）**：如BGI19、BCG+21提出将函数秘密共享应用于安全计算，提出了基于函数秘密共享的安全两方计算框架。在此框架下，APR+22结合函数秘密共享和加性秘密共享实现逻辑回归，RTPB22基于函数秘密共享提出隐私保护神经网络系统Ariann
+ **隐私信息信息检索（PIR）**：
+ **隐私集合求交（PSI）**：DIL+20和DIL+22基于函数秘密共享提出隐私保护集合求交运算
+ **隐私频繁项查询（PHH）**：BBG+21提出基于iDPF（DPF变体）的隐私频繁项查询算法
+ **隐私数据库查询**：DRPS22提出基于函数秘密共享的隐私保护数据库查询算法
+ ...

[回到顶部](#readme)
