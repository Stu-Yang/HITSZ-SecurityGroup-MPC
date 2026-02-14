# Covert Security 隐蔽安全性

## 1. 隐蔽安全介绍

在安全多方计算（Secure Multi-Party Computation, MPC）中，根据敌手的能力，通常将敌手模型划分为以下几类：
+ **被动安全模型（Passive Security）**：在被动安全模型中，腐化参与方也会遵循协议流程执行协议，但敌手能够获取所有腐化参与方的内部状态（包括所有已接收消息的记录），并试图利用这些信息来获取本应保密的信息
+ **主动安全模型（Active Security）**：在恶意安全模型中，腐化参与方会根据敌方的指令任意地偏离协议流程
+ **隐蔽安全模型（CovertSecurity）**：在隐蔽安全模型中，敌手可能会尝试破坏协议执行，但如果尝试攻击，会以一定的概率被检测到（例如，有80%的概率检测到恶意行为，该概率可根据具体应用进行调整）。注意，与恶意安全模型不同，如果敌手的恶意行为未被检测到，则其可能成功作弊（例如，获取诚实方的输入）。

## 2. 隐蔽安全相关论文

> 正如Yehuda Lindell在[[LP11]Secure Two-Party Computation via Cut-and-Choose Oblivious Transfer](https://eprint.iacr.org/2010/284)和[[Lin13]Fast Cut-and-Choose Based Protocols for Malicious and Covert Adversaries](https://eprint.iacr.org/2013/079)指出，现有Cut-and-Choose-based Garbled Circuit (GC) 协议能够实现隐蔽安全，其中攻击者作弊被抓获的威慑概率等于1减去协议的统计误差（[LP11], page 27; [Lin13], page 3）。但Cut-and-Choose-based GC协议主要目标是实现主动安全，因此不在本页面展示，详见[cut-and-choose-based-gc](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/gc-based-mpc#221-%E5%9F%BA%E4%BA%8Ecut-and-choose%E7%9A%84%E6%81%B6%E6%84%8F%E5%AE%89%E5%85%A8%E4%B8%A4%E6%96%B9%E8%AE%A1%E7%AE%97%E5%8D%8F%E8%AE%AE)
>
> 同时，部分Covert multi-party computation的论文（[[AHL05]Covert Two-Party Computation](https://dl.acm.org/doi/abs/10.1145/1060590.1060668), [[CGOS07]Covert Multiparty Computation](http://web.cs.ucla.edu/~rafail/PUBLIC/83.pdf)等）考虑隐写安全计算，因此是计算本身是隐蔽的，而本页面讨论的工作考虑隐蔽的敌手行为，因此这些工作与本页面讨论的隐蔽安全有着本质不同，因此不包括在本页面
> 
> 另外，注意公开可验证隐蔽安全（Publicly Verifiable Covert Security）和可识别中止（Identifiable Abort Security）的区别

+ :triangular_flag_on_post:***[AL07] Security Against Covert Adversaries: Efficient Protocols for Realistic Adversaries***
  + 提出隐蔽安全概念
  + 发表在TCC 2027, JoC 2010，论文链接见[IACR eprint](https://eprint.iacr.org/2007/060)
+ ***[GMS08] Efficient Two Party and Multi Party Computation Against Covert Adversaries***
  + 提出不诚实大多数隐蔽安全两方和多方计算协议，多方计算协议通过修改BMR Garbled Circuits (GC) 协议获得
  + 发表在EuroCrypt 2008，论文链接见[IACR eprint](https://iacr.org/archive/eurocrypt2008/49650287/49650287.pdf), [Slides](https://www.iacr.org/conferences/eurocrypt2008/sessions/paymanMohosell_20080416.pdf)
+ ***[DGN10] From Passive to Covert Security at Low Cost***
  + 提出隐蔽安全编译器，可将基于秘密共享的诚实大多数设置下半诚实安全协议编译成隐蔽安全协议
  + 发表在TCC 2010，论文链接见[IACR eprint](https://eprint.iacr.org/2009/592)
+ ***[LOP11] IPS Compiler: Optimizations, Variants and Concrete Efficiency***
  + 提出了一种类似于IPS (Ishai, Prabhakaran and Saha, CRYPTO 2008)的编译器，可将不诚实大多数下半诚实安全协议编译成隐蔽安全协议
  + 发表在CRYPTO 2011，论文链接见[IACR eprint](https://eprint.iacr.org/2011/435)
+ :triangular_flag_on_post:***[AO12] Calling out Cheaters: Covert Security with Public Verifiability***
  + 提出公开可验证隐蔽安全，其中提出sign-OT协议
  + 发表在AsiaCrypt 2012，论文链接见[IACR eprint](https://eprint.iacr.org/2012/708.pdf)
+ ***[MR13]Garbled Circuits Checking Garbled Circuits: More Efficient and Secure Two-Party Computation***
  + 结合Dual Execution和Cut-and-Choose实现了保证输出正确性的Covert 2PC协议
  + 发表在Crypto 2013，论文链接见[IACR eprint](https://eprint.iacr.org/2013/051)
+ ***[NME13]Efficient Multiparty Computation for Arithmetic Circuits against a Covert Majority***
  + 设计了不诚实大多数情况下隐蔽安全算术电路协议，之前的协议大多考虑布尔电路
  + 发表在AfricaCrypt 2013，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-642-38553-7_15)
+ ***[DKL+13]Practical Covertly Secure MPC for Dishonest Majority – or: Breaking the SPDZ Limits***
  + 提出SPDZ范式的不诚实大多数下隐蔽安全多方计算协议，其未实现公开可验证
  + 发表在ESORICS 2013，论文链接见[IACR eprint](https://eprint.iacr.org/2012/642)
+ ***[KM15]Public Verifiability in the Covert Model (Almost) for Free***
  + 提出公开可验证隐蔽安全优化协议，其中提出sign-OT extension协议
  + 发表在AsiaCrypt 2015，论文链接见[IACR eprint](https://eprint.iacr.org/2015/1067)
+ ***[KPR18]Overdrive: Making SPDZ Great Again***
  + 提出SPDZ范式的不诚实大多数下隐蔽安全多方计算协议（其未实现公开可验证），是DKL+13的优化，在[MP-SPDZ library](https://github.com/data61/MP-SPDZ) 中有实现
  + 发表在EuroCrypt 2018，论文链接见[IACR eprint](https://eprint.iacr.org/2017/1230), [code](https://github.com/data61/MP-SPDZ#protocols)
+ :triangular_flag_on_post:***[HKK+19]Covert Security with Public Verifiability: Faster, Leaner, and Simpler***
  + 提出标准OT下公开可验证隐蔽安全协议
  + 发表在EuroCrypt 2019，论文链接见[IACR eprint](https://eprint.iacr.org/2018/1108)，[code](https://github.com/emp-toolkit/emp-pvc)
+ ***[ZDH19]Efficient Publicly Verifiable 2PC over a Blockchain with Applications to Financially-Secure Computations***
  + 公开可验证隐蔽安全两方计算在区块链上的应用
  + 发表在CCS 2019，论文链接见[Yan Huang Homepage](https://homes.luddy.indiana.edu/yh33/mypub/pvc.pdf)
+ ***[DOS20] Black-Box Transformations from Passive to Covert Security with Public Verifiability***
  + 提出一种黑盒构造的编译器，将半诚实安全两方计算协议编译成公开可验证隐蔽安全协议，之前的编译器没有考虑公开可验证性
  + 发表在CRYPTO 2020，论文链接见[IACR eprint](https://iacr.org/archive/crypto2020/12171355/12171355.pdf), [Video](https://www.youtube.com/watch?v=plB0ZYrjagM)
+ ***[Gol20]Practical Covert Multiparty Computation with Interactive Public Verifiability***
  + 结合PVC和dual execution去实现输出正确性
  + Reichman University (Israel) 学位论文，论文链接见[ProQuest](https://www.proquest.com/docview/2904457864?pq-origsite=gscholar&fromopenview=true&sourcetype=Dissertations%20&%20Theses)，[Github Upload](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/blob/main/mpc/mpc-research/covert-mpc/%5BGol20%5DThesis-Practical%20Covert%20Multiparty%20Computation%20With%20Interactive%20Public%20Verifiability.pdf)
+ ***[FHKS21]Generic Compiler for Publicly Verifiable Covert Multi-Party Computation***
  + 提出公开可验证安全多方计算协议编译器，DOS20主要关注两方计算
  + 发表在EuroCrypt 2021，论文链接见[IACR eprint](https://eprint.iacr.org/2021/251)
+ ***[ABGK21]MPC-Friendly Commitments for Publicly Verifiable Covert Security***
  + 提出面向公开可验证隐蔽安全计算协议的承诺方案
  + 发表在CCS 2021，论文链接见[IACR eprint](https://eprint.iacr.org/2022/102)
+ ***[SSS22]Multiparty Computation with Covert Security and Public Verifiability***
  + 提出公开可验证隐蔽安全多方计算协议编译器
  + 发表在ITC 2022，论文链接见[IACR eprint](https://eprint.iacr.org/2021/366)
+ ***[LWY22]Making Private Function Evaluation Safer, Faster, and Simpler***
  + 提出公开可验证隐蔽安全的私有函数评估协议
  + 发表在PKC 2022，论文链接见[IACR eprint](https://eprint.iacr.org/2021/1682)
+ ***[FHKS22]Financially Backed Covert Security***
  + 提出以经济支持为保障的隐蔽安全（Financially Backed Covert，FBC）的概念，确保如果发现作弊行为，对手将受到经济惩罚
  + 发表在PKC 2022，论文链接见[IACR eprint](https://eprint.iacr.org/2021/1652)
+ ***[ADEL22]Efficient Compiler to Covert Security with Public Verifiability for Honest Majority MPC***
  + 提出诚实大多数下公开可验证隐蔽安全多方计算协议编译器，通过提出一个公开可验证秘密共享方案，避免使用FHKS21和SSS22中计算开销大的time-lock puzzles（FHKS21和SSS22都是利用通用主动安全MPC协议来实例化time-lock puzzles）
  + 发表在ACNS 2022，论文链接见[IACR eprint](https://eprint.iacr.org/2022/454), [Msc Thesis with implementation by V.A. Dunning](http://essay.utwente.nl/87995/)
+ ***[FHKS23]Putting the Online Phase on a Diet: Covert Security from Short MACs***
  + 提出基于IT-MAC的Covert MPC协议
  + 发表在CT-RSA 2023，论文链接见[IACR eprint](https://eprint.iacr.org/2023/052)
+ :triangular_flag_on_post:***[LLW+23]Robust Publicly Verifiable Covert Security: Limited Information Leakage and Guaranteed Correctness with Low Overhead***
  + 提出鲁棒公开可验证隐蔽安全
  + 发表在AsiaCrypt 2015，论文链接见[IACR eprint](https://eprint.iacr.org/2023/1392)
+ ***[NH24]Covert Adaptive Adversary Model: A New Adversary Model for Multiparty Computation***
  + 提出自适应敌手（Adaptive Adversaries）设置下隐蔽安全多方计算协议
  + 论文链接见[IACR eprint-1](https://eprint.iacr.org/2024/729), [IACR eprint-2](https://eprint.iacr.org/2024/735)
+ ***[LSYL25]Zero-Knowledge Protocols with PVC Security: Striking the Balance Between Security and Efficiency***
  + 提出公开可验证隐蔽安全的零知识证明协议
  + 发表在ICICS 2025，论文链接见[IACR 2025](https://eprint.iacr.org/2025/2146)
+ ***[BKV] The Complexity of Memory Checking with Covert Security***
   + Memory checker 是一种算法工具，用于验证维护在远程、不可靠、计算能力有限的服务器上的数据库的完整性，该工作将隐蔽安全的概念应用于Memory Checking
   + 发表在EUROCRYPT 2025，论文链接在[IACR eprint 2025](https://eprint.iacr.org/2025/358)
+ ***[DLH+26]ECHO: Efficient Covertly-Secure Three-party Computation with Applications to Private Machine Learning***
   + 提出基于MAC和Distributed ZK的PVC安全诚实大多数安全三方计算协议
   + 发表在TIFS，论文链接在[IACR eprint](https://eprint.iacr.org/2026/216)
