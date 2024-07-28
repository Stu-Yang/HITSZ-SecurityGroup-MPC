# MPC组2024年暑期学习：安全多方计算基础

> 点击 [README.md](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/edit/main/mpc/mpc-school/mpc-summer-2024/README.md) 修改内容。

## 1. 机器学习

### 1.1 深度神经网络

> pictures from [Deep Neural Network optimization: Binary Neural Networks](https://slideplayer.com/slide/17585887/)
<img width="615" alt="image" src="https://github.com/user-attachments/assets/d7daa063-60f2-4eea-8ff3-b57a26e1c595">




### 1.2 量化神经网络

+ **Intro to Binarized Neural Networks**
  + [Video](https://www.youtube.com/watch?v=d9AeVyRzU5Q)，[Slide](https://slideplayer.com/slide/17585887/)，[Binary Neural Networks: A Survey](https://arxiv.org/abs/2004.03333)，[A comprehensive review of Binary Neural Network](https://arxiv.org/abs/2110.06804)


## 2. 秘密共享

### 2.1 一些基础知识
+ **并行前缀加法器 Parallel Prefix Adder**
  + 主要内容：加法器（半加器和全加器）、超前进位加法器、并行前缀加法器，并行前缀加法器在MPC中的作用和应用
  + [Video](https://www.bilibili.com/video/BV1KA4y1Z74V/?spm_id_from=333.999.0.0&vd_source=45400e58cd0ed58d7605745553c0f81e), [Note](https://zhuanlan.zhihu.com/p/476627132), and [Slides](https://users.encs.concordia.ca/~asim/COEN_6501/Lecture_Notes/Parallel%20prefix%20adders%20presentation.pdf)

### 2.2 Sharim Secret Sharing and Packed Secret Sharing
> refer to [Efficient Secret Sharing for Large-Scale Applications](https://eprint.iacr.org/2024/1045.pdf)
<img width="563" alt="image" src="https://github.com/user-attachments/assets/85774df9-869e-4143-a13e-b42fdd1a4d49">

### 2.3 BDOZ and SPDZ



+ **多项式插值**
+ **Sharim秘密共享**
+ **打包秘密共享**
  + [TPMPC video-Communication Efficient MPC using Packed Secret Sharing](https://www.youtube.com/watch?v=xoxUbz-_S4w), [paper-CRYPTO 2022-Sharing Transformation and Dishonest Majority MPC with Packed Secret Sharing](https://eprint.iacr.org/2022/831)

## 3. 混淆电路

+ **Overview of secure computation and textbook Yao's protocol**
  + Main Idea: [Slides](https://web.engr.oregonstate.edu/~rosulekm/cryptabit/1-overview.pdf) and [Video](https://www.bilibili.com/video/BV1e64y1C7Te/?spm_id_from=333.999.0.0) from [Mike Rosulek](https://web.engr.oregonstate.edu/~rosulekm/)
  + Formal Definition: [JoC 2009-A Proof of Security of Yao’s Protocol for Two-Party Computation](https://eprint.iacr.org/2004/175), [Foundations of Garbled Circuits](https://eprint.iacr.org/2012/265.pdf)
+ **Optimizations to Garbled Circuits (point-permute, free-XOR, half-gates, arithmetic garbling)**
  + Main Idea: [Slides](https://web.engr.oregonstate.edu/~rosulekm/cryptabit/2-gc.pdf) and [Video](https://www.bilibili.com/video/BV1hK4y197gW/?spm_id_from=333.999.0.0) from [Mike Rosulek](https://web.engr.oregonstate.edu/~rosulekm/)
  + Formal Definition: [Half-Gates](https://eprint.iacr.org/2014/756), [CRYPTO 2021-Beating the Half-Gates](https://eprint.iacr.org/2021/749)

