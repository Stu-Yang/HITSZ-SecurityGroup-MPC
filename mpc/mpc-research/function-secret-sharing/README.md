# 函数秘密共享

函数秘密共享（Function Secret Sharing，FSS）是[Elette Boyle](https://cs.idc.ac.il/~elette/)等人在2015年提出的密码学原语，其将函数作为秘密分发的对象，使得参与方获得函数秘密份额，之后参与方便在本地函数秘密份额评估，获得结果的秘密份额。函数秘密共享是同态秘密共享的对偶过程，二者在不同的应用中均获得良好的性能。


## FSS-Paper
+ [GI14]Distributed Point Functions and Their Applications
  + 分布式点函数及其在PIR上的应用（函数秘密共享本质上是分布式点函数更泛化的表示）
  + 发表在EuroCrypto 2014，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-642-55220-5_35)、[ePrint](https://www.iacr.org/conferences/eurocrypt2014/37)
+ [BGI15]Function Secret Sharing
  + 函数秘密共享的开山之作，首次提出了DPF的FSS构造
  + 发表在EuroCrypto 2015，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-662-46803-6_12)
+ [BGI16]Function Secret Sharing: Improvements and Extensions
  + 函数秘密共享的进一步研究，优化了DPF的FSS构造，并首次提出针对决策树的FSS构造
  + 发表在CCS 2016，论文链接见[ACM CCS](https://dl.acm.org/doi/10.1145/2976749.2978429)、[ePrint](https://eprint.iacr.org/2018/707)
+ [BGI19]Secure Computation with Preprocessing via Function Secret Sharing
  + 利用函数秘密共享实现了预处理模型下的安全计算协议
  + 发表在TCC 2019，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-030-36030-6_14)、[ePrint](https://eprint.iacr.org/2019/1095)
+ [BCG+21]Function Secret Sharing for Mixed-Mode and Fixed-Point Secure Computation
  + BGI19的进一步优化，提出了针对更多非线性函数的FSS构造方案
  + 发表在EuroCrypto 2021，论文链接见[Springer](https://link.springer.com/chapter/10.1007/978-3-030-77886-6_30)、[ePrint](https://eprint.iacr.org/2020/1392)

## FSS-Online-Talk
+ [The 12th BIU Winter School on Cryptography: Advances in Secure Computation](https://cyber.biu.ac.il/event/the-12th-biu-winter-school-on-cryptography/)
  + 第12届BIU密码学冬令营中有Elette Boyle讲述的关于函数秘密共享的相关内容([Slide](http://cyber.biu.ac.il/wp-content/uploads/2021/11/FSS-2022-BIU-WinterSchool_Elette.pdf))
    + Function Secret Sharing: Definition ([Video](https://www.youtube.com/watch?v=fAXlOOs2t88))
    + Function Secret Sharing: Core Constructions of DPF and DCF ([Video](https://www.youtube.com/watch?v=Zm-MUVve2_w))
    + Function Secret Sharing: Extensions & Applications ([Video](https://www.youtube.com/watch?v=ORBLeo3lB4U&t=9s))




