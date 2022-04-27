# 安全多方计算(MPC)的基本框架

在这里将介绍安全多方计算(MPC)的基本框架以及学习路线，对应地，也会提供一些学习资源。

## MPC基本框架

MPC的基本概念和构建协议的基础模块是MPC的基石，在此之上有一些通用安全多方计算协议，其可以用于计算任意的功能函数，利用这些通用协议并结合应用便形成了安全多方计算的应用研究。

![](mpc-frame.png)

## MPC学习路线
安全多方计算(MPC)没有一本特别权威又特别易懂的书籍供大家参考，在我们首页的[如何学习安全多方计算？](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC#%E5%A6%82%E4%BD%95%E5%AD%A6%E4%B9%A0%E5%AE%89%E5%85%A8%E5%A4%9A%E6%96%B9%E8%AE%A1%E7%AE%97)中介绍了一些大牛的学习总结、经典课程和书籍给大家，在这里我们详细地介绍一些学习安全多方计算的基本路线，并且提供一些论文、Slides、书籍和课程等。
+ MPC学习路线也可以参考
  + 知乎的[安全多方计算学习路线](https://zhuanlan.zhihu.com/p/351492646)
  + Yehuda Lindell教授的[Resources for Getting Started with MPC](https://u.cs.biu.ac.il/~lindell/MPC-resources.html)
  + Mike Rosulek教授的[An Annotated Bibliography of Practical Secure Computation](https://web.engr.oregonstate.edu/~rosulekm/scbib/index.php?n=Main.GettingStarted)
+ 基本概念
  + MPC基本概念：掌握基本概念，如诚实方、腐坏方和敌手、半诚实模型和恶意模型等
    + Lindell教授的最新MPC综述:[Secure Multiparty Computation (MPC)](https://eprint.iacr.org/2020/300.pdf)：介绍了MPC的基本内容，学习之后可以梳理出基本概念
    + 书籍[[Hazay&Lindell2010]Efficient Secure Two-Party Protocols](https://u.cs.biu.ac.il/~lindell/efficient-protocols.html)的第一章
  + MPC定义及其安全性定义：掌握MPC形式化定义，了解分析安全性的方法和形式化定义
    + 书籍[[Hazay&Lindell2010]Efficient Secure Two-Party Protocols](https://u.cs.biu.ac.il/~lindell/efficient-protocols.html)的第二章：介绍了MPC的定义、安全两方计算(2PC)的半诚实模型和恶意模型下的形式化安全性定义
  + 关于基本概念，许多学者也有介绍，其中比较好的有Lindell的[Tutorial on Secure Multi-Party Computation](https://u.cs.biu.ac.il/~lindell/research-statements/tutorial-secure-computation.ppt)讲解
+ 基础模块
  + 不经意传输(Oblivious Transfer, OT)：掌握基础OT协议(1-out-of-2 OT，C-OT和R-OT等)及其优化(如IKNP03等)
    + 在知乎上有关于不经意传输的介绍[不经意传输(OT)-总结](https://zhuanlan.zhihu.com/p/399361005)
    + 关于OT协议优化，Mike Rosulek教授讲授的[Optimizations to oblivious transfer (Beaver precomputation, OT extension, IKNP protocol and variants)](https://web.engr.oregonstate.edu/~rosulekm/cryptabit/3-ot.pdf)
    + IKNP03的论文[Extending Oblivious Transfers Efficiently](https://link.springer.com/content/pdf/10.1007%2F978-3-540-45146-4_9.pdf)：了解IKNP03的基本思想和技术即可
  + 秘密共享(Secret Sharing, SS)：掌握门限秘密共享和加性秘密共享
    + 关于门限秘密共享，需要掌握Shamir的秘密共享方案[How to share a secret](https://dl.acm.org/doi/pdf/10.1145/359168.359176)及其拉格朗日插值法
    + 关于加性秘密共享，掌握其基本原理即可，可参考一些博客[加法秘密共享(Additive Secret Sharing)](https://blog.csdn.net/qq_33154865/article/details/106271611)
  + 混淆电路(Garbled Circuits, GC)：掌握混淆电路的基本思想及其优化
    + 这部分结合混淆电路协议进行介绍，详见下面的混淆电路协议[Yao86]
  + 剪切-选择技术(Cut-and-Choose)
  + 零知识证明(Zero Knowledge Proof)
  + 同态加密(Homomorphic Encryption)
+ 经典协议
  + 混淆电路协议[Yao86]
    + Mike Rosulek教授讲授的混淆电路的基本思想及其优化[Optimizations to garbled circuits (point-permute, free-XOR, half-gates, arithmetic garbling)](https://web.engr.oregonstate.edu/~rosulekm/cryptabit/2-gc.pdf)
  + GMW协议[GMW87]
  + BGW协议[BGW88]
  + BMR协议[BMR90]
+ 通用协议框架
  + 基于混淆电路的MPC协议
  + 基于秘密共享的MPC协议
  + 基于同态加密的MPC协议
  + 混合协议
    + SPDZ框架：基于秘密共享和有限同态加密的协议框架
    + ABY系列：基于布尔电路、算术电路和混淆电路的协议框架，包括ABY、ABY3和ABY2.0
+ 应用研究
  + 隐私集合操作(Private Set Operation)
  + 隐私保护机器学习(Privacy Preserving Machine Learning)
  + ...
