# 向量不经意线性函数计算VOLE和伪随机相关生成器PCG

向量不经意线性函数计算（Vector Oblivious Linear Evaluation, VOLE）是一种十分有用的相关随机性（Correlated Randomness），这些相关随机性可以由一种称为伪随机相关生成器（Pseudorandom Correlation Generator, PCG）来生成，PCG的构造主要依赖于[函数秘密共享](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/function-secret-sharing)、[同态秘密共享](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/homomorphic-secret-sharing)和LPN（Learning Parity with Noise）假设来构造。

## 1. 伪随机相关生成器领域的相关大牛
+ [Elette Boyle](https://cs.idc.ac.il/~elette/)：提出伪随机相关生成器PCG，并针对VOLE相关随机性提出了基于PCG的高效方案
+ [Geoffroy Couteau](https://geoffroycouteau.github.io/)：和Boyle一起合作了伪随机相关生成器PCG的开创性论文
+ [Niv Gilboa](https://www.bgu.ac.il/~gilboan)：系统研究伪随机相关生成器PCG
+ [Yuval Ishai](https://www.cs.technion.ac.il/~yuvali/)：Boyle的老师，其和Niv Gilboa一起系统研究伪随机相关生成器PCG
+ [Peter Scholl](https://dblp.org/pid/00/10576.html)：对预处理模型下的安全多方计算很有研究
+ [Lisa Kohl](https://lisakohl.me/)：Yuval Ishai的学生

## 2. 伪随机相关生成器相关论文
+ ***[Bea91]Efficient Multiparty Protocols Using Circuit Randomization***
  + 预处理模型最早源于Beaver的工作，Beaver针对BGW协议的复杂乘法运算，提出了乘法三元组的概念（后也称Beaver三元组），用一轮交互便可完成一次乘法运算，大大提高了乘法运算的效率。
  + 论文发表在CRYPTO 1991，论文链接见[Springer](https://link.springer.com/chapter/10.1007/3-540-46766-1_34)
+ ***Function Secret Sharing***
  + Elette Boyle等人在2015年提出函数秘密共享（Function Secret Sharing, FSS），详见[Function Secret Sharing](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/function-secret-sharing)
+ ***Homomorphic Secret Sharing***
  + Elette Boyle等人在2016年提出同态秘密共享（Homomorphic Secret Sharing, HSS），详见[Homomorphic Secret Sharing](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/homomorphic-secret-sharing)。在研究同态秘密共享时，Boyle等人提出了伪随机相关生成器的概念。
+ ***[DNNR17]The TinyTable protocol for 2-Party Secure Computation, or: Gate-scrambling Revisited***
  + 利用真值表来实现所有函数的预处理模型下安全计算，该方法针对布尔电路
  + 发表在Crypto 2017，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-319-63688-7_6)，[eprint](https://eprint.iacr.org/2016/695)
+ :triangular_flag_on_post:***[BCGI18]Compressing Vector OLE***
  + 基于函数秘密共享和LPN假设提出了一种快速生成 VOLE 伪随机实例的新方法
  + 论文发表在CCS 2018，论文链接见[ACM](https://dl.acm.org/doi/10.1145/3243734.3243868)，[eprint](https://eprint.iacr.org/2019/273)
+ :triangular_flag_on_post:***[BCG+19]Efficient Pseudorandom Correlation Generators: Silent OT Extension and More***
  + 正式提出伪随机相关生成器，并给出其定义和安全性定义，同时为OT相关性、两方相关性和多方相关性提出伪随机相关生成器构造
  + 论文发表在CRYPTO 2019，论文链接见[SPringer](https://link.springer.com/chapter/10.1007/978-3-030-26954-8_16)，[eprint](https://eprint.iacr.org/2019/448)
+ ***[BCG+20]Efficient Pseudorandom Correlation Generators from Ring-LPN***
  + 基于环上LPN假设设计了高效的伪随机相关生成器构造
  + 论文发表在CRYPTO 2020，论文链接见[SPringer](https://link.springer.com/chapter/10.1007/978-3-030-26954-8_16)，[eprint](https://eprint.iacr.org/2019/448)
+ ***[BGIN]Sublinear GMW-Style Compiler for MPC with Preprocessing***
  + 提出了具有亚线性离线阶段的GMW范式安全多方计算
  + 论文发表在CRYPTO 2021，论文链接见[SPringer](https://link.springer.com/chapter/10.1007/978-3-030-84245-1_16)，[eprint](https://eprint.iacr.org/2022/261)
+ ***[BCG+20]Efficient Pseudorandom Correlation Generators from Ring-LPN***
  + 基于环上LPN假设设计了高效的伪随机相关生成器构造
  + 论文发表在EUROCRYPT 2022，论文链接见[SPringer](https://link.springer.com/chapter/10.1007/978-3-031-06944-4_15)

