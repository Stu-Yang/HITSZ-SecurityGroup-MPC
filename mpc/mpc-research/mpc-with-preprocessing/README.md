# 预处理模型下的安全多方计算协议
（Secure Multi-Party Computation in the Pre-processing model）

在预处理模型（Preprocessing Model）中，协议被分为预处理阶段（Preprocessing Phase）和在线阶段（Online Phase）。在预处理阶段（也称为设置阶段（Setup Phase）、离线阶段（Offline Phase）），各个参与方共同运行一个与数据独立安全协议来产生相关随机性（correlated randomness），这些相关值可以辅助完成计算任务；在线阶段则利用预处理阶段提供的相关值，基于参与方的数据来计算功能函数。这种基于预处理模型的两阶段协议的优点在于将在线阶段的大量计算移到预处理阶段，从而使得在线阶段的效率较高，由于在预处理阶段不需要知道参与者的输入，因此预处理阶段可以在目标计算任务之前的任何时间执行。

## 1. 相关材料

+ Geoffroy Couteau在ITC 2023关于相关随机性的报告
  + [Correlated Pseudorandomness](https://geoffroycouteau.github.io/assets/slides/itc_2023.pdf): Achieving faster secure computation through pseudorandom correlation generators
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

![image](https://user-images.githubusercontent.com/66773755/201795749-4418f8f0-760a-467a-a5c7-31b1a8258342.png)

+ ***[Bea91]Efficient Multiparty Protocols Using Circuit Randomization***
  + 预处理模型最早源于Beaver的工作，Beaver针对BGW协议的复杂乘法运算，提出了乘法三元组的概念（后也称Beaver三元组），用一轮交互便可完成一次乘法运算，大大提高了乘法运算的效率。
  + 作者为Donald Beaver，论文链接见[Springer](https://link.springer.com/chapter/10.1007/3-540-46766-1_34)
+ ***[Bea95]Precomputing Oblivious Transfer***
  + 作者为Donald Beaver，论文链接见[springer](https://link.springer.com/chapter/10.1007/3-540-44750-4_8)
+ ***[DN07]Scalable and Unconditionally Secure Multiparty Computation***
  + 作者为Ivan Damgård and Jesper Buus Nielsen，论文链接见[eprint](https://www.iacr.org/archive/crypto2007/46220565/46220565.pdf)
+ ***[DGKN09]Asynchronous Multiparty Computation: Theory and Implementation***
  + 作者为Ivan Damgård, Martin Geisler, Mikkel Krøigaard, and Jesper Buus Nielsen，论文链接见[eprint](https://eprint.iacr.org/2008/415)
  + 2009年，Damgård等人提出了异步网络下的安全多方计算协议，该协议由预处理和输入阶段、计算阶段组成，其中预处理阶段生成乘法三元组，并提出了基于Hyperinvertible Matrices的乘法三元组生成协议和基于Pseudorandom Secret-Sharing的乘法三元组生成协议。
+ ***[DO10]Multiparty Computation for Dishonest Majority: from Passive to Active Security at Low Cost***
  + 作者为Ivan Damgård and Claudio Orlandi，论文链接见[eprint](https://eprint.iacr.org/2010/318)
  + Damgård和Orlandi在2010年提出了一个不诚实大多数的恶意安全多方计算协议，并在协议中采用了预处理模型。在该协议中，采用的乘法三元组是带承诺的Beaver三元组，例如$[a],[b],[c]$和$\textsf{Comm}(a),\textsf{Comm}(b),\textsf{Comm}(c)$，并利用Shamir秘密共享来生成乘法三元组，同时用零知识证明来验证三元组的正确性。
+ ***[BDOZ11]Semi-Homomorphic Encryption and Multiparty Computation***
  + 作者为Rikke Bendlin, Ivan Damgård, Claudio Orlandi, and Sarah Zakarias，论文链接见[eprint](https://eprint.iacr.org/2010/514)
  + Bendlin等人在2011年提出的BDOZ协议利用部分同态加密（Somewhat Homomorphic Encryption，SHE）生成乘法三元组，而且不再基于离散对数问题的困难性（hardness of discrete logarithms），仅仅依赖于Paillier encryption的安全性。不过，BDOZ协议依然使用零知识证明协议来验证乘法三元组的正确性。
+ ***[NNO+12]A New Approach to Practical Active-Secure Two-Party Computation***
  + 作者为Jesper Buus Nielsen, Peter Sebastian Nordholt, Claudio Orlandi, and Sai Sheshank Burra，论文链接见[eprint](https://eprint.iacr.org/2011/091)
  + Nielsen等人在2012年提出了一个基于OT协议的恶意安全两方计算协议，称为TinyOT。
+ :triangular_flag_on_post:***[SPDZ12]Multiparty Computation from Somewhat Homomorphic Encryption***
  + 作者为I. Damgard, V. Pastro, N. P. Smart, and S. Zakarias，论文链接见[eprint](https://eprint.iacr.org/2011/535)
  + SPDZ-1协议：Damgård等人在2012年基于BDOZ协议的框架，优化了BDOZ协议的可认证秘密共享方案，同时使用部分同态加密（Somewhat
	Homomorphic Encryption，SHE）来生成乘法三元组，进一步降低了在线阶段的计算复杂度和通信复杂度，使其与参与者数量呈线性关系。
+ ***[DKL+13]Practical Covertly Secure MPC for Dishonest Majority – or: Breaking the SPDZ Limits***
  + 作者为Ivan Damgard, Marcel Keller, Enrique Larraia, Valerio Pastro, Peter Scholl, and Nigel P. Smart，论文链接见[eprint](https://eprint.iacr.org/2012/642)
  + SPDZ-2协议：Damgård等人在2013年提出了进一步的优化，使得在线阶段可以重用相关随机性，并将部分验证（称为 Sacrificing 步骤）移到离线阶段，提高了在线阶段的性能。
+ ***[DZ13]Constant-Overhead Secure Computation of Boolean Circuits using Preprocessing***
  + 作者为Ivan Damgard and Sarah Zakarias，论文链接见[eprint](https://eprint.iacr.org/2012/512)
  + 在2013年，Damgård和Zakarias提出了计算布尔电路的不诚实大多数恶意安全多方计算协议，称为MiniMAC协议，该协议采用了和BDOZ协议和SPDZ-1协议的在线阶段，但与BDOZ协议和SPDZ-1协议使用消息认证码不同的是，该工作使用基于线性码（Linear Codes）的同态认证（Homomorphic Authentication）方案。
+ ***[IKM+13]On the Power of Correlated Randomness in Secure Computation***
  + 作者为Yuval Ishai, Eyal Kushilevitz, Sigurd Meldgaard, Claudio Orlandi & Anat Paskin-Cherniavsky，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-642-36594-2_34)
  + Ishai等人在2013年研究了相关随机性能在多大程度上帮助构造不诚实大多数的安全多方计算协议，称为OTTT协议。
+ ***[KSS13]An architecture for practical actively secure MPC with dishonest majority***
  + 作者为Marcel Keller, Peter Scholl, and Nigel P. Smart，论文链接见[eprint](https://eprint.iacr.org/2013/143)
+ ***[Pul13]Actively Secure Two-Party Computation: Efficient Beaver Triple Generation***
  + 作者为Pille Pullonen，论文链接见[website](https://sharemind.cyber.ee/files/papers/sharemind_active_security_pullonen_2013.pdf)
  + Pille Pullonen的博士毕业论文
+ ***[LOS14]Dishonest Majority Multi-Party Computation for Binary Circuits***
  + 作者为Enrique Larraia, Emmanuela Orsini, and Nigel P. Smart，论文链接见[eprint](https://eprint.iacr.org/2014/101)
  + TinyOT的多方版本
+ ***[DNPR15]On the Communication required for Unconditionally Secure Multiplication***
  + 作者为Ivan Damgård, Jesper Buus Nielsen, Antigoni Polychroniadou, and Michael Raskin，论文链接见[eprint](https://eprint.iacr.org/2015/1097)
+ ***[DSZ15]ABY - A framework for efficient mixedprotocol secure two-party computation***
  + Daniel Demmler, Thomas Schneider, Michael Zohner
+ ***[FKOS15]A Unified Approach to MPC with Preprocessing using OT***
  + 作者为Tore Kasper Frederiksen, Marcel Keller, Emmanuela Orsini, and Peter Scholl，论文链接见[eprint](https://eprint.iacr.org/2015/901)
  + Frederiksen等人在2015年基于相关OT扩展（Correlated OT Extension）协议，实现了预处理模型下的带MACs的MPC协议（MPC with MACs），该工作关注于有限域$\mathbb{F}_{2^k}$。
+ ***[HIJ+15]Secure Multiparty Computation with General Interaction Patterns***
  + 作者为Shai Halevi, Yuval Ishai, Abhishek Jain, Eyal Kushilevitz, and Tal Rabin，slide链接见[Reusable Correlated Randomness in the CRS Model](https://1library.net/article/reusable-correlated-randomness-in-the-crs-model.zp2rn47y)，论文链接见[eprint](https://eprint.iacr.org/2015/1173)
+ ***[LPS15]Efficient Constant Round Multi-Party Computation Combining BMR and SPDZ***
  + 作者为Yehuda Lindell, Benny Pinkas, Nigel P. Smart, and Avishay Yanai，论文链接见[eprint](https://eprint.iacr.org/2015/523)
+ :triangular_flag_on_post:***[KOS16]MASCOT: Faster Malicious Arithmetic Secure Computation with Oblivious Transfer***
  + 作者为Marcel Keller, Emmanuela Orsini, and Peter Scholl，论文链接见[eprint](https://eprint.iacr.org/2016/505)
  + 2016年，Keller等人提出了MASCOT协议来解决有限域上算术电路的安全多方计算任务，其预处理阶段基于相关不经意传输协议（Oblivious
	 Transfer，OT），而不是经典SPDZ协议采用的部分同态加密技术，其性能相比于SPDZ-2协议提升了两个数量级。
+ ***[BDTZ16]Better Preprocessing for Secure Multiparty Computation***
  + 作者为Carsten Baum, Ivan Damgård, Tomas Toft, and Rasmus Zakarias，论文链接见[eprint](https://eprint.iacr.org/2016/048)
  + 2016年，Baum等人基于SPDZ-1协议和SPDZ-2协议设计了更优的预处理阶段，在预处理阶段，该工作基于线性同态加密（Linearly Homomorphic Encryption，LHE）生成乘法三元组，并重新设计了零知识证明协议来验证其正确性。
+ ***[DNNR17]Gate-scrambling Revisited - or: The TinyTable protocol for 2-Party Secure Computation***
  + 作者为Ivan Damgård, Jesper Buus Nielsen, Michael Nielsen, and Samuel Ranellucci，论文链接见[eprint](https://eprint.iacr.org/2016/695)
  + 2016年，Damgård等人提出了一个新的预处理模型下的恶意安全两方计算协议，称为TinyTable。
+ ***[HIJ17]Non-Interactive Multiparty Computation without Correlated Randomness***
  + 作者为Shai Halevi, Yuval Ishai, Abhishek Jain, Ilan Komargodski, Amit Sahai, and Eylon Yogev，论文链接见[eprint](https://eprint.iacr.org/2017/871)
  + 帮助不大
+ ***[SSW17]When It’s All Just Too Much: Outsourcing MPC-Preprocessing***
  + 作者为Peter Scholl, Nigel P. Smart, and Tim Wood，论文链接见[eprint](https://eprint.iacr.org/2017/262)
  + 2017年，Scholl等人也提出优化预处理阶段，其将预处理阶段外包给其他参与方集合以提高预处理阶段的效率。
+ ***[BCGI18]Compressing Vector OLE***
  + 作者为Elette Boyle, Geoffroy Couteau, Niv Gilboa, and Yuval Ishai，论文链接见[eprint](https://eprint.iacr.org/2019/273)
  + 2018年，Boyle等人从一种新的角度看待相关随机性，与BDOZ协议和SPDZ类协议将相关随机性看成乘法三元组，该工作利用伪随机相关生成器（Pseudorandom Correlation Generator）来获得一对相同的秘密随机串（Secret Random Strings），并构造了VOLE（Vector Oblivious Transfer Evaluation）相关生成器，从而获得更优的预处理模型。
+ ***[CDE+18]SPDZ2^k:efficient MPC mod 2^k for dishonest majority***
  + 作者为Ronald Cramer, Ivan Damgård, Daniel Escudero, Peter Scholl, and Chaoping Xing，论文链接见[eprint](https://eprint.iacr.org/2018/482)
  + 2018年Cramer等人\cite提出了$\mathbb{F}_{2^k}$上的SPDZ类协议，称为$\texr{SPD}\mathbb{Z}_{2^k}$，该协议采用了SPDZ-1协议的预处理模型，但在预处理阶段使用MASCOT协议的OT技术来实现
+ ***[KPR18]Overdrive: Making SPDZ Great Again***
  + 作者为Marcel Keller, Valerio Pastro, and Dragos Rotaru，论文链接见[eprint](https://eprint.iacr.org/2017/1230)
  + 2018年，Keller等人提出SPDZ-Overdrive协议优化了基于SHE的预处理阶段，该协议采用的SHE技术是对加法同态是半同态加密（Semi-Homomorphic
	Encryption），而不是支持深度为1的乘法的SHE。
+ ***[BCG+19]Efficient Pseudorandom Correlation Generators: Silent OT Extension and More***
  + 作者为Elette Boyle, Geoffroy Couteau, Niv Gilboa, Yuval Ishai, Lisa Kohl, and Peter Scholl，论文链接见[eprint](https://eprint.iacr.org/2019/448)
  + Boyle等人在2019年则对PCG进行了系统的研究，并提出了针对MPC相关性的构造协议。
+ ***[BCG+19]Efficient Two-Round OT Extension and Silent Non-Interactive Secure Computation***
  + 作者为Elette Boyle, Geoffroy Couteau, Niv Gilboa, Yuval Ishai, Lisa Kohl, Peter Rindal, and Peter Scholl，Slide链接见[slides](https://simons.berkeley.edu/sites/default/files/docs/15517/mpcwithsilentpreprocessing.pdf)、[slides](https://u.cs.biu.ac.il/~lindell/TPMPC2019/Peter_Scholl_TPMPC2019.pdf)，论文链接见[eprint](https://eprint.iacr.org/2019/1159)
  + 针对[BCGI18]Compressing Vector OLE和[BCG+19]Efficient Pseudorandom Correlation Generators: Silent OT Extension and More的需要较多的通信轮数，并且只能保证半诚实安全问题，该工作解决了这些问题。
+ ***[BGI19]Secure computation with preprocessing via function secret sharing***
  + 作者为Elette Boyle, Niv Gilboa, and Yuval Ishai，论文链接见[eprint](https://eprint.iacr.org/2019/1095)
  + 2019年，Boyle等人进一步地优化了TinyTable协议，该工作基于函数秘密共享（Function Secret Sharing，FSS）实现了预处理模型下的半诚实安全两方计算协议。
+ ***[Cou19]A Note on the Communication Complexity of Multiparty Computation in the Correlated Randomness Model***
  + 作者为Geoffroy Couteau，Slide链接见[slide](https://geoffroycouteau.github.io/assets/slides/presentation_corrmpc_ec2019.pdf)，论文链接见[eprint](https://eprint.iacr.org/2018/465)
  + 2019年，Couteau基于OTTT协议进一步提出了优化
+ ***[CRFG19]MonZa: Fast Maliciously Secure Two Party Computation on Z_{2^k}***
  + 作者为Dario Catalano, Mario Di Raimondo, Dario Fiore, and Irene Giacomelli，论文链接见[eprint](https://eprint.iacr.org/2019/211)，论文链接见
  + 2019年，Catalano等人提出了一个环$\mathbb{Z}_{2^k}$上的快速安全两方计算协议，该协议基于$\text{SPD}\mathbb{Z}_{2^k}$的认证机制，但使用同态加密来生成乘法三元组，其离线阶段和BDOZ协议十分相似。值得注意的是，像BDOZ协议、SPDZ类协议往往都基于域上的运算，而该协议则是基于环上的运算。
+ ***[DLN19]Communication Lower Bounds for Statistically Secure MPC, with or without Preprocessing***
  + 作者为Ivan Damgård, Kasper Green Larsen, and Jesper Buus Nielsen，论文链接见[eprint](https://eprint.iacr.org/2019/220)
  + 2019年，Damgård等人在标准模型下的诚实大多数情况和预处理模型下的不诚实大多数情况证明了无条件安全多方计算的计算复杂性下界。
+ ***[BCG+20]Efficient Pseudorandom Correlation Generators from Ring-LPN***
  + 作者为Elette Boyle, Geoffroy Couteau, Niv Gilboa, Yuval Ishai, Lisa Kohl & Peter Scholl，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-030-56880-1_14)
  + 2020年，Boyle等人基于环上LPN（ring-LPN）假设设计了新的PCG方案，该PCG能够生成OLE相关性（OLE Correlations）、可认证乘法三元组（Authenticated Multiplication Triples）、矩阵乘法相关性（Matrix Product Correlations）等。
+ ***[Keller20] MP-SPDZ: A Versatile Framework for Multi-Party Computation***
  + 作者为Marcel Keller，论文链接见[eprint](https://eprint.iacr.org/2020/521)
  + 2020年，Keller提出了MP-SPDZ框架，其讨论了众多的SPDZ类协议。
+ ***[ON20]Communication-Efficient (Client-Aided) Secure Two-Party Protocols and Its Application***
  + 提出预处理模型下安全两方计算协议，提供了许多通信高效的安全子协议，如多输入乘法等
  + 发表在FC 20，论文链接见[SPringer](https://link.springer.com/chapter/10.1007/978-3-030-51280-4_20)
+ ***[BGIN21]Sublinear GMW-Style Compiler for MPC with Preprocessing***
  + 作者为Elette Boyle, Niv Gilboa, Yuval Ishai, and Ariel Nof，论文链接见[eprint](https://eprint.iacr.org/2022/261)
  + 2021年，Boyle等人提供了一个编译器，该编译器可以将任何满足温和的安全和结构要求的预处理模型下的MPC协议（即大多数半诚实安全的标准协议），编译为恶意安全多方计算协议，其中额外的附加存储及在线通信成本和电路大小呈对数关系，从而平衡了在线阶段的通信成本和相关随机性存储代价。
+ ***[LZZ21]Correlated Randomness Teleportation via Semi-trusted Hardware – Enabling Silent Multi-party computation***
  + 作者为浙大隐私计算团队Yibiao Lu, Bingsheng Zhang, Hong-Sheng Zou, Weiran Liu, Lei Zhang, Kui Ren，论文发表在ESORICS 2021，论文链接见[eprint](https://eprint.iacr.org/2020/1259)
  + 2021年浙江大学隐私计算团队的Lu等人将可信执行环境（Trusted Execution Environment，TEE）引入到相关随机性的生成过程，该工作提出半可信硬件模型（Semi-Trusted Hardwares Model），利用半可信硬件（Semi-Trusted Hardwares）来生成混淆电路这种相关随机性，从而提高协议的效率。
+ ***[ORS21]On the Bottleneck Complexity of MPC with Correlated Randomness***
  + 作者为Claudio Orlandi, Divya Ravi, and Peter Scholl，论文链接见[eprint](https://eprint.iacr.org/2021/1594)
  + 2022年，Orlandi等人研究了预处理模型下的MPC协议的瓶颈复杂度（Bottleneck Complexity），该复杂度由Boyle等人提出，衡量了MPC协议中任何一方最大通信复杂度，以提高各方的负载均衡。
+ ***[BCG+22]Correlated Pseudorandomness from Expand-Accumulate Codes***
  + 作者为Elette Boyle , IDC Herzliya and NTT Research Israel; Geoffroy Couteau , CNRS, IRIF, Université de Paris; Niv Gilboa , Ben-Gurion University; Yuval Ishai , Technion Lisa Kohl , CWI; Nicolas Resch , CWI; Peter Scholl , Aarhus University，论文链接见[eprint](https://iacr.org/cryptodb/data/paper.php?pubkey=32265)
  + 2022年，Boyle等人基于Expand-Accumulate Codes设计了新的PCG构造方案，通信代价更低。
+ ***[BGIN22]Secure Multiparty Computation with Sublinear Preprocessing***
  + 作者为Elette Boyle, Niv Gilboa, Yuval Ishai & Ariel Nof，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-031-06944-4_15)
  + 在2022年，Boyle等人基于工作[BGIN21]Sublinear GMW-Style Compiler for MPC with Preprocessing实现了预处理模型下的MPC协议的亚线性预处理阶段（Sublinear Preprocessing），其离线阶段的通信和电路大小呈亚线性关系。


### 2.2 应用研究

+ ***[JLP15]Preprocessing-Based Verification of Multiparty Protocols with Honest Majority***
  + 作者为Roman Jagomägis, Peeter Laud, and Alisa Pankova，论文链接见[eprint](https://eprint.iacr.org/2015/674)
+ ***[NST16]Constant Round Maliciously Secure 2PC with Function-independent Preprocessing using LEGO***
  + 作者为Jesper Buus Nielsen, Thomas Schneider, and Roberto Trifiletti，论文链接见[eprint](https://eprint.iacr.org/2016/1069)
+ ***[MAT18]Constant-Round Client-Aided Secure Comparison Protocol***
  + 作者为Hiraku Morita, Nuttapong Attrapadung, Tadanori Teruya, Satsuya Ohata, Koji Nuida & Goichiro Hanaoka，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-319-98989-1_20)
+ ***[BD19]Optimal-Round Preprocessing-MPC via Polynomial Representation and Distributed Random Matrix***
  + 作者为Dor Bitan and Shlomi Dolev，论文链接见[eprint](https://eprint.iacr.org/2019/1024)
  + 2022年，Bitan等人针对高阶多项式提出了第一个预处理模型MPC协议，其有最优的轮复杂度。
+ ***[SXL20]Privacy-Preserving Deep Learning with SPDZ***
  + 作者为Shreya Sharma, Chaoping Xing, Yang Liu，论文链接见[other](https://www2.isye.gatech.edu/~fferdinando3/cfp/PPAI20/papers/paper_3.pdf)
+ ***[BAH21]Outsourcing Secure MPC to Untrusted Cloud Environments with Correctness Verification***
  + 作者为Oscar Bautista; Kemal Akkaya; Soamar Homsi，论文链接见[eprint](https://ieeexplore.ieee.org/document/9524971)
+ ***[CDN21]High Performance Logistic Regression for Privacy-Preserving Genome Analysis***
  + 作者为Martine De Cock, Rafael Dowsley, Anderson C. A. Nascimento, Davis Railsback, Jianwei Shen, and Ariel Todoki，论文链接见[eprint](https://eprint.iacr.org/2020/171)
+ ***[RRKK22]Arithmetic Tuples for MPC***
  + 作者为Pascal Reisert, Marc Rivinius,Toomas Krips, Ralf Kuesters，论文链接见[eprint](https://eprint.iacr.org/2022/667)

