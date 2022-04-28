# 安全多方计算

安全多方计算(Secure Multiparty Computation，MPC)最初由图灵奖获得者、中国科学院院士姚期智教授在1982年通过百万富翁问题提出。

经典的MPC协议常常指n个互不信任的参与方，通过MPC协议来共同计算某个功能函数，并且要求在计算完成后不会泄露各个参与方输入的任何信息。而对于广义的安全多方计算则包括指的是在分布式计算场景下，互不信任的参与方实现安全计算的目的。经过多年的理论和实践的研究，实用安全多方计算已经得到了长足的发展，为目前十分热门的“隐私计算”概念提供了技术解。

## 安全多方计算基本框架
安全多方计算(MPC)的基本概念和基础工具构成了安全多方计算的基石，近些年基于此进行了大量的通用安全多方计算协议研究，并在结合应用形成了大量的安全多方计算应用研究。关于MPC的理论和实践的基本框架详见[安全多方计算基本框架](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc-learning)。

## 如何学习安全多方计算？

在[安全多方计算学习路线](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc-learning)中，我们详细介绍了安全多方计算的学习路线和学习材料，下面是关于安全多方计算学习的概述。

+ MPC大牛的学习经验
  + [Yehuda Lindell](https://u.cs.biu.ac.il/~lindell/)谈如何学习安全多方计算
    + [Resources for Getting Started with MPC](https://u.cs.biu.ac.il/~lindell/MPC-resources.html)
    + 综述文章[Secure Multiparty Computation (MPC)](https://eprint.iacr.org/2020/300.pdf)
  + [Mike Rosulek](https://web.engr.oregonstate.edu/~rosulekm/)谈论如何入门学习安全多方计算
    + [An Annotated Bibliography of Practical Secure Computation](https://web.engr.oregonstate.edu/~rosulekm/scbib/index.php?n=Main.GettingStarted)
+ MPC课程学习
  + 第一届BIU密码学冬令营：安全多方计算与效率
    + [The 1st BIU Winter School: Secure Computation and Efficiency (01/30 - 02/01, 2011)](https://cyber.biu.ac.il/event/the-1st-biu-winter-school/)
  + 第五届BIU密码学冬令营：实用安全多方计算进展
    + [The 5th BIU Winter School: Advances in Practical Multiparty Computation (02/15 – 02/19, 2015)](https://cyber.biu.ac.il/event/the-5th-biu-winter-school/)
  + [Arpita Patra](https://www.csa.iisc.ac.in/~arpita/index.html)关于安全多方计算的课程
    + [Secure Computation 2015](https://www.csa.iisc.ac.in/~arpita/SecureComputation15.html)
    + [Secure Computation 2017](https://www.csa.iisc.ac.in/~arpita/FoSC17.html)
+ MPC相关书籍
  + [[Evans et al.2018]A Pragmatic Introduction to Secure Multi-Party Computation](https://securecomputation.org/)
    + 该书概述了安全多方计算中的定义、基本工具和经典协议，并调查了提高使用 MPC 构建的隐私保护应用程序效率的方法。除了对该领域的广泛概述和主要结构的见解外，还概述了当前最活跃的MPC研究领域，旨在让读者深入了解当今使用MPC可以实际解决哪些问题，以及不同的威胁模型和假设如何影响 不同方法的实用性。
  + [[Hazay&Lindell2010]Efficient Secure Two-Party Protocols](https://u.cs.biu.ac.il/~lindell/efficient-protocols.html)
    + 该书详细介绍了安全两方计算的基本概念，和相关的工具和技术。
    + [Download](https://link.springer.com/book/10.1007/978-3-642-14303-8)