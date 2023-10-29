# 同态秘密共享（Homomorphic Secret Sharing）

同态秘密共享是[Elette Boyle](https://cs.idc.ac.il/~elette/)在2016年提出的密码学原语，是全同态加密（Fully Homomorphic Encryption，FHE）的放松版本，基于同态秘密共享可以实现安全计算，相较于全同态加密能够获得较大的性能提升。

## 相关论文
+ [BGI16]Breaking the Circuit Size Barrier for Secure Computation Under DDH
  + 同态秘密共享的开山之作
  + 发表在Crypto 2016，论文链接见[eprint](https://eprint.iacr.org/2016/585)
+ [BGI17]Group-Based Secure Computation: Optimizing Rounds, Communication, and Computation
  + 同态秘密共享的开山续作
  + 发表在EuroCrypto 2017，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-319-56614-6_6) 
+ [BCG+17]Homomorphic Secret Sharing: Optimizations and Applications
  + 同态秘密共享的系统研究
  + 发表在CCS 2017，论文链接见[eprint](https://eprint.iacr.org/2018/419)
+ [BGIL18]Foundations of Homomorphic Secret Sharing
  + 发表在ITCS 2018，论文链接见[ePrint](https://eprint.iacr.org/2017/1248)
+ [BKS19]Homomorphic Secret Sharing from Lattices Without FHE
  + 发表在EuroCrypto 2019，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-030-17656-3_1)、[ePrint](https://eprint.iacr.org/2019/129)
+ [Boyle22]Function Secret Sharing and Homomorphic Secret Sharing
  + Boyle关于函数秘密共享（Function Secret Sharing）和同态秘密共享（Homomorphic Secret Sharing）综述
  + 暂未发表，文章链接见[Boyle-Survey](https://cs.idc.ac.il/~elette/HSS_FSS-Survey.pdf)
+ [DIJL23]Multi-Party Homomorphic Secret Sharing and Sublinear MPC from Sparse LPN
  + 给出了第一个针对非平凡函数类的多方 HSS 方案的构造
  + 论文发表在Crypto 2023，论文链接见[eprint](https://eprint.iacr.org/2023/1593)
