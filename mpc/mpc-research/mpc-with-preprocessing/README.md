# 预处理模型下的安全多方计算协议
（Secure Multi-Party Computation in the Pre-processing model）

在预处理模型（Preprocessing Model）中，协议被分为预处理阶段（Preprocessing Phase）和在线阶段（Online Phase）。在预处理阶段（也称为设置阶段（Setup Phase）、离线阶段（Offline Phase）），各个参与方共同运行一个与数据独立安全协议来产生相关随机性（correlated randomness），这些相关值可以辅助完成计算任务；在线阶段则利用预处理阶段提供的相关值，基于参与方的数据来计算功能函数。这种基于预处理模型的两阶段协议的优点在于将在线阶段的大量计算移到预处理阶段，从而使得在线阶段的效率较高，由于在预处理阶段不需要知道参与者的输入，因此预处理阶段可以在目标计算任务之前的任何时间执行。

## 

+[Explanation of correlated randomness](https://crypto.stackexchange.com/questions/58259/explanation-of-correlated-randomness-for-garbled-circuits)
+[The TinyOT Protocol Part 1 - Prof. Claudio Orlandi](https://www.youtube.com/watch?v=jJ5d-EUq-DY)

## 相关论文

+ [BDOZ11]Semi-Homomorphic Encryption and Multiparty Computation
  + Rikke Bendlin, Ivan Damgård, Claudio Orlandi, and Sarah Zakarias
  + [eprint](https://eprint.iacr.org/2010/514)
+ [BGI19]Secure computation with preprocessing via function secret sharing
  + Elette Boyle, Niv Gilboa, and Yuval Ishai
  + [eprint](https://eprint.iacr.org/2019/1095)
+ [CDE+18]SPDZ2^k:efficient MPC mod 2^k for dishonest majority
  + Ronald Cramer, Ivan Damgård, Daniel Escudero, Peter Scholl, and Chaoping Xing
  + [eprint](https://eprint.iacr.org/2018/482)
+ [DKL+13]Practical Covertly Secure MPC for Dishonest Majority – or: Breaking the SPDZ Limits
  + Ivan Damgard, Marcel Keller, Enrique Larraia, Valerio Pastro, Peter Scholl, and Nigel P. Smart
  + [eprint](https://eprint.iacr.org/2012/642)
  + SPDZ-2
+ [DNN+17]Gate-scrambling Revisited - or: The TinyTable protocol for 2-Party Secure Computation
  + Ivan Damgård, Jesper Buus Nielsen, Michael Nielsen, and Samuel Ranellucci
  + [eprint](https://eprint.iacr.org/2016/695)
+ [SPDZ12]Multiparty Computation from Somewhat Homomorphic Encryption
  + I. Damgard, V. Pastro, N. P. Smart, and S. Zakarias
  + [eprint](https://eprint.iacr.org/2011/535)
+ [DZ13]Constant-Overhead Secure Computation of Boolean Circuits using Preprocessing
  + Ivan Damgard and Sarah Zakarias
  + [eprint](https://eprint.iacr.org/2012/512)
+ [IKM+13]On the Power of Correlated Randomness in Secure Computation
  + Yuval Ishai, Eyal Kushilevitz, Sigurd Meldgaard, Claudio Orlandi & Anat Paskin-Cherniavsky 
  + [Springer](https://link.springer.com/chapter/10.1007/978-3-642-36594-2_34)
+ [NNO+12]A New Approach to Practical Active-Secure Two-Party Computation
  + Jesper Buus Nielsen, Peter Sebastian Nordholt, Claudio Orlandi, and Sai Sheshank Burra
  + [eprint](https://eprint.iacr.org/2011/091)
+ [Beaver91]Efficient Multiparty Protocols Using Circuit Randomization
  + Donald Beaver 
  + [Springer](https://link.springer.com/chapter/10.1007/3-540-46766-1_34)
+ [KOS16]MASCOT: Faster Malicious Arithmetic Secure Computation with Oblivious Transfer
  + Marcel Keller, Emmanuela Orsini, and Peter Scholl
  + [eprint](https://eprint.iacr.org/2016/505)
+ [KPR18]Overdrive: Making SPDZ Great Again
  + Marcel Keller, Valerio Pastro, and Dragos Rotaru
  + [eprint](https://eprint.iacr.org/2017/1230)
+ [CRFG19]MonZa: Fast Maliciously Secure Two Party Computation on Z_{2^k}
  + Dario Catalano, Mario Di Raimondo, Dario Fiore, and Irene Giacomelli
  + [eprint](https://eprint.iacr.org/2019/211)
+ [BGIN21]Sublinear GMW-Style Compiler for MPC with Preprocessing
  + Elette Boyle, Niv Gilboa, Yuval Ishai, and Ariel Nof
  + [eprint](https://eprint.iacr.org/2022/261)
+ [BCG+19]Efficient Two-Round OT Extension and Silent Non-Interactive Secure Computation
  + Elette Boyle, Geoffroy Couteau, Niv Gilboa, Yuval Ishai, Lisa Kohl, Peter Rindal, and Peter Scholl
  + [eprint](https://eprint.iacr.org/2019/1159)
+ [BCG+19]Efficient Pseudorandom Correlation Generators: Silent OT Extension and More
  + Elette Boyle, Geoffroy Couteau, Niv Gilboa, Yuval Ishai, Lisa Kohl, and Peter Scholl
  + [eprint](https://eprint.iacr.org/2019/448)
+ [BCG+20]Efficient Pseudorandom Correlation Generators from Ring-LPN
  + Elette Boyle, Geoffroy Couteau, Niv Gilboa, Yuval Ishai, Lisa Kohl & Peter Scholl 
  + [Springer](https://link.springer.com/chapter/10.1007/978-3-030-56880-1_14)
+ [BGIN22]Secure Multiparty Computation with Sublinear Preprocessing
  + Elette Boyle, Niv Gilboa, Yuval Ishai & Ariel Nof 
  + [Springer](https://link.springer.com/chapter/10.1007/978-3-031-06944-4_15)
+ [BDTZ16]Better Preprocessing for Secure Multiparty Computation
  + Carsten Baum, Ivan Damgård, Tomas Toft, and Rasmus Zakarias
  + [eprint](https://eprint.iacr.org/2016/048)
+ [ORS21]On the Bottleneck Complexity of MPC with Correlated Randomness
  + Claudio Orlandi, Divya Ravi, and Peter Scholl
  + [eprint](https://eprint.iacr.org/2021/1594)
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






























