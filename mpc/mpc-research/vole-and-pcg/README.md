# 向量不经意线性函数计算VOLE和伪随机相关生成器PCG

向量不经意线性函数计算（Vector Oblivious Linear Evaluation, VOLE）是一种十分有用的相关随机性（Correlated Randomness），这些相关随机性可以由一种称为伪随机相关生成器（Pseudorandom Correlation Generator, PCG）来生成，PCG的构造主要依赖于[函数秘密共享](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/function-secret-sharing)、[同态秘密共享](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/homomorphic-secret-sharing)和LPN（Learning Parity with Noise）假设来构造。

## 0. 如何学习VOLE和PCG

+ 2022年BIU冬令营：在2022年BIU冬令营中，有对VOLE和PCG的系统介绍（部分Slide资料可能无法现在，请前往[addingIce/12th-BIU](https://github.com/addingIce/The-12th-BIU-Winter-School-on-Cryptography)进行下载。），详见如下
  + Peter Scholl: Vector Oblivious Linear Evaluation – part 1 ([Slides](http://cyber.biu.ac.il/wp-content/uploads/2021/11/Vector_Oblivious_Linear_Evaluation-1.pdf)) ([Video](https://www.youtube.com/watch?v=ZfdXY_oLhSo&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=9&t=9s))
  + Peter Scholl: Vector Oblivious Linear Evaluation – part 2 ([Slides](http://cyber.biu.ac.il/wp-content/uploads/2021/11/Vector_Oblivious_Linear_Evaluation-2.pdf)) ([Video](https://www.youtube.com/watch?v=i0Y6wdOgRR8&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=10&t=4s))
  + Yuval Ishai: Pseudorandom Correlation Generators – part 1 ([Slides parts 1-2](http://cyber.biu.ac.il/wp-content/uploads/2021/11/pcg-Yuval_Ishai.pdf)) ([Video](https://www.youtube.com/watch?v=A2jWB6mlUPE&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=11&t=5s))
  + Yuval Ishai: Pseudorandom Correlation Generators – part 2 ([Video](https://www.youtube.com/watch?v=AkfRu0yYkGU&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=12&t=3s))
  + Peter Scholl: Silent OT and VOLE from LPN  ([Slides](http://cyber.biu.ac.il/wp-content/uploads/2021/11/pcg-3.pdf)) ([Video](https://www.youtube.com/watch?v=OxXBa-pUwa4&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=19))
  + Peter Scholl: Pseudorandom Correlation Functions from Paillier ([Slides](http://cyber.biu.ac.il/wp-content/uploads/2021/11/pcg-4.pdf)) ([Video](https://www.youtube.com/watch?v=TbUQa-bJAHM&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=20&t=1s))
+ 其他资料
  + Lisa Kohl关于MPC with Silent Preprocessing via Pseudorandom Correlation Generators的汇报（[Slides](https://simons.berkeley.edu/sites/default/files/docs/15517/mpcwithsilentpreprocessing.pdf), [Video](https://www.youtube.com/watch?v=CVRZdUJwlqw)）
  + Peter Scholl在TPMPC 2019中关于MPC with Silent Preprocessing or (or: Two-Round OT Extension from LPN)的汇报（[Slides](http://u.cs.biu.ac.il/~lindell/TPMPC2019/Peter_Scholl_TPMPC2019.pdf)）

## 1. 伪随机相关生成器领域的相关大牛
+ [Elette Boyle](https://cs.idc.ac.il/~elette/)：提出伪随机相关生成器PCG，并针对VOLE相关随机性提出了基于PCG的高效方案
+ [Geoffroy Couteau](https://geoffroycouteau.github.io/)：和Boyle一起合作了伪随机相关生成器PCG的开创性论文
+ [Niv Gilboa](https://www.bgu.ac.il/~gilboan)：系统研究伪随机相关生成器PCG
+ [Yuval Ishai](https://www.cs.technion.ac.il/~yuvali/)：Boyle的老师，其和Niv Gilboa一起系统研究伪随机相关生成器PCG
+ [Ariel Nof](https://u.cs.biu.ac.il/~nofarie/)：近几年也在和Boyle合作研究伪随机相关生成器
+ [Peter Scholl](https://dblp.org/pid/00/10576.html)：对预处理模型下的安全多方计算很有研究
+ [Lisa Kohl](https://lisakohl.me/)：Yuval Ishai的学生

## 2. 伪随机相关生成器相关论文

<details>
<summary>伪随机相关生成器相关论文和阅读材料，请点击展开</summary>

### 2.1 相关论文

+ ***[Bea91]Efficient Multiparty Protocols Using Circuit Randomization***
  + 预处理模型最早源于Beaver的工作，Beaver针对BGW协议的复杂乘法运算，提出了乘法三元组的概念（后也称Beaver三元组），用一轮交互便可完成一次乘法运算，大大提高了乘法运算的效率。
  + 论文发表在CRYPTO 1991，论文链接见[Springer](https://link.springer.com/chapter/10.1007/3-540-46766-1_34)
+ ***[IKM+13]On the Power of Correlated Randomness in Secure Computation***
  + Ishai等人在2013年研究了相关随机性能在多大程度上帮助构造不诚实大多数的安全多方计算协议，称为OTTT协议
  + 论文发表在TCC，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-642-36594-2_34)，[eprint](https://www.iacr.org/archive/tcc2013/77850598/77850598.pdf)
+ :triangular_flag_on_post:***Function Secret Sharing***：Elette Boyle等人在2015年提出函数秘密共享（Function Secret Sharing, FSS），详见[Function Secret Sharing](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/function-secret-sharing)
  + ***[BGI15]Function Secret Sharing***：函数秘密共享的开山之作，论文发表在EuroCrypto 2015，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-662-46803-6_12)
  + ***[BGI16]Function Secret Sharing: Improvements and Extensions***：函数秘密共享的系统研究，发表在CCS 2016，论文链接见[ACM CCS](https://dl.acm.org/doi/10.1145/2976749.2978429)、[ePrint](https://eprint.iacr.org/2018/707)
  + ***[BGI19]Secure Computation with Preprocessing via Function Secret Sharing***：利用函数秘密共享实现了预处理模型下的安全计算协议，发表在TCC 2019，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-030-36030-6_14)、[ePrint](https://eprint.iacr.org/2019/1095)
  + ***[BCG+21]Function Secret Sharing for Mixed-Mode and Fixed-Point Secure Computation***：函数秘密共享和安全计算，论文发表在EuroCrypto 2021，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-030-77886-6_30)、[ePrint](https://eprint.iacr.org/2020/1392)
+ :triangular_flag_on_post:***Homomorphic Secret Sharing***：Elette Boyle等人在2016年提出同态秘密共享（Homomorphic Secret Sharing, HSS），详见[Homomorphic Secret Sharing](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/homomorphic-secret-sharing)。在研究同态秘密共享时，Boyle等人提出了伪随机相关生成器的概念。
  + ***[BGI16]Breaking the Circuit Size Barrier for Secure Computation Under DDH***：同态秘密共享的开山之作，发表在Crypto 2016，论文链接见[eprint](https://eprint.iacr.org/2016/585)
  + ***[BGI17]Group-Based Secure Computation: Optimizing Rounds, Communication, and Computation***：同态秘密共享的开山续作，发表在EuroCrypto 2017，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-319-56614-6_6) 
  + ***[BCG+17]Homomorphic Secret Sharing: Optimizations and Applications***：同态秘密共享的系统研究，发表在CCS 2017，论文链接见[eprint](https://eprint.iacr.org/2018/419)
+ ***[BCGI18]Compressing Vector OLE***
  + 基于函数秘密共享和LPN假设提出了一种快速生成 VOLE 伪随机实例的新方法
  + 论文发表在CCS 2018，论文链接见[ACM](https://dl.acm.org/doi/10.1145/3243734.3243868)，[eprint](https://eprint.iacr.org/2019/273)
+ :triangular_flag_on_post:***[BCG+19]Efficient Pseudorandom Correlation Generators: Silent OT Extension and More***
  + 正式提出伪随机相关生成器，并给出其定义和安全性定义，同时为OT相关性、两方相关性和多方相关性提出伪随机相关生成器构造
  + 论文发表在CRYPTO 2019，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-030-26954-8_16)，[eprint](https://eprint.iacr.org/2019/448)，论文汇报见[Video](https://www.youtube.com/watch?v=6XQgFCVg6d4&list=PLeeS-3Ml-rppCQ2B6cqzZinF3352qVYF4&index=68)
+ ***[BCG+19]Efficient Two-Round OT Extension and Silent Non-Interactive Secure Computation***
  + 基于伪随机相关生成器构造了两轮的OT扩展
  + 论文发表在CCS 2019，论文链接见[ACM](https://dl.acm.org/doi/10.1145/3319535.3354255)，[eprint](https://eprint.iacr.org/2019/1159)
+ ***[BCG+20]Efficient Pseudorandom Correlation Generators from Ring-LPN***
  + 基于环上LPN假设设计了高效的伪随机相关生成器构造
  + 论文发表在CRYPTO 2020，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-030-26954-8_16)，[eprint](https://eprint.iacr.org/2019/448)，论文汇报见[Slides](https://iacr.org/submit/files/slides/2020/crypto/crypto2020/401/slides.pdf)
+ ***[BCG+20]Correlated Pseudorandom Functions from Variable-Density LPN***
  + 基于Variable-Density LPN的伪随机相关函数，其是伪随机相关生成器的推广
  + 论文发表在FOCS 2020，论文链接见[eprint](https://eprint.iacr.org/2020/1417)
+ ***[BGIN21]Sublinear GMW-Style Compiler for MPC with Preprocessing***
  + 提出了具有亚线性离线阶段的GMW范式安全多方计算
  + 论文发表在CRYPTO 2021，论文链接见[SPringer](https://link.springer.com/chapter/10.1007/978-3-030-84245-1_16)，[eprint](https://eprint.iacr.org/2022/261)
+ ***[BGIN22]Secure Multiparty Computation with Sublinear Preprocessing***
  + 提出了第一个针对（恶意）MPC 进行预处理的具体有效方法，其中离线通信在电路大小上是次线性的
  + 论文发表在EUROCRYPT 2022，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-031-06944-4_15)，论文汇报见[Slides](https://iacr.org/submit/files/slides/2022/eurocrypt/eurocrypt2022/376/slides.pptx), [Video](https://www.youtube.com/watch?v=bmTcgj_dmsY&list=PLeeS-3Ml-rpo46w2onH4CGzlHZ8uwa1w5&index=23)
+ ***[BCM22]Correlated Pseudorandomness from Expand-Accumulate Codes***
  + 引入了一种基于所谓的扩展累积码的简单 PCG 新设计
  + 论文发表在CRYPTO 2022，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-031-15979-4_21)，[eprint](https://eprint.iacr.org/2022/1014)
+ ***[BCM22]Sublinear Secure Computation from New Assumptions***
  + 通过利用新技术来扩展亚线性通信的计算假设集
  + 论文发表在TCC 2022，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-031-22365-5_5)，[eprint](https://eprint.iacr.org/2023/513)
+ ***[AS22]Low-Communication Multiparty Triple Generation for SPDZ from Ring-LPN***
  + 基于3方DPF构造，提出了面向SPDZ的多方元组生成，而现有工作支持两方的构造
  + 论文发表在PKC 2022，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-030-97121-2_9)，[eprint](https://eprint.iacr.org/2022/315.pdf)
+ ***[BCG+23]Oblivious Transfer with Constant Computational Overhead***
  + 基于用于bit-OT相关的恒定开销伪随机相关生成器PCG，提出了具有常数计算代价的不经意传输协议
  + 论文发表在EUROCRYPT 2023，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-031-30545-0_10)，[eprint](https://eprint.iacr.org/2023/817)
+ ***[BCM23]Sublinear-Communication Secure Multiparty Computation Does Not Require FHE***
  + 基于N方函数秘密共享的特定形式构建了一个用于实现安全N+1方计算框架，且离线通信为亚线性复杂度
  + 论文发表在EUROCRYPT 2023，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-031-30617-4_6)
+ ***[CD23]Pseudorandom Correlation Functions from Variable-Density LPN, Revisited***
  + [BCG+20]Correlated Pseudorandom Functions from Variable-Density LPN的进一步工作
  + 发表在PKC 23，论文链接见[Springe](https://link.springer.com/chapter/10.1007/978-3-031-31371-4_8)，[eprint](https://eprint.iacr.org/2023/650)

### 2.2 相关随机性阅读材料

这里列出一些相关随机性，以及对应的论文
+ 乘法三元组，以及认证乘法三元组
+ 二项式元组和算术元组
  + ***[RRKK22]Arithmetic Tuples for MPC***
    + 作者为Pascal Reisert, Marc Rivinius,Toomas Krips, Ralf Kuesters，论文链接见[eprint](https://eprint.iacr.org/2022/667)
+ OT相关随机性（ROT、COT和OT）
+ VOLE相关随机性（OLE、R-OLE和VOLE）
+ 查找表（Lookup Table）
  + ***[IKM+13]On the Power of Correlated Randomness in Secure Computation***
    + Ishai等人在2013年研究了相关随机性能在多大程度上帮助构造不诚实大多数的安全多方计算协议，称为OTTT协议
    + 论文发表在TCC 2013，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-642-36594-2_34)，[eprint](https://www.iacr.org/archive/tcc2013/77850598/77850598.pdf)
  + ***[DNNR17]The TinyTable protocol for 2-Party Secure Computation, or: Gate-scrambling Revisited***
    + 利用真值表来实现所有函数的预处理模型下安全计算，该方法针对布尔电路
    + 发表在Crypto 2017，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-319-63688-7_6)，[eprint](https://eprint.iacr.org/2016/695)
  + ***[DKS+17]Pushing the Communication Barrier in Secure Computation using Lookup Tables***
    + 发表在NDSS 2017，论文链接见[eprint](https://eprint.iacr.org/2018/486.pdf)
  + ***[BHS+23]FLUTE: Fast and Secure Lookup Table Evaluations***
    + 发表在SP 2023，论文链接见[eprint](https://eprint.iacr.org/2023/499)

</details>

## 3. VOLE、PCG和安全计算

从结构上看，VOLE是一种相关性，PCG是生成相关性的生成器，预处理模型下的安全计算则依赖于相关性。


![prg](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/assets/66773755/5e376bcf-f456-464e-9fb9-8a9d3851f76e)

