# 安全多方计算

在这里，我们按主题列出一些优秀的MPC相关的论文：

## MPC综述
+ [Secure Multiparty Computation (MPC)](https://eprint.iacr.org/2020/300.pdf)
  + 机构&作者：以色列BIU大学Yehuda Lindell
  + 会议/期刊&年份：Communications of the ACM, 2020
  + 主要内容：详细介绍了目前安全多方计算领域的基本概念和发展趋势，该文章不涉及复杂的公式，只有一些基本的概念
+ [实用安全多方计算协议关键技术研究进展](https://crad.ict.ac.cn/CN/10.7544/issn1000-1239.2015.20150763)
  + 机构&作者：山东大学计算机科学与技术学院[蒋瀚](https://www.sc.sdu.edu.cn/info/1043/2243.htm)、[徐秋亮](https://www.sc.sdu.edu.cn/info/1043/2238.htm)
  + 会议/期刊&年份：计算机研究与发展，2015
  + 主要内容：介绍了实用化安全多方计算协议研究的主要进展和成果，并重点介绍安全多方计算实用化的3个支撑性重要技术，包括混乱电路优化、剪切-选择技术及不经意传输扩展技术，这些技术在不同的方面显著提高了安全多方计算协议的效率。
+ [Practical Secure Computation Outsourcing: A Survey](https://dl.acm.org/doi/pdf/10.1145/3158363)
  + 机构&作者：ZIHAO SHAN, KUI REN, and MARINA BLANTON(State University of New York at Buffalo) | CONG WANG(City University of Hong Kong)
  + 会议/期刊&年份：ACM Computating Survey，2018
  + 主要内容：主要介绍了安全外包计算的基本技术，并对比了各种技术，同时也介绍了安全外包计算的一些应用

## 隐私保护数据挖掘

详见[隐私保护数据挖掘](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/privacy-preserving-data-mining)

## 恶意模型下的安全多方计算

详见[恶意模型下的安全多方计算](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/malicious-mpc)

## 其他
+ [Scalable Secure Multiparty Computation](https://link.springer.com/chapter/10.1007/11818175_30)
  + 机构&作者：Ivan Damgård & Yuval Ishai
  + 期刊/论文：Crypto2006
+ [SecFloat: Accurate Floating-Point meets Secure 2-Party Computation](https://eprint.iacr.org/2022/322.pdf)
  + 作者：Deevashwer Rathee等
  + 期刊/论文：S&P2022
  + 主要内容：介绍了安全两方计算的浮点数运算
  + 阅读笔记：[SecFloat：面向精确浮点计算的安全两方计算](https://mp.weixin.qq.com/s/feyQD5OlEuRENrz2U1oSCg)
+ [Arithmetic Tuples for MPC](https://eprint.iacr.org/2022/667.pdf)
  + 作者&机构：Pascal Reisert, Marc Rivinius and Ralf Küsters(Institute of Information Security, University of Stuttgart, Germany), Toomas Krips(University of Tartu, Estonia)
  + 主要内容：预处理模型下的安全多方计算乘法三元组优化
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
  + 秘密共享综述，2011年
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
