## 基于混淆电路的安全多方计算协议

混淆电路（Garbled Circuits）是一种用于安全多方计算（Secure Multi-Party Computation, MPC）中的加密技术，由Andrew Yao在1986年提出。其基本思想是通过对电路的各个逻辑门进行加密，使得参与方能够在不知道输入和中间计算结果的情况下执行计算。混淆电路技术的发展包括优化电路大小和效率、减少通信开销和提高安全性等方面。

### 1.1 混淆电路学习路线
+ 混淆电路基础协议学习
  + 参考[Mike Rosulek](https://web.engr.oregonstate.edu/~rosulekm/)2PC Course，[video-gc](https://www.bilibili.com/video/BV1e64y1C7Te/?spm_id_from=333.999.0.0), [slides-textbook Yao's protocol](https://web.engr.oregonstate.edu/~rosulekm/cryptabit/1-overview.pdf)
  + 相关书籍参考[book-Pragmatic MPC](https://securecomputation.org/)-3.1 Yao’s Garbled Circuits Protocol
+ 混淆电路优化协议学习
  + 参考[Mike Rosulek](https://web.engr.oregonstate.edu/~rosulekm/)的2PC Course，[video-gc optimation](https://www.bilibili.com/video/BV1hK4y197gW/?spm_id_from=333.999.0.0), [slides-Optimizations to garbled circuits (point-permute, free-XOR, half-gates, arithmetic garbling)](https://web.engr.oregonstate.edu/~rosulekm/cryptabit/2-gc.pdf)
  + 相关书籍参考[book-Pragmatic MPC](https://securecomputation.org/)-4.1 Less Expensive Garbling
  + 针对一些关键优化进行，通过阅读下面的论文来学习其具体协议
+ 恶意混淆电路协议学习
  + 参考[Mike Rosulek](https://web.engr.oregonstate.edu/~rosulekm/)的2PC Course，[slides-Protecting Yao's protocol from malicious attacks](https://web.engr.oregonstate.edu/~rosulekm/cryptabit/4-malicious.pdf)
  + 相关书籍参考[book-Pragmatic MPC](https://securecomputation.org/)-6.1-6.4 Cut-and-Choose
+ 实用混淆电路协议学习
  + 针对一些混淆电路设计和实现，通过阅读下面的论文进行学习
  + [Mike Rosulek](https://web.engr.oregonstate.edu/~rosulekm/)整理了一系列论文，见[An Annotated Bibliography of Practical Secure Computation](https://web.engr.oregonstate.edu/~rosulekm/scbib/index.php)


### 1.2 混淆电路相关论文

+ ***[Yao86]How to generate and exchange secrets***
  + 混淆电路的开山之作（建议瞻仰，不建议阅读，因为没有阐述现行混淆电路协议的主要框架）
  + 发表在FOCS 1986，论文链接见[IEEE](https://ieeexplore.ieee.org/abstract/document/4568207)，[github](https://mit6875.github.io/FA23HANDOUTS/yao-garbled-circuits.pdf)
+ ***[MNPS04]Fairplay—A Secure Two-Party Computation System***
  + 第一个安全两方计算系统实现，基于混淆电路技术
  + 发表在USENIX 2004，论文链接见[usenix](https://www.usenix.org/conference/13th-usenix-security-symposium/fairplay%E2%80%94-secure-two-party-computation-system)
+ :triangular_flag_on_post: ***[MF06] Efficiency Tradeoffs for Malicious Two-Party Computation***
  + 第一个提出Dual Execution的概念，并提出基于Dual Execution的恶意安全两方计算协议，该协议存在one-bit leakage
  + 发表在PKC 2006，论文链接见[PKC 2006](https://www.iacr.org/archive/pkc2006/39580468/39580468.pdf), [Springer](https://link.springer.com/chapter/10.1007/11745853_30)
+ :triangular_flag_on_post: ***[LP07]An efficient protocol for secure two-party computation in the presence of malicious adversaries***
  + 首次定义和证明cut-and-choose技术，Pinkas[Pin03](https://link.springer.com/content/pdf/10.1007/3-540-39200-9_6.pdf)和 Malkhi 等人[MNPS04](https://www.usenix.org/conference/13th-usenix-security-symposium/fairplay%E2%80%94-secure-two-party-computation-system)之前曾采用过该技术，但后来证明这些方法存在缺陷[KS06](https://www.win.tue.nl/~berry/papers/wic06.pdf), [MF06](https://link.springer.com/chapter/10.1007/11745853_30)。
  + 发表在EUROCRYPT 2007，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-540-72540-4_4)，[ePrint](https://eprint.iacr.org/2008/049)
+ ***Efficient Two Party and Multi Party Computation Against Covert Adversaries***
  + 针对Covert敌手提出了基于Cut-and-Choose技术的安全两方和多方计算技术
  + 发表在EUROCRYPT 2008，论文链接见[ICAR](https://iacr.org/archive/eurocrypt2008/49650287/49650287.pdf)，[Slides](https://www.iacr.org/conferences/eurocrypt2008/sessions/paymanMohosell_20080416.pdf)
+ ***[NO09]LEGO for Two Party Secure Computation***
  + 提出了基于门级Cut-and-Choose的安全两方计算协议
  + 发表在TCC 09，论文链接见[ePrint](https://eprint.iacr.org/2008/427)
+ ***[HEKM11]Faster Secure Two-Party Computation Using Garbled Circuits***
  + 优化了基于混淆电路的半诚实安全两方系统FairPlay的实现，并面向Hamming distance、Smith-Waterman genome alignment, and AES等任务设计了隐私保护计算协议
  + 发表在[USENIX 2011]([https://www.usenix.org/legacy/events/sec11/tech/full_papers/Huang.pdf](https://www.usenix.org/conference/usenix-security-11/faster-secure-two-party-computation-using-garbled-circuits))，论文链接见[usenix](https://www.usenix.org/legacy/events/sec11/tech/full_papers/Huang.pdf), [video](https://www.usenix.org/conference/usenix-security-11/faster-secure-two-party-computation-using-garbled-circuits), [slides](https://www.usenix.org/legacy/events/sec11/tech/slides/huang.pdf)，[source code](https://mightbeevil.org/)
+ ***[SS11] Two-Output Secure Computation with Malicious Adversaries***
  + 提出了基于Cut-and-Choose优化的安全两方计算，打开并检查 60% 的电路（而不是 50%），则误差变为 2−0.32s（s为Cut-and-Choose所需生成的电路，称为复制因子
  + 论文发表在EUROCRYPTO 2011，论文链接见[ePrint](https://eprint.iacr.org/2011/533)
+ ***[LP11]Secure Two-Party Computation via Cut-and-Choose Oblivious Transfer***
  + 提出了基于Cut-and-Choose优化的安全两方计算，对于复制因子s，敌手成功作弊的概率为2^−0.311s
  + 论文发表在TCC 2011，论文链接见[ePrint](https://eprint.iacr.org/2010/284.pdf)
+ :triangular_flag_on_post: ***[BHR12]Foundations of garbled circuits***
  + 系统介绍了混淆电路，阐述了现行混淆电路协议的主要框架
  + 论文发表在[CCS 2012](https://dl.acm.org/doi/10.1145/2382196.2382279)，论文链接见[CCS](https://dl.acm.org/doi/10.1145/2382196.2382279), [IACR-ePrint](https://eprint.iacr.org/2012/265)
+ :triangular_flag_on_post: ***[HKE12]Quid-Pro-Quo-tocols: Strengthening Semi-Honest Protocols with Dual Execution***
  + Quid-Pro-Quo-tocols意为等价交换，该论文是针对基于Dual Execution的恶意安全两方计算协议的优化
  + 论文发表在[SP 2012](https://ieeexplore.ieee.org/document/6234418)，论文链接见[IEEE SP 2012](https://ieeexplore.ieee.org/document/6234418)，[Huang](https://homes.luddy.indiana.edu/yh33/mypub/mal-sec-two-party-comp.pdf)
+ ***[HKE13]Efficient Secure Two-Party Computation Using Symmetric Cut-and-Choose***
  + 研究了对称Cut-and-Choose技术，即双方都执行Cut-and-Choose，从而能将混淆电路副本数量减小3倍
  + 论文发表在CRYPTO 2013，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-642-40084-1_2)，[ePrint](https://eprint.iacr.org/2013/081)
+ ***[Lin13]Fast Cut-and-Choose Based Protocols for Malicious and Covert Adversaries***
  + 提出了cheating-punishment机制，面向恶意和隐蔽敌手设计了高效的Cut-and-Choose协议，可以实现利用κ个混淆电路实现2^-κ的安全性
  + 论文发表在CRYPTO 2013，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-642-40084-1_1)，[ePrint](https://eprint.iacr.org/2013/079)
+ ***[FJN+13]MiniLEGO: Efficient Secure Two-Party Computation From General Assumptions*** 
  + 门级Cut-and-Choose技术LEGO的优化
  + 发表在EUROCRYPT 2013，论文链接见[ePrint](https://eprint.iacr.org/2013/155)
+ ***[HKK+14]Amortizing Garbled Circuits***
  + 提出了基于Cut-and-Choose的多次执行(multiple execution)的安全两方计算协议，之前[HKE13]和[Lin13]都只面向单次执行(single execution)，该协议依赖于cheating-punishment机制
  + 论文发表在CRYPTO 2014，论文链接见[ePrint](https://eprint.iacr.org/2015/081.pdf)
+ ***[LR14]Cut-and-Choose Yao-Based Secure Computation in the Online/Offline and Batch Settings***
  + 提出了基于Cut-and-Choose的多次执行(multiple execution)的安全两方计算协议，和HKK+14不同的是，HKK+14总是让评估者挑选一半的电路进行检查，但改论文表明改变检查电路的数量可以带来额外的性能提升。
  + 论文发表在CRYPTO 2014，论文链接见[springer](https://link.springer.com/chapter/10.1007/978-3-662-44381-1_27)，[ePrint](https://eprint.iacr.org/2014/667)
+ ***[ZHKS16]The Cut-and-Choose Game and Its Application to Cryptographic Protocols***
  + 分析了Cut-and-Choose的三种情况：SingleCut、MajorityCut和BatchedCut，通过参数分析和算法求解得到最优情况
  + 论文发表在USENIX 2016，论文链接见[usenix](https://www.usenix.org/conference/usenixsecurity16/technical-sessions/presentation/zhu)，[slides](https://www.usenix.org/sites/default/files/conference/protected-files/security16_slides_zhu.pdf)
+ ***[ZH17]JIMU: Faster LEGO-based Secure Computation using Additive Homomorphic Hashes***
  + 基于优化LEGO-style cut-and-choose的安全两方计算协议，是LEGO的优化（避免使用homomorphic commitments）
  + 论文发表在ASIACRYPT 2017，论文链接见[ePrint](https://eprint.iacr.org/2017/226)
+ ******
  + 123
  + 论文发表在，论文链接见[]()
+ ******
  + 123
  + 论文发表在，论文链接见[]()
+ ******
  + 123
  + 论文发表在，论文链接见[]()
+ ******
  + 123
  + 论文发表在，论文链接见[]()













