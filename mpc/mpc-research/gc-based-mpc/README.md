## 基于混淆电路的安全多方计算协议

混淆电路（Garbled Circuits）是一种用于安全多方计算（Secure Multi-Party Computation, MPC）中的加密技术，由Andrew Yao在1986年提出。其基本思想是通过对电路的各个逻辑门进行加密，使得参与方能够在不知道输入和中间计算结果的情况下执行计算。混淆电路技术的发展包括优化电路大小和效率、减少通信开销和提高安全性等方面。

### 1.1 混淆电路学习路线
+ 混淆电路基础协议学习
  + 参考[Mike Rosulek](https://web.engr.oregonstate.edu/~rosulekm/)2PC Course，[video-gc](https://www.bilibili.com/video/BV1e64y1C7Te/?spm_id_from=333.999.0.0), [slides-textbook Yao's protocol](https://web.engr.oregonstate.edu/~rosulekm/cryptabit/1-overview.pdf)
  + 相关书籍参考[book-Pragmatic MPC](https://securecomputation.org/)-3.1 Yao’s Garbled Circuits Protocol
+ 混淆电路优化协议学习
  + 参考[Mike Rosulek](https://web.engr.oregonstate.edu/~rosulekm/)2PC Course，[video-gc optimation](https://www.bilibili.com/video/BV1hK4y197gW/?spm_id_from=333.999.0.0), [slides-Optimizations to garbled circuits (point-permute, free-XOR, half-gates, arithmetic garbling)](https://web.engr.oregonstate.edu/~rosulekm/cryptabit/2-gc.pdf)
  + 相关书籍参考[book-Pragmatic MPC](https://securecomputation.org/)-4.1 Less Expensive Garbling
  + 针对一些关键优化进行，通过阅读下面的论文来学习其具体协议
+ 恶意混淆电路协议学习
  + 参考参考[Mike Rosulek](https://web.engr.oregonstate.edu/~rosulekm/)2PC Course，[slides-Protecting Yao's protocol from malicious attacks](https://web.engr.oregonstate.edu/~rosulekm/cryptabit/4-malicious.pdf)
  + 相关书籍参考[book-Pragmatic MPC](https://securecomputation.org/)-6.1-6.4 Cut-and-Choose
+ 实用混淆电路协议学习
  + 针对一些混淆电路设计和实现，通过阅读下面的论文进行学习


### 1.2 混淆电路相关论文

+ ***[Yao86]How to generate and exchange secrets***
  + 混淆电路的开山之作（建议瞻仰，不建议阅读，因为没有阐述现行混淆电路协议的主要框架）
  + 发表在[FOCS86](https://ieeexplore.ieee.org/abstract/document/4568207)，论文链接见[github](https://mit6875.github.io/FA23HANDOUTS/yao-garbled-circuits.pdf)
+ ***Fairplay—A Secure Two-Party Computation System***
  + 第一个安全两方计算系统实现，基于混淆电路技术
  + 发表在[USENIX 2004](https://www.usenix.org/conference/13th-usenix-security-symposium/fairplay%E2%80%94-secure-two-party-computation-system)，论文链接见[usenix](https://www.usenix.org/conference/13th-usenix-security-symposium/fairplay%E2%80%94-secure-two-party-computation-system)
+ ***[HEKM11]Faster Secure Two-Party Computation Using Garbled Circuits***
  + 优化了基于混淆电路的半诚实安全两方系统FairPlay的实现，并面向Hamming distance、Smith-Waterman genome alignment, and AES等任务设计了隐私保护计算协议
  + 发表在[USENIX 2011]([https://www.usenix.org/legacy/events/sec11/tech/full_papers/Huang.pdf](https://www.usenix.org/conference/usenix-security-11/faster-secure-two-party-computation-using-garbled-circuits))，论文链接见[usenix](https://www.usenix.org/legacy/events/sec11/tech/full_papers/Huang.pdf), [video](https://www.usenix.org/conference/usenix-security-11/faster-secure-two-party-computation-using-garbled-circuits), [slides](https://www.usenix.org/legacy/events/sec11/tech/slides/huang.pdf)，[source code](https://mightbeevil.org/)
+ :triangular_flag_on_post: ***[BHR12]Foundations of garbled circuits***
  + 系统介绍了混淆电路，阐述了现行混淆电路协议的主要框架
  + 论文发表在[CCS 2012](https://dl.acm.org/doi/10.1145/2382196.2382279)，论文链接见[CCS](https://dl.acm.org/doi/10.1145/2382196.2382279), [IACR-ePrint](https://eprint.iacr.org/2012/265)
+ ******
  + 123
  + 论文发表在[]()，论文链接见[]()
+ ******
  + 123
  + 论文发表在[]()，论文链接见[]()
+ ******
  + 123
  + 论文发表在[]()，论文链接见[]()
+ ******
  + 123
  + 论文发表在[]()，论文链接见[]()
+ ******
  + 123
  + 论文发表在[]()，论文链接见[]()
+ ******
  + 123
  + 论文发表在[]()，论文链接见[]()
















