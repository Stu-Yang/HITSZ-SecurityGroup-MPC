# S&P中MPC相关论文


## S&P 2024

> 详见[IEEE S&P 2024-Accepted Papers](xxx)。

<details>
<summary>以下是S&P 2024中MPC相关论文，请点击展开</summary>

+ ***Orca: FSS-based Secure Training and Inference with GPUs***
  + 基于函数秘密共享的安全神经网络训练，并用GPU进行加速
  + 论文链接见[IEEE](https://www.computer.org/csdl/proceedings-article/sp/2024/313000a063/1RjEaAAmAAE), [eprint](https://eprint.iacr.org/2023/206)

</details>


## S&P 2023

> 详见[IEEE S&P 2023-Accepted Papers](https://www.ieee-security.org/TC/SP2023/program-papers.html)和[IEEE S&P 2023-Online Papers](https://ieeexplore.ieee.org/xpl/conhome/10179215/proceeding)。

<details>
<summary>以下是S&P 2023中MPC相关论文，请点击展开</summary>

+ ***Vectorized Batch Private Information Retrieval***
  + 利用vectorized homomorpohic encryption改进batch PIR
  + 论文链接见[IEEE](https://ieeexplore.ieee.org/abstract/document/10179329), [eprint](https://eprint.iacr.org/2022/1262)
+ ***SoK: Cryptographic Neural-Network Computation***
  + 隐私保护神经网络计算综述
  + 论文链接见[IEEE](https://ieeexplore.ieee.org/document/10179483/)
+ ***Flamingo: Multi-Round Single-Server Secure Aggregation with Applications to Private Federated Learning***
  + 基于多轮单服务器安全模型聚合算法的隐私保护联邦学习
  + 论文链接见[IEEE](https://ieeexplore.ieee.org/document/10179434/), [eprint]()，论文相关资料见[video](https://www.youtube.com/watch?v=Jtij2oJax14)
+ ***FLUTE: Fast and Secure Lookup Table Evaluations***
  + 基于查找表实现半诚实安全两方计算，性能比最好的半诚实安全两方计算ABY2.0好
  + 论文链接见[IEEE](https://ieeexplore.ieee.org/document/10179345/)，[eprint](https://eprint.iacr.org/2023/499)，论文相关资料见[video](https://www.youtube.com/watch?v=fO9uEPh8t7M), [code](https://github.com/encryptogroup/FLUTE), [paper-report](https://zhuanlan.zhihu.com/p/623249935)
+ ***Bicoptor: Two-round Secure Three-party Non-linear Computation without Preprocessing for Privacy-preserving Machine Learning***
  + 基于安全三方计算的两轮安全比较运算
  + 论文链接见[IEEE](https://ieeexplore.ieee.org/abstract/document/10179449/), [Arixv](https://arxiv.org/abs/2210.01988)，论文相关资料见[video](https://www.youtube.com/watch?v=oaeycdolvVg)
+ ***Private Access Control for Function Secret Sharing***
  + 研究函数秘密共享FSS访问控制，支持FSS的新应用，例如多方环境中的匿名身份验证，私人数据库中的访问控制，以及匿名通信系统中的身份验证和垃圾邮件预防
  + 论文链接见[IEEE](https://ieeexplore.ieee.org/abstract/document/10179295/), [eprint](https://eprint.iacr.org/2022/1707)，论文相关资料见[video](https://www.youtube.com/watch?v=qhwJPDvIrPY)
+ ***MPCAuth: Multi-factor Authentication for Distributed-trust Systems***
  + 提出一个用于分布式信任应用程序的多因素身份验证系统MPCAuth
  + 论文链接见[IEEE](https://ieeexplore.ieee.org/abstract/document/10179481/), [eprint](https://eprint.iacr.org/2021/342)，论文相关资料见[video](https://www.youtube.com/watch?v=aK6ZdW5zGog)

</details>

## S&P 2022

> 详见[S&P 2022 accepted-papers](https://www.ieee-security.org/TC/SP2022/program-papers.html)

<details>
<summary>以下是S&P 2022中MPC相关论文，请点击展开</summary>

+ [Multi-Server Verifiable Computation of Low-Degree Polynomials](https://www.computer.org/csdl/proceedings-article/sp/2022/131600b499/1A4Q4ozkJbi)
  + 作者&机构：Liang Feng Zhang (ShanghaiTech University), Huaxiong Wang (Nanyang Technological University)
  + 主要研究内容：可验证计算允许计算能力较弱的用户将复杂计算任务委托（外包）给计算资源密集的云服务器并对云服务器计算过程的正确性进行验证。更多介绍见[信息学院张良峰课题组在多服务器非交互式可验证计算研究方面取得重要进展](https://sist.shanghaitech.edu.cn/2021/1129/c2858a166288/page.htm)
  + 相关工作：[Two-Server Verifiable Homomorphic Secret Sharing for High-Degree Polynomials](https://arxiv.org/abs/2104.12163)
+ [Private Nearest Neighbor Search with Sublinear Communication and Malicious Security](https://eprint.iacr.org/archive/2021/1157/20211217:135438)
  + 作者&机构：Sacha Servan-Schreiber (Massachusetts Institute of Technology), Simon Langowski (Massachusetts Institute of Technology), Srinivas Devadas (Massachusetts Institute of Technology)
  + 主要研究内容：具有**次线性通信**和恶意安全的隐私最近邻搜索(轻量级)
+ [Publicly Accountable Robust Multi-Party Computation](https://eprint.iacr.org/2022/436.pdf)
  + 作者&机构：Marc Rivinius (University of Stuttgart), Pascal Reisert (University of Stuttgart), Daniel Rausch (University of Stuttgart), Ralf Küsters (University of Stuttgart)
  + 主要内容：恶意安全多方计算协议
+ [SecFloat: Accurate Floating-Point meets Secure 2-Party Computation](https://www.microsoft.com/en-us/research/uploads/prod/2022/04/main-6266710a3c049.pdf)
  + 作者&机构：Deevashwer Rathee (UC Berkeley), Anwesh Bhattacharya (Microsoft Research India), Rahul Sharma (Microsoft Research India), Divya Gupta (Microsoft Research India), Nishanth Chandran (Microsoft Research India), Aseem Rastogi (Microsoft Research India)
  + 主要研究内容：支持浮点数的安全两方计算协议
+ [Sphinx: Enabling Privacy-Preserving Online Learning over the Cloud](https://cse.hkust.edu.hk/~kaichen/papers/sphinx-sp22.pdf)
  + 作者&机构：Han Tian (Hong Kong University of Science and Technology), Chaoliang Zeng (Hong Kong University of Science and Technology), Zhenghang Ren (Hong Kong University of Science and Technology), Di Chai (Hong Kong University of Science and Technology), Junxue ZHANG (Hong Kong University of Science and Technology), Kai Chen (Hong Kong University of Science and Technology), Qiang Yang (Hong Kong University of Science and Technology)
  + 主要研究内容：该研究提出了一种隐私保护在线深度学习框架 Sphinx，该学习框架无需任何受信任的第三方，并且在训练和推理中较之前方案都有明显提升。Sphinx 将其神经网络模型中的线性参数 (linear) 保持为明文，并使用差分隐私技术进行隐私保护；其加和偏差部分模型参数 (bias) 使用同态加密技术进行加密保护。Sphinx 结合同态加密、差分隐私和秘密共享多种隐私保护技术，根据训练和推理的具体任务特点提出了定制且兼容的训练和推理混合协议，从而实现快速的训练和推理计算。Sphinx 通过对隐私保护场景下推理和训练协议进行系统优化，在模型性能、计算效率和隐私保护之间取得平衡
  + 更多内容详见[IEEE S&P 2022丨速度提升达4-6个数量级，港科大、星云Clustar联合提出隐私保护的在线机器学习新框架](https://cloud.tencent.com/developer/article/1964982)
+ [Spiral: Fast, High-Rate Single-Server PIR via FHE Composition](https://eprint.iacr.org/2022/368.pdf)
  + 作者&机构：Samir Jordan Menon (None), David J. Wu (UT Austin)
  + 主要研究内容：针对单服务器隐私信息检索问题，利用同态加密技术，在不泄露用户隐私的情况下完成隐私检索任务
+ [Waldo: A Private Time-Series Database from Function Secret Sharing](https://eprint.iacr.org/2021/1661)
  + 作者&机构：Emma Dauterman (UC Berkeley), Mayank Rathee (UC Berkeley), Raluca Popa (UC Berkeley), Ion Stoica (UC Berkeley)

</details>
