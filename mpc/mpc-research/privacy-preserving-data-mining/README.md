# 隐私保护数据挖掘

## 1. 隐私保护机器学习

基于安全多方计算、同态加密实现隐私保护机器学习的训练和推理，主要包括隐私保护线性回归、逻辑回归、神经网络和泊松回归。

<details>
<summary>以下是隐私保护机器学习相关论文，请点击展开</summary>

+ :triangular_flag_on_post: ***[DSZ15]ABY-A framework for efficient mixed-protocol secure two-party computation***
  + 混合协议开篇之作，ABY：算术秘密份额（A）、布尔秘密份额（B）和姚氏秘密份额（Y）
  + 发表在NDSS 2015，论文链接见[NDSS 2015](https://www.ndss-symposium.org/ndss2015/ndss-2015-programme/aby-framework-efficient-mixed-protocol-secure-two-party-computation/)，[encryptogroup](http://thomaschneider.de/papers/DSZ15.pdf)
+ ***[GSB+17]Privacy-Preserving Distributed Linear Regression on High-Dimensional Data***
  + 高维数据的隐私保护线性回归
  + 发表在PoPETS 2017，论文链接见[PoPETS](https://petsymposium.org/popets/2017/popets-2017-0053.php)，[eprint](https://eprint.iacr.org/2016/892.pdf)、对应的slides见[Slide](http://archive.dimacs.rutgers.edu/Workshops/RAM/Slides/raykova.pdf)
+ :triangular_flag_on_post: ***[MZ17]SecureML: A system for scalable privacy-preserving machine learning***
  + 隐私保护机器学习（线性回归、逻辑回归和神经网络）
  + 发表在S&P 2017，论文链接见[eprint](https://eprint.iacr.org/2017/396.pdf)
+ ***[LJLA17]Oblivious Neural Network Predictions via MiniONN Transformations***
  + 基于安全两方计算的安全二值神经网络推理，实现能将任何神经网络都转换为安全神经网络推理（即通用安全神经网络推理方案）
  + 发表在CCS 2017，论文链接见[ACM CCS](https://dl.acm.org/doi/abs/10.1145/3133956.3134056)，[eprint](https://eprint.iacr.org/2017/452)
+ ***[JVC18]GAZELLE: A Low Latency Framework for Secure Neural Network Inference***
  + 基于同态加密和安全多方计算（混淆电路）实现的安全两方神经网络推理，是第一份将同态加密和安全多方计算结合起来的工作
  + 论文发表在USENIX 2018，论文链接见[USENIX](https://www.usenix.org/conference/usenixsecurity18/presentation/juvekar)，[ICAR eprint](https://eprint.iacr.org/2018/073)
+ ***[MR18]ABY3: A mixed protocol framework for machine learning***
  + 利用复制秘密共享技术提出了恶意模型下基于混合协议的安全三方计算通用框架ABY3，但仅在半诚实模型下实现了线性回归、逻辑回归和神经网络的安全计算
  + 论文发表在CCS 2018，论文链接见[ACM CCS](https://dl.acm.org/doi/abs/10.1145/3243734.3243760)，[eprint](https://eprint.iacr.org/2018/403)
+ ***Trident: Efficient 4PC Framework for Privacy Preserving Machine Learning***
+ ***QUOTIENT: Two-Party Secure Neural Network Training and Prediction***
+ ***New Primitives for Actively-Secure MPC over Rings with Applications to Private Machine Learning***
+ ***[RSC+19]XONN:XNOR-based Oblivious Deep Neural Network Inference***
  + 安全两方二值神经网络推理
  + 发表在USENIX 2019，论文链接见[USENIX](https://www.usenix.org/conference/usenixsecurity19/presentation/riazi)，[eprint](https://eprint.iacr.org/2019/171)
+ ***[WGC+19]SecureNN-3-Party Secure Computation for Neural Network Training***
  + 安全三方隐私保护神经网络训练，发表在PoPETS2019
  + 论文链接见[PoPETS 2019](https://petsymposium.org/popets/2019/popets-2019-0035.php)
+ ***2020：[Effectiveness of MPC-friendly Softmax Replacement](https://arxiv.org/abs/2011.11202)***
+ ***[MLS+20]DELPHI:a cryptographic inference service for neural networks***
  + 基于安全多方计算的神经网络推理，采用neural architecture search (NAS)来平衡效率和精度
  + 论文发表在USENIX 2020上，论文链接见[IACR eprint](https://eprint.iacr.org/2020/050)
+ ***[RRK+20]CrypTFlow2: Practical 2-Party Secure Inference***
  + 安全两方神经网络推理
  + 发表在CCS 2020，论文链接见[eprint](https://eprint.iacr.org/2020/1002)
+ ***[Privacy-Preserving Decision Trees Training and Prediction](https://dl.acm.org/doi/pdf/10.1145/3517197)***
+ ***[PSSY21]ABY2.0: Improved Mixed-Protocol Secure Two-Party Computation***
  + 在ABY框架的基础上进一步减少了秘密份额转换的开销，降低了协议的通信开销
  + 论文发表在USENIX 2021，论文链接见[USENIX](https://www.usenix.org/conference/usenixsecurity21/presentation/patra)，[eprint](https://eprint.iacr.org/2020/1225)
+ ***[CZW+21]When Homomorphic Encryption Marries Secret Sharing: Secure Large-Scale Sparse Logistic Regression and Applications in Risk Control***
  + 结合秘密共享和同态加密实现稀疏数据的逻辑回归
  + 发表在KDD 2021，文章链接见[ACM](https://dl.acm.org/doi/10.1145/3447548.3467210)，[arXiv](https://arxiv.org/pdf/2008.08753.pdf)
+ ***[LMSP21]Muse:Secure Inference Resilient to Malicious Clients***
  + 抵抗恶意客户端的恶意安全机器学习推理
  + 发表在USENIX 2021，论文链接见[USENIX](https://www.usenix.org/conference/usenixsecurity21/presentation/lehmkuhl), [IACR-eprint](https://eprint.iacr.org/2021/1040)
+ ***[BDST22]MOTION - A Framework for Mixed-Protocol Multi-Party Computation***
  + ABY的多方版本，文章中详细论述了ABY系列协议
  + 发表在TOPS 2022，论文链接见[eprint](https://eprint.iacr.org/2020/1137)，[ACM](https://dl.acm.org/doi/abs/10.1145/3490390)
+ ***[ZWLL22]SecureBiNN-3-Party Secure Computation for Binarized Neural Network Inference***
  + 安全三方二值神经网络推理
  + 发表在ESORICS 2022，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-031-17143-7_14)
+ ***[APR+22]Communication Efficient Secure Logistic Regression***
  + 基于函数秘密共享和秘密共享结合的安全两方逻辑回归
  + 论文链接见[eprint](https://eprint.iacr.org/2022/866)
+ ***[HLHD22]Cheetah:Lean and Fast Secure Two-Party Deep Neural Network Inference***
  + 安全两方神经网络推理，基于秘密共享和同态加密
  + 阿里巴巴双子座实验室发表在USENIX 2022上的论文，论文链接见[USENIX](https://www.usenix.org/conference/usenixsecurity22/presentation/huang-zhicong)、[eprint](https://eprint.iacr.org/2022/207)
+ ***[CGOS22]SIMC: ML Inference Secure Against Malicious Clients at Semi-Honest Cost***
  + 抵抗恶意服务器的恶意安全机器学习推理
  + 发表在USENIX 2022，论文链接见[USENIX](https://www.usenix.org/conference/usenixsecurity22/presentation/chandran)
+ ***[DWL+23]Fusion: Efficient and Secure Inference Resilient to Malicious Server and Curious Clients***
  + 抵抗恶意服务器的恶意安全机器学习推理
  + 发表在NDSS 2023，论文链接在[NDSS](https://www.ndss-symposium.org/ndss-paper/fusion-efficient-and-secure-inference-resilient-to-malicious-servers/)，[Arxiv eprint](https://arxiv.org/abs/2205.03040)
+ ***[BBY23]Multi-Party Replicated Secret Sharing over a Ring with Applications to Privacy-Preserving Machine Learning***
  + 多方复制秘密共享技术及其在隐私保护机器学习上的应用
  + 发表在PoPETS 2023，论文链接见[ICAR eprint](https://eprint.iacr.org/2020/1577)
+ ***[RRHK23]Convolutions in Overdrive - Maliciously Secure Convolutions for MPC***
  + 恶意安全卷积运算
  + 发表在PoPETS 2023，论文链接见[ICAR eprint](https://eprint.iacr.org/2023/359)
+ ***[TJB23]A Method for Securely Comparing Integers using Binary Trees***
  + 安全整数比较算法
  + 发表在PoPETS 2023，论文链接见[ICAR eprint](https://eprint.iacr.org/2021/1646)
+ ***[KBM23]Faster Secure Comparisons with Offline Phase for Efficient Private Set Intersection***
  
  
  
</details>

## 2. 隐私保护特征工程

+ ***[LDC21]Privacy-preserving feature selection with secure multiparty computation***
  + 基于安全多方计算的隐私保护特征选择
  + 发表在PMLR 2021，论文链接见[PMLR](http://proceedings.mlr.press/v139/li21e/li21e.pdf)、[ICAR eprint](https://eprint.iacr.org/2021/132)、[Arxiv eprint](https://arxiv.org/abs/2102.03517)
+ ***[SDH21]Feature Engineering Framework based on Secure Multi-Party Computation in Federated Learning***
  + 发表在IEEE HPCC/DSS/SmartCity/DependSys，论文链接见[IEEE](https://ieeexplore.ieee.org/abstract/document/9780936/)



## 3. 联合统计分析
+ ***[KLRS22]Secure Poisson Regression***
  + 安全两方泊松回归
  + 发表在USENIX 2022，论文链接见[USENIX 2022](https://www.usenix.org/conference/usenixsecurity22/presentation/kelkar)，[eprint](https://eprint.iacr.org/2021/208)
