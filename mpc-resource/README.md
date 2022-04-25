# MPC资源

## 安全多方计算书籍

+ [[Evans et al.2018]A Pragmatic Introduction to Secure Multi-Party Computation](https://securecomputation.org/)
  + 该书概述了安全多方计算中的定义、基本工具和经典协议，并调查了提高使用 MPC 构建的隐私保护应用程序效率的方法。除了对该领域的广泛概述和主要结构的见解外，还概述了当前最活跃的MPC研究领域，旨在让读者深入了解当今使用MPC可以实际解决哪些问题，以及不同的威胁模型和假设如何影响 不同方法的实用性。

+ [[Hazay&Lindell2010]Efficient Secure Two-Party Protocols](https://link.springer.com/book/10.1007/978-3-642-14303-8)
  + 该书详细介绍了安全两方计算的基本概念，和相关的工具和技术。

+ [[Lindell2021]A Tutorial on the Simulation Proof Technique](https://eprint.iacr.org/2016/046.pdf)
  + 该书介绍了安全多方计算中的安全性定义和证明，从加密到零知识证明，再到安全多方计算，循序渐进地介绍了如何理解安全多方计算中的安全性定义，以及如何使用工具来证明安全多方计算协议的安全性

## 安全多方计算课程

+ 印度科技学院的[Arpita Patra](https://www.csa.iisc.ac.in/~arpita/index.html)教授关于安全多方计算的课程
  + [Secure Computation 2015](https://www.csa.iisc.ac.in/~arpita/SecureComputation15.html)
  + [Secure Computation 2017](https://www.csa.iisc.ac.in/~arpita/FoSC17.html)

## 安全多方计算教程和幻灯片

+ 俄勒冈州立大学的[Mike Rosulek](https://web.engr.oregonstate.edu/~rosulekm/)讲述的高效安全计算技术课程，重点介绍了基于混淆电路的安全两方计算(2PC)和隐私集合求交(PSI)

  + **Day 1:** Overview of secure computation (applications and definitions) and textbook Yao's protocol. [slides](https://web.engr.oregonstate.edu/~rosulekm/cryptabit/1-overview.pdf)

  + **Day 2:** Optimizations to garbled circuits (point-permute, free-XOR, half-gates, arithmetic garbling). [slides](https://web.engr.oregonstate.edu/~rosulekm/cryptabit/2-gc.pdf)

  + **Day 3:** Optimizations to oblivious transfer (Beaver precomputation, OT extension, IKNP protocol and variants). [slides](https://web.engr.oregonstate.edu/~rosulekm/cryptabit/3-ot.pdf)

  + **Day 4:** Protecting Yao's protocol from malicious attacks (cut-and-choose & its subtleties, cheating punishment, dual execution variants, batch cut-and-choose) [slides](https://web.engr.oregonstate.edu/~rosulekm/cryptabit/4-malicious.pdf)

  + **Day 5:** Private set intersection (classic DH protocol, OT-based equality tests, hashing techniques) [slides](https://web.engr.oregonstate.edu/~rosulekm/cryptabit/5-psi.pdf)

  + [Homework problems](https://web.engr.oregonstate.edu/~rosulekm/cryptabit/problems.pdf) for all days
