# 预处理模型下的安全多方计算协议
（Secure Multi-Party Computation in the Pre-processing model）

在预处理模型（Preprocessing Model）中，协议被分为预处理阶段（Preprocessing Phase）和在线阶段（Online Phase）。在预处理阶段（也称为设置阶段（Setup Phase）、离线阶段（Offline Phase）），各个参与方共同运行一个与数据独立安全协议来产生相关随机性（correlated randomness），这些相关值可以辅助完成计算任务；在线阶段则利用预处理阶段提供的相关值，基于参与方的数据来计算功能函数。这种基于预处理模型的两阶段协议的优点在于将在线阶段的大量计算移到预处理阶段，从而使得在线阶段的效率较高，由于在预处理阶段不需要知道参与者的输入，因此预处理阶段可以在目标计算任务之前的任何时间执行。

## 1. 相关材料

+ [Explanation of correlated randomness](https://crypto.stackexchange.com/questions/58259/explanation-of-correlated-randomness-for-garbled-circuits)
  + 从high-level的角度来介绍相关随机性
+ [The TinyOT Protocol Part 1 - Prof. Claudio Orlandi](https://www.youtube.com/watch?v=jJ5d-EUq-DY)
  + 关于TinyOT的介绍，里面对于基于相关随机性范式有详细地介绍
+ [MPC in the Preprocessing Model](https://simons.berkeley.edu/sites/default/files/docs/15669/simons-spdz.pdf)
  + Homomorphic Encryption in the SPDZ Protocol for MPC
+ [Peter Scholl](https://dblp.org/pid/00/10576.html)
  + 做安全多方计算的一个大佬，对于预处理模型下的安全多方计算很有研究
  + Low-Communication Multiparty Triple Generation for SPDZ from Ring-LPN
  + When It's All Just Too Much: Outsourcing MPC-Preprocessing
  + SPDZ中的P



## 2. 相关论文

### 2.1 理论研究

+ [Beaver91]Efficient Multiparty Protocols Using Circuit Randomization
  + Donald Beaver 
  + [Springer](https://link.springer.com/chapter/10.1007/3-540-46766-1_34)
  + 预处理模型最早源于Beaver的工作，Beaver针对BGW协议的复杂乘法运算，提出了乘法三元组的概念（后也称Beaver三元组），用一轮交互便可完成一次乘法运算，大大提高了乘法运算的效率。
+ [DGKN08]Asynchronous Multiparty Computation: Theory and Implementation
  + Ivan Damgård, Martin Geisler, Mikkel Krøigaard, and Jesper Buus Nielsen
  + [eprint](https://eprint.iacr.org/2008/415)
+ [DO10]Multiparty Computation for Dishonest Majority: from Passive to Active Security at Low Cost
  + Ivan Damgård and Claudio Orlandi
  + [eprint](https://eprint.iacr.org/2010/318)
  + Damgård和Orlandi在2010年提出了一个不诚实大多数的恶意安全多方计算协议，并在协议中采用了预处理模型。在该协议中，采用的乘法三元组是带承诺的Beaver三元组，例如$[a],[b],[c]$和$\textsf{Comm}(a),\textsf{Comm}(b),\textsf{Comm}(c)$，并利用Shamir秘密共享来生成乘法三元组，同时用零知识证明来验证三元组的正确性。
+ [BDOZ11]Semi-Homomorphic Encryption and Multiparty Computation
  + Rikke Bendlin, Ivan Damgård, Claudio Orlandi, and Sarah Zakarias
  + [eprint](https://eprint.iacr.org/2010/514)
  + Bendlin等人在2011年提出的BDOZ协议利用部分同态加密（Somewhat Homomorphic Encryption，SHE）生成乘法三元组，而且不再基于离散对数问题的困难性（hardness of discrete logarithms），仅仅依赖于Paillier encryption的安全性。不过，BDOZ协议依然使用零知识证明协议来验证乘法三元组的正确性。
+ [NNO+12]A New Approach to Practical Active-Secure Two-Party Computation
  + Jesper Buus Nielsen, Peter Sebastian Nordholt, Claudio Orlandi, and Sai Sheshank Burra
  + [eprint](https://eprint.iacr.org/2011/091)
  + Nielsen等人在2012年提出了一个基于OT协议的恶意安全两方计算协议，称为TinyOT。
+ [SPDZ12]Multiparty Computation from Somewhat Homomorphic Encryption
  + I. Damgard, V. Pastro, N. P. Smart, and S. Zakarias
  + [eprint](https://eprint.iacr.org/2011/535)
  + SPDZ-1协议：Damgård等人在2012年基于BDOZ协议的框架，优化了BDOZ协议的可认证秘密共享方案，同时使用部分同态加密（Somewhat
	Homomorphic Encryption，SHE）来生成乘法三元组，进一步降低了在线阶段的计算复杂度和通信复杂度，使其与参与者数量呈线性关系。
+ [DKL+13]Practical Covertly Secure MPC for Dishonest Majority – or: Breaking the SPDZ Limits
  + Ivan Damgard, Marcel Keller, Enrique Larraia, Valerio Pastro, Peter Scholl, and Nigel P. Smart
  + [eprint](https://eprint.iacr.org/2012/642)
  + SPDZ-2协议：Damgård等人在2013年提出了进一步的优化，使得在线阶段可以重用相关随机性，并将部分验证（称为 Sacrificing 步骤）移到离线阶段，提高了在线阶段的性能。
+ [DZ13]Constant-Overhead Secure Computation of Boolean Circuits using Preprocessing
  + Ivan Damgard and Sarah Zakarias
  + [eprint](https://eprint.iacr.org/2012/512)
  + 在2013年，Damgård和Zakarias提出了计算布尔电路的不诚实大多数恶意安全多方计算协议，称为MiniMAC协议，该协议采用了和BDOZ协议和SPDZ-1协议的在线阶段，但与BDOZ协议和SPDZ-1协议使用消息认证码不同的是，该工作使用基于线性码（Linear Codes）的同态认证（Homomorphic Authentication）方案。
+ [IKM+13]On the Power of Correlated Randomness in Secure Computation
  + Yuval Ishai, Eyal Kushilevitz, Sigurd Meldgaard, Claudio Orlandi & Anat Paskin-Cherniavsky 
  + [Springer](https://link.springer.com/chapter/10.1007/978-3-642-36594-2_34)
  + Ishai等人在2013年研究了相关随机性能在多大程度上帮助构造不诚实大多数的安全多方计算协议。
+ [KSS13]An architecture for practical actively secure MPC with dishonest majority
  + Marcel Keller, Peter Scholl, and Nigel P. Smart
  + [eprint](https://eprint.iacr.org/2013/143)
+ [PUL13]Actively Secure Two-Party Computation: Efficient Beaver Triple Generation
  + Pille Pullonen
  + [website](https://sharemind.cyber.ee/files/papers/sharemind_active_security_pullonen_2013.pdf)
+ [LOS14]Dishonest Majority Multi-Party Computation for Binary Circuits
  + Enrique Larraia, Emmanuela Orsini, and Nigel P. Smart
  + [eprint](https://eprint.iacr.org/2014/101)
  + TinyOT的多方版本
+ [DNPR15]On the Communication required for Unconditionally Secure Multiplication
  + Ivan Damgård, Jesper Buus Nielsen, Antigoni Polychroniadou, and Michael Raskin
  + [eprint](https://eprint.iacr.org/2015/1097)
  + 帮助不大
+ [DSZ15]ABY - A framework for efficient mixedprotocol secure two-party computation
  + Daniel Demmler, Thomas Schneider, Michael Zohner
+ [FKOS15]A Unified Approach to MPC with Preprocessing using OT
  + Tore Kasper Frederiksen, Marcel Keller, Emmanuela Orsini, and Peter Scholl
  + [eprint](https://eprint.iacr.org/2015/901)
  + Frederiksen等人在2015年基于相关OT扩展（Correlated OT Extension）协议，实现了预处理模型下的带MACs的MPC协议（MPC with MACs），该工作关注于有限域$\mathbb{F}_{2^k}$。
+ [HIJ+15]Secure Multiparty Computation with General Interaction Patterns
  + Shai Halevi, Yuval Ishai, Abhishek Jain, Eyal Kushilevitz, and Tal Rabin
  + [Reusable Correlated Randomness in the CRS Model](https://1library.net/article/reusable-correlated-randomness-in-the-crs-model.zp2rn47y)
  + [eprint](https://eprint.iacr.org/2015/1173)
  + 帮助不大
+ [LPS15]Efficient Constant Round Multi-Party Computation Combining BMR and SPDZ
  + Yehuda Lindell, Benny Pinkas, Nigel P. Smart, and Avishay Yanai
  + [eprint](https://eprint.iacr.org/2015/523)
  + 帮助不大
+ [KOS16]MASCOT: Faster Malicious Arithmetic Secure Computation with Oblivious Transfer
  + Marcel Keller, Emmanuela Orsini, and Peter Scholl
  + [eprint](https://eprint.iacr.org/2016/505)
  + 2016年，Keller等人提出了MASCOT协议来解决有限域上算术电路的安全多方计算任务，其预处理阶段基于相关不经意传输协议（Oblivious
	 Transfer，OT），而不是经典SPDZ协议采用的部分同态加密技术，其性能相比于SPDZ-2协议提升了两个数量级。
+ [BDTZ16]Better Preprocessing for Secure Multiparty Computation
  + Carsten Baum, Ivan Damgård, Tomas Toft, and Rasmus Zakarias
  + [eprint](https://eprint.iacr.org/2016/048)
+ [DNN+17]Gate-scrambling Revisited - or: The TinyTable protocol for 2-Party Secure Computation
  + Ivan Damgård, Jesper Buus Nielsen, Michael Nielsen, and Samuel Ranellucci
  + [eprint](https://eprint.iacr.org/2016/695)
+ [HIJ17]Non-Interactive Multiparty Computation without Correlated Randomness
  + Shai Halevi, Yuval Ishai, Abhishek Jain, Ilan Komargodski, Amit Sahai, and Eylon Yogev
  + [eprint](https://eprint.iacr.org/2017/871)
+ [SSW17]When It’s All Just Too Much: Outsourcing MPC-Preprocessing
  + Peter Scholl, Nigel P. Smart, and Tim Wood
  + [eprint](https://eprint.iacr.org/2017/262)
+ [CDE+18]SPDZ2^k:efficient MPC mod 2^k for dishonest majority
  + Ronald Cramer, Ivan Damgård, Daniel Escudero, Peter Scholl, and Chaoping Xing
  + [eprint](https://eprint.iacr.org/2018/482)
+ [Couteau18]A Note on the Communication Complexity of Multiparty Computation in the Correlated Randomness Model
  + Geoffroy Couteau
  + [slide](https://geoffroycouteau.github.io/assets/slides/presentation_corrmpc_ec2019.pdf)
  + [eprint](https://eprint.iacr.org/2018/465)
+ [KPR18]Overdrive: Making SPDZ Great Again
  + Marcel Keller, Valerio Pastro, and Dragos Rotaru
  + [eprint](https://eprint.iacr.org/2017/1230)
+ [BCG+19]Efficient Two-Round OT Extension and Silent Non-Interactive Secure Computation
  + Elette Boyle, Geoffroy Couteau, Niv Gilboa, Yuval Ishai, Lisa Kohl, Peter Rindal, and Peter Scholl
  + [slides](https://simons.berkeley.edu/sites/default/files/docs/15517/mpcwithsilentpreprocessing.pdf)
  + [slides](https://u.cs.biu.ac.il/~lindell/TPMPC2019/Peter_Scholl_TPMPC2019.pdf)
  + [eprint](https://eprint.iacr.org/2019/1159)
+ [BCG+19]Efficient Pseudorandom Correlation Generators: Silent OT Extension and More
  + Elette Boyle, Geoffroy Couteau, Niv Gilboa, Yuval Ishai, Lisa Kohl, and Peter Scholl
  + [eprint](https://eprint.iacr.org/2019/448)
+ [BGI19]Secure computation with preprocessing via function secret sharing
  + Elette Boyle, Niv Gilboa, and Yuval Ishai
  + [eprint](https://eprint.iacr.org/2019/1095)
+ [CRFG19]MonZa: Fast Maliciously Secure Two Party Computation on Z_{2^k}
  + Dario Catalano, Mario Di Raimondo, Dario Fiore, and Irene Giacomelli
  + [eprint](https://eprint.iacr.org/2019/211)
+ [DLN19]Communication Lower Bounds for Statistically Secure MPC, with or without Preprocessing
  + Ivan Damgård, Kasper Green Larsen, and Jesper Buus Nielsen
  + [eprint](https://eprint.iacr.org/2019/220)
+ [BCG+20]Efficient Pseudorandom Correlation Generators from Ring-LPN
  + Elette Boyle, Geoffroy Couteau, Niv Gilboa, Yuval Ishai, Lisa Kohl & Peter Scholl 
  + [Springer](https://link.springer.com/chapter/10.1007/978-3-030-56880-1_14)
+ [Keller20] MP-SPDZ: A Versatile Framework for Multi-Party Computation
  + Marcel Keller
  + [eprint](https://eprint.iacr.org/2020/521)
+ [BGIN21]Sublinear GMW-Style Compiler for MPC with Preprocessing
  + Elette Boyle, Niv Gilboa, Yuval Ishai, and Ariel Nof
  + [eprint](https://eprint.iacr.org/2022/261)
+ [LZZ21]Correlated Randomness Teleportation via Semi-trusted Hardware – Enabling Silent Multi-party computation
  + 浙大隐私计算团队
  + Yibiao Lu, Bingsheng Zhang, Hong-Sheng Zou, Weiran Liu, Lei Zhang, **Kui Ren**
  + Proceedings of the 26th European Symposium on Research in Computer Security(ESORICS 2021)
  + [eprint](https://eprint.iacr.org/2020/1259)
+ [ORS21]On the Bottleneck Complexity of MPC with Correlated Randomness
  + Claudio Orlandi, Divya Ravi, and Peter Scholl
  + [eprint](https://eprint.iacr.org/2021/1594)
+ [BCG+22]Correlated Pseudorandomness from Expand-Accumulate Codes
  + Elette Boyle , IDC Herzliya and NTT Research Israel; Geoffroy Couteau , CNRS, IRIF, Université de Paris; Niv Gilboa , Ben-Gurion University; Yuval Ishai , Technion
Lisa Kohl , CWI; Nicolas Resch , CWI; Peter Scholl , Aarhus University
  + [eprint](https://iacr.org/cryptodb/data/paper.php?pubkey=32265)
+ [BGIN22]Secure Multiparty Computation with Sublinear Preprocessing
  + Elette Boyle, Niv Gilboa, Yuval Ishai & Ariel Nof 
  + [Springer](https://link.springer.com/chapter/10.1007/978-3-031-06944-4_15)

+ []
  + 
  + [eprint]()
+ []
  + 
  + [eprint]()
+ []
  + 
  + [eprint]()
+ []
  + 
  + [eprint]()
+ []
  + 
  + [eprint]()
+ []
  + 
  + [eprint]()


### 2.2 应用研究

+ [JLP15]Preprocessing-Based Verification of Multiparty Protocols with Honest Majority
  + Roman Jagomägis, Peeter Laud, and Alisa Pankova
  + [eprint](https://eprint.iacr.org/2015/674)
+ [NST16]Constant Round Maliciously Secure 2PC with Function-independent Preprocessing using LEGO
  + Jesper Buus Nielsen, Thomas Schneider, and Roberto Trifiletti
  + [eprint](https://eprint.iacr.org/2016/1069)
+ [MAT18]Constant-Round Client-Aided Secure Comparison Protocol
  + Hiraku Morita, Nuttapong Attrapadung, Tadanori Teruya, Satsuya Ohata, Koji Nuida & Goichiro Hanaoka 
  + [Springer](https://link.springer.com/chapter/10.1007/978-3-319-98989-1_20)
+ [BD19]Optimal-Round Preprocessing-MPC via Polynomial Representation and Distributed Random Matrix
  + Dor Bitan and Shlomi Dolev
  + [eprint](https://eprint.iacr.org/2019/1024)
+ [SXL20]Privacy-Preserving Deep Learning with SPDZ
  + Shreya Sharma, Chaoping Xing, Yang Liu
  + [other](https://www2.isye.gatech.edu/~fferdinando3/cfp/PPAI20/papers/paper_3.pdf)
+ [BAH21]Outsourcing Secure MPC to Untrusted Cloud Environments with Correctness Verification
  + Oscar Bautista; Kemal Akkaya; Soamar Homsi
  + [eprint](https://ieeexplore.ieee.org/document/9524971)
+ [CDN21]High Performance Logistic Regression for Privacy-Preserving Genome Analysis
  + Martine De Cock, Rafael Dowsley, Anderson C. A. Nascimento, Davis Railsback, Jianwei Shen, and Ariel Todoki
  + [eprint](https://eprint.iacr.org/2020/171)
+ [RRKK22]Arithmetic Tuples for MPC
  + Pascal Reisert, University of Stuttgart; Marc Rivinius, University of Stuttgart; Toomas Krips, University of Tartu; Ralf Kuesters, University of Stuttgart
  + [eprint](https://eprint.iacr.org/2022/667)
+ []
  + 
  + [eprint]()
+ []
  + 
  + [eprint]()
+ []
  + 
  + [eprint]()
+ []
  + 
  + [eprint]()
+ []
  + 
  + [eprint]()
+ []
  + 
  + [eprint]()
