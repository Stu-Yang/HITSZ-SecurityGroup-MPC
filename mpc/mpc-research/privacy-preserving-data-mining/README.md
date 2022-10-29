# 隐私保护数据挖掘

## 1. 隐私保护机器学习

基于安全多方计算、同态加密实现隐私保护机器学习的训练和推理，主要包括隐私保护线性回归、逻辑回归、神经网络和泊松回归。

+ :triangular_flag_on_post: **[DSZ15]ABY-A framework for efficient mixed-protocol secure two-party computation**
  + 混合协议开篇之作，ABY：算术秘密份额（A）、布尔秘密份额（B）和姚氏秘密份额（Y）
  + 发表在NDSS 2015，论文链接见[NDSS 2015](https://www.ndss-symposium.org/ndss2015/ndss-2015-programme/aby-framework-efficient-mixed-protocol-secure-two-party-computation/)
+ :triangular_flag_on_post: **[MZ17]SecureML: A system for scalable privacy-preserving machine learning**
  + 隐私保护机器学习（线性回归、逻辑回归和神经网络）
  + 发表在S&P 2017，论文链接见[eprint](https://eprint.iacr.org/2017/396.pdf)
+ [MR18]ABY3: A mixed protocol framework for machine learning
  + 利用复制秘密共享技术提出了恶意模型下基于混合协议的安全三方计算通用框架ABY3，但仅在半诚实模型下实现了线性回归、逻辑回归和神经网络的安全计算
  + 论文发表在CCS 2018，论文链接见[ACM CCS](https://dl.acm.org/doi/abs/10.1145/3243734.3243760)，[eprint](https://eprint.iacr.org/2018/403)
+ Oblivious neural network predictions via minionn transformations
+ GAZELLE: A Low Latency Framework for Secure Neural Network Inference
+ Trident: Efficient 4PC Framework for Privacy Preserving Machine Learning
+ QUOTIENT: Two-Party Secure Neural Network Training and Prediction
+ New Primitives for Actively-Secure MPC over Rings with Applications to Private Machine Learning
+ XONN: XNOR-based Oblivious Deep Neural Network Inference
+ [WGC+19]SecureNN-3-Party Secure Computation for Neural Network Training
  + 安全三方隐私保护神经网络训练，发表在PoPETS2019
  + 论文链接见[PoPETS 2019](https://petsymposium.org/popets/2019/popets-2019-0035.php)
+ 2020：[Effectiveness of MPC-friendly Softmax Replacement](https://arxiv.org/abs/2011.11202)
+ [RRK+20]CrypTFlow2: Practical 2-Party Secure Inference
  + 安全两方神经网络推理
  + 发表在CCS 2020，论文链接见[eprint](https://eprint.iacr.org/2020/1002)
+ [Privacy-Preserving Decision Trees Training and Prediction](https://dl.acm.org/doi/pdf/10.1145/3517197)
+ [PSSY21]ABY2.0: Improved Mixed-Protocol Secure Two-Party Computation
  + 在ABY框架的基础上进一步减少了秘密份额转换的开销，降低了协议的通信开销
  + 论文发表在USENIX 2021，论文链接见[USENIX](https://www.usenix.org/conference/usenixsecurity21/presentation/patra)，[eprint](https://eprint.iacr.org/2020/1225)
+ [BDST]MOTION - A Framework for Mixed-Protocol Multi-Party Computation
  + ABY的多方版本，文章中详细论述了ABY系列协议
  + 发表在TOPS 2022，论文链接见[eprint](https://eprint.iacr.org/2020/1137)，[ACM](https://dl.acm.org/doi/abs/10.1145/3490390)
+ [CGOS22]SIMC: ML Inference Secure Against Malicious Clients at Semi-Honest Cost
  + 恶意模型下安全神经网络推理
  + 发表在USENIX 2022，论文链接见[USENIX 2022](https://www.usenix.org/conference/usenixsecurity22/presentation/chandran)
+ [ZWLL22]SecureBiNN-3-Party Secure Computation for Binarized Neural Network Inference
  + 安全三方二值神经网络推理
  + 发表在ESORICS 2022，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-031-17143-7_14)
+ [APR+22]Communication Efficient Secure Logistic Regression
  + 基于函数秘密共享和秘密共享结合的安全两方逻辑回归
  + 论文链接见[eprint](https://eprint.iacr.org/2022/866)

## 2. 联合统计分析
+ [KLRS22]Secure Poisson Regression
  + 安全两方泊松回归
  + 发表在USENIX 2022，论文链接见[USENIX 2022](https://www.usenix.org/conference/usenixsecurity22/presentation/kelkar)，[eprint](https://eprint.iacr.org/2021/208)

