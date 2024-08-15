# Shamir Secret Sharing 和 Packed Secret Sharing

Shamir Secret Sharing（Shamir SS）是一种秘密共享方案，由Adi Shamir在1979年提出。其主要思想是将一个秘密分成多个份额（shares），并分发给参与者，使得只有当收集到一定数量的份额时，才能恢复出原始的秘密。具体来说，给定一个秘密s，可以选择一个足够高阶的多项式f(x)，使得f(0)=s，然后为每个参与者分配一个不同的x值，并计算相应的f(x) 作为其份额。通过拉格朗日插值，多数参与者可以联合恢复秘密。

Packed Secret Sharing（Packed SS）是Linear Secret Sharing (例如Shamir SS) 的一个变种，它通过打包多个秘密在同一个多项式中来提高效率。在Packed SS中，不是仅仅将一个秘密嵌入到多项式的常数项中，而是通过不同的系数嵌入多个秘密。例如，如果有多个秘密s1, s2, ..., sm，可以构造一个多项式f(x)=s1 + s2⋅x + s3⋅x^2 + ... + sm ⋅x^m−1 ，然后按照Shamir的方式分发份额。这样，通过收集足够多的份额，参与者可以同时恢复多个秘密。

<p align="center">
    <img src="https://github.com/user-attachments/assets/e5c90483-5bb4-432d-8c11-a69c8a131e90" width="600" />
</p>


## 1. Shamir SS和Packed Shamir SS学习路线

+ **Shamir SS学习路线**
  + 学习[安全多方计算短期课程-冯登国](https://www.bilibili.com/video/BV16j411q7pf/?vd_source=45400e58cd0ed58d7605745553c0f81e)中的[Lecture 2 基于秘密分享方法的 MPC 协议](https://www.bilibili.com/video/BV1Z8411Q7Af/?spm_id_from=333.788&vd_source=45400e58cd0ed58d7605745553c0f81e)，其中有关于Shamir Secret Sharing的介绍，相关资料见[slides](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/blob/main/mpc/mpc-research/shamir-ss-and-packed-shamir-ss/MPC%E5%9F%BA%E7%A1%80%E8%AE%B2%E4%B9%892-%E5%9F%BA%E4%BA%8E%E7%A7%98%E5%AF%86%E5%88%86%E4%BA%AB%E6%96%B9%E6%B3%95%E7%9A%84%E5%AE%89%E5%85%A8%E5%A4%9A%E6%96%B9%E8%AE%A1%E7%AE%97%E5%8D%8F%E8%AE%AE.pdf)
  + 学习[The Joy of Cryptography by Mike Rosulek](https://joyofcryptography.com/pdf/book.pdf)中的Section 3.4 Shamir Secret Sharing
+ **Packed Shamir SS学习路线**
  + 了解和掌握Shamir SS基本概念，然后了解Packed Shamir SS的基本概念及其与Shamir SS的区别，然后主要通过论文进行学习Packed Shamir SS

## 2. Shamir SS和Packed Shamir SS论文

### 2.1 Shamir秘密共享

### 2.2 Packed Secret Sharing（打包的Packed秘密共享）

+ ***[GPS21]Sharing Transformation and Dishonest Majority MPC with Packed Secret Sharing***
  + 基于Packed Secret Sharing设计的不诚实大多数MPC
  + 论文发表在CRYPTO 2022，论文链接见[eprint](https://eprint.iacr.org/2022/831), [video](https://www.youtube.com/watch?v=iuEI7l2Tbc8), [Goyal-TPMPC22-video](https://www.youtube.com/watch?v=xoxUbz-_S4w), [Goyal-TPMPC22-slides](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/blob/main/mpc/mpc-research/shamir-ss-and-packed-shamir-ss/%5BGoyal-TPMPC22%5DCommunication%20Efficient%20MPC%20using%20Packed%20Secret%20Sharing.pdf)
+ ***[GGJ+23]zkSaaS: Zero-Knowledge SNARKs as a Service***
  + 利用基于Packed Secret Sharing的安全多方计算协议实现ZKP分布式计算
  + 论文发表在USENIX Security 23，论文链接见[usenix](https://www.usenix.org/conference/usenixsecurity23/presentation/garg), [eprint](https://eprint.iacr.org/2023/905)
+ ***[EGPS22]TurboPack: Honest Majority MPC with Constant Online Communication***
  + 基于Packed Secret Sharing实现具有常数在线通信的诚实大多数MPC协议
  + 论文发表在CCS 2022，论文链接见[eprint](https://eprint.iacr.org/2022/1316)
+ ***[EGP+23]SUPERPACK: Dishonest Majority MPC with Constant Online Communication***
  + 基于Packed Secret Sharing实现具有常数在线通信的不诚实大多数MPC协议
  + 论文发表在EUROCRYPTO 2023，论文链接见[epirnt](https://eprint.iacr.org/2023/307)


