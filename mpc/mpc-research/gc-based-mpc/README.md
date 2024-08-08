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

+ ***Faster Secure Two-Party Computation Using Garbled Circuits***
  + Yan Huang, David Evans, Jonathan Katz, Lior Malka.
  + 介绍了基于混淆电路的安全两方计算协议
  + 发表在[USENIX 2011]([https://www.usenix.org/legacy/events/sec11/tech/full_papers/Huang.pdf](https://www.usenix.org/conference/usenix-security-11/faster-secure-two-party-computation-using-garbled-circuits))，论文链接见[usenix](https://www.usenix.org/legacy/events/sec11/tech/full_papers/Huang.pdf)
