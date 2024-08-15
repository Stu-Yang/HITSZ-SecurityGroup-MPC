# 安全多方计算（Secure Multiparty Computation, MPC）

在这里，我们按主题列出一些安全多方计算主题，另外按照会议/期刊记录的文章请参考[top conferences and journals](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/conferences%26journals)。

## 0. 安全多方计算综述

关于安全多方计算的一些综述，详见[安全多方计算综述](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/mpc-survery)

## 1. 安全多方计算理论研究

### 1.1 恶意模型下的安全多方计算（Malicious MPC）

详见[恶意模型下的安全多方计算](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/malicious-mpc)，研究报告详见[malicious-mpc](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/blob/main/mpc/mpc-research/malicious-mpc/malicious-mpc.pdf)

#### 1.1.2 Z2k上的不诚实大多数恶意MPC

详见[Z2k上的不诚实大多数恶意MPC](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/mpcZ2k)，和下面的[预处理模型下的安全多方计算](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/mpc-with-preprocessing)有交叉

### 1.2 预处理模型下的安全多方计算（MPC in the preprocessing model）

在预处理模型（Preprocessing Model）中，协议被分为离线阶段（Offline Phase）和在线阶段（Online Phase）。在离线阶段（也称为预处理阶段（Preprocessing Phase）和设置阶段（Setup Phase）），各个参与方共同运行一个与数据独立安全协议来产生相关随机性（correlated randomness），这些相关值可以辅助完成计算任务；在线阶段则利用预处理阶段提供的相关值，基于参与方的数据来计算功能函数。

#### 1.2.1 预处理模型下的安全多方计算进展

详见[预处理模型下的安全多方计算](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/mpc-with-preprocessing)，研究报告详见[correlated-randomness-in-the-preprocessing-model](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/blob/main/mpc/mpc-research/mpc-with-preprocessing/correlated-randomness-in-the-preprocessing-model.pdf)

#### 1.2.2 函数秘密共享、同态秘密共享

函数秘密共享（Function secret sharing, FSS）和同态秘密共享（Homomorphic Secret Sharing, HSS）是[Elette Boyle](https://cs.idc.ac.il/~elette/)提出的密码学原语，详见
+ [函数秘密共享](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/function-secret-sharing)
+ [同态秘密共享](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/homomorphic-secret-sharing)

#### 1.2.3 伪随机相关生成器

向量不经意线性函数计算（Vector Oblivious Linear Evaluation, VOLE）是一种十分有用的相关随机性，这些相关随机性可以由一种称为伪随机相关生成器（Pseudorandom Correlation Generator, PCG）来生成，PCG的构造主要依赖于函数秘密共享、同态秘密共享和LPN（Learning Parity with Noise）假设来构造。详见

+ [VOLE和PCG](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/vole-and-pcg)

> **Elette Boyle等人在2022年撰写了关于函数秘密共享、同态秘密共享和伪随机相关生成器的综述，详见[Survey-FSS-HSS-PCG](https://cs.idc.ac.il/~elette/HSS_FSS-Survey.pdf)**

#### 1.2.4 Shamir secret sharing and Packed Shamir secret sharing

详见[Shamir secret sharing and Packed Shamir secret sharing](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/sss-and-psss)


### 1.3 基于混淆电路的安全多方计算协议

详见[基于混淆电路的安全多方计算协议](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/gc-based-mpc)

### 1.4 私有函数评估（Private Function Evaluation， PFE）

详见[私有函数评估（Private Function Evaluation， PFE）](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/pfe)


### 1.5 基于ORAM程序的安全多方计算协议

参考[slides](https://web.engr.oregonstate.edu/~rosulekm/pubs/malram-talk.pdf)



### 1.Z 其他模型下的安全多方计算协议

#### 1.5.1 支持动态参与方的安全多方计算协议（Fluid MPC）

+ ***Fluid MPC: Secure Multiparty Computation with Dynamic Participants***
  + 论文发表在CRYPTO 2021，论文链接见[IACR eprint](https://eprint.iacr.org/2020/754)
+ ***Le Mans: Dynamic and Fluid MPC for Dishonest Majority***
  + 论文发表在CRYPTO 2022，论文链接见[IACR eprint](https://eprint.iacr.org/2021/1579)
+ ***Maximally-Fluid MPC with Guaranteed Output Delivery***
  + 论文发表在CRYPTO 2023，论文链接见[IACR eprint](https://eprint.iacr.org/2023/415)


## 2. 安全多方计算应用研究

### 2.1 隐私保护数据挖掘（Privacy-Preserving Data Mining）

详见[隐私保护数据挖掘](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/privacy-preserving-data-mining)，主要包括以下内容：
  + [隐私保护机器学习](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/privacy-preserving-data-mining#1-%E9%9A%90%E7%A7%81%E4%BF%9D%E6%8A%A4%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0)：基于安全多方计算设计安全机器学习训练和推理，保护数据隐私和模型隐私
  + [隐私保护特征工程](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/privacy-preserving-data-mining#2-%E9%9A%90%E7%A7%81%E4%BF%9D%E6%8A%A4%E7%89%B9%E5%BE%81%E5%B7%A5%E7%A8%8B)：基于安全多方计算设计安全特征工程，结合隐私保护机器学习实现全过程安全多方保护机器学习

### 2.2 隐私保护数据库使用

基于安全多方计算实现安全数据库查询、秘密分享数据的隐私集合求交、隐私信息检索和隐私频繁项查询等，详见[database-query](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/database-query)
+ [密态数据库查询（Encrypted database Query）](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/database-query#11-%E5%AF%86%E6%80%81%E6%95%B0%E6%8D%AE%E5%BA%93%E6%9F%A5%E8%AF%A2encrypted-database-query)
+ [秘密分享数据的隐私集合求交（PSI over secret-shared data）](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/database-query#12-%E7%A7%98%E5%AF%86%E4%BB%BD%E9%A2%9D%E6%95%B0%E6%8D%AE%E7%9A%84%E9%9A%90%E7%A7%81%E9%9B%86%E5%90%88%E6%B1%82%E4%BA%A4psi-over-secret-shared-data)
+ [隐私信息检索（Private Information Retrieval，PIR）](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/database-query#2-%E9%9A%90%E7%A7%81%E4%BF%A1%E6%81%AF%E6%A3%80%E7%B4%A2private-information-retrievalpir)
+ [隐私频繁项查询（Private Heavy Hitters）](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/database-query#3-%E9%9A%90%E7%A7%81%E9%A2%91%E7%B9%81%E9%A1%B9%E6%9F%A5%E8%AF%A2)


## X. 其他

<details>
<summary>以下是MPC其他主题的论文，请点击展开</summary>

+ [SecFloat: Accurate Floating-Point meets Secure 2-Party Computation](https://eprint.iacr.org/2022/322.pdf)
  + 作者：Deevashwer Rathee等
  + 期刊/论文：S&P2022
  + 主要内容：介绍了安全两方计算的浮点数运算
  + 阅读笔记：[SecFloat：面向精确浮点计算的安全两方计算](https://mp.weixin.qq.com/s/feyQD5OlEuRENrz2U1oSCg)
+ [Arithmetic Tuples for MPC](https://eprint.iacr.org/2022/667.pdf)
  + 作者&机构：Pascal Reisert, Marc Rivinius and Ralf Küsters(Institute of Information Security, University of Stuttgart, Germany), Toomas Krips(University of Tartu, Estonia)
  + 主要内容：预处理模型下的安全多方计算乘法三元组优化
+ [Scalable Secure Multiparty Computation](https://link.springer.com/chapter/10.1007/11818175_30)
  + 机构&作者：Ivan Damgård & Yuval Ishai
  + 期刊/论文：Crypto2006
+ [Publicly Accountable Robust Multi-Party Computation](https://eprint.iacr.org/2022/436.pdf)
  + 作者&机构：Marc Rivinius, Pascal Reisert, Daniel Rausch, and Ralf Küsters
  + 主要内容：实现public accountability, public verifiability and robustness的安全多方计算
+ [Two Round Multiparty Computation via Multi-Key FHE](https://eprint.iacr.org/2015/345.pdf)
  + 主要内容：用HE实现MPC
+ [Two-Round Multiparty Secure Computation Minimizing Public Key Operations](https://eprint.iacr.org/2018/180.pdf)
  + 主要内容：用HE实现MPC
+ [Efficient Privacy Preserving Logistic Regression Inference and Training](https://eprint.iacr.org/2020/1396.pdf)
  + 主要内容：结合MPC和HE实现隐私保护逻辑回归
+ [Secure Outsourced Matrix Computation and Application to Neural Networks](https://eprint.iacr.org/2018/1041.pdf)
  + 主要内容：结合MPC和HE实现安全矩阵运算和神经网络
+ [Secret-Sharing Schemes: A Survey](https://link.springer.com/content/pdf/10.1007/978-3-642-20901-7_2.pdf)
  + 2011年的一篇关于秘密共享的综述
+ SPDZ系列论文：[MP-SPDZ: A Versatile Framework for Multi-Party Computation](https://eprint.iacr.org/2020/521.pdf)
+ [Two-Server Verifiable Homomorphic Secret Sharing for High-Degree Polynomials](https://link.springer.com/chapter/10.1007/978-3-030-62974-8_5)
+ [Two Round Multiparty Computation via Multi-Key FHE](https://eprint.iacr.org/2015/345.pdf)
  + 应用多密钥全同态实现安全多方计算
+ [GMW vs. Yao? Efficient Secure Two-Party Computation with Low Depth Circuits](https://link.springer.com/content/pdf/10.1007/978-3-642-39884-1_23.pdf)
  + 高效安全两方计算
+ [Privacy-preserving cloud computing on sensitive data: A survey of methods, products and challenges](https://www.sciencedirect.com/science/article/pii/S0140366418310740)
  + 隐私保护云计算综述
+ [Privacy preserving in cloud computing environment](https://onlinelibrary.wiley.com/doi/10.1002/sec.1498)
  + 隐私保护云计算
+ [Highly Efficient Linear Regression Outsourcing to a Cloud](https://ieeexplore.ieee.org/document/6979197)
  + 安全外包计算：线性回归
+ [High-Precision Privacy-Preserving Real-Valued Function Evaluation](https://eprint.iacr.org/2017/1234)
  + 作者：Christina Boura, Ilaria Chillotti, Nicolas Gama, Dimitar Jetchev, Stanislav Peceny, and Alexander Petric
  + 主要内容：提出了一种新颖的多方计算协议来评估具有高数值精度的连续实值函数。
+ [Secure Computation from Elastic Noisy Channels](https://eprint.iacr.org/2016/497.pdf)
  + 作者：Dakshita Khurana, Hemanta K. Maji, and Amit Sahai
  + 主要内容：考虑带噪声信道的安全多方计算
+ [New Multiparty Computational Model: From Nakamoto to YOSO]()
  + 作者&机构：Tal Rabin (UPenn and Algorand Foundation)
  + 主要内容：提出了一个安全多方计算新模型
  + [Slide](https://asiaccs2022.conferenceservice.jp/doc/1K-1_slide.pdf)
+ [Cloud Computing Security: Foundations and Research Directions](https://www.nowpublishers.com/article/Details/SEC-028)
  + 作者&机构：By Anrin Chakraborti, Duke University, USA, anrin.chakraborti@duke.edu | Reza Curtmola, New Jersey Institute of Technology, USA, reza.curtmola@njit.edu | Jonathan Katz, University of Maryland, USA, jkatz@cs.umd.edu | Jason Nieh, Columbia University, USA, nieh@cs.columbia.edu | Ahmad-Reza Sadeghi, Technische Universität Darmstadt, Germany, ahmad.sadeghi@trust.tu-darmstadt.de | Radu Sion, Stony Brook University, USA, sion@cs.stonybrook.edu | Yinqian Zhang, Southern University of Science and Technology, China, yinqianz@acm.org
+ [Global-Scale Secure Multiparty Computation](https://eprint.iacr.org/2017/189.pdf)
  + 作者&机构：Xiao Wang, Samuel Ranellucci, and Jonathan Katz
  + 主要内容：We propose a new, constant-round protocol for multi-party computation of boolean circuits that is secure against an arbitrary number of malicious corruptions.
</details>
