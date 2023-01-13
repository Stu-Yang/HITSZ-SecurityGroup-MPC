# 1. 密态数据库查询(Encrypted database Query)

## 1.1 简单介绍

基于安全多方计算的密态数据库查询算法考虑这样的场景：有若干个云数据库$S_1,S_2,...,S_n$，数据拥有者将其数据放在数据库中，为了不让单一数据库知晓自己数据（数据中存在隐私），数据拥有者将自己的数据通过**加性秘密共享**技术分发给云数据库$S_1,S_2,...,S_n$，例如下面的一种方式：

1. 数据拥有者拥有数据$x$，打算将其存储在云数据库$S_1,S_2,...,S_n$中
2. 数据拥有者随机选择$n-1$个随机数$r_1,r_2,...r_{n-1}$，并计算$[x]_1 = r_1, [x]_2 = r_2, ..., [x]_{n-1} = r_{n-1}, x_{n} = x-r_1-r_2-...-r_{n-1}$
3. 数据拥有者将$[x]_i$发送给云数据库$S_i$，其中$i = 1,2,...,n$

通过这种方式，云数据库$S_i$分别拥有数据$x$的一部分$[x]_i$，而且$[x]_1+[x]_2+...+[x]_n = x$，通常将$[x]_i$称为数据的秘密份额，通过秘密份额$[x]_i$数据库无法知晓原始数据$x$。同样地，众多的数据拥有者将自己的数据以上述方式上传到云数据库，云数据库从而拥有了所有数据拥有者数据的秘密份额，因此可将这些云数据库称之为分布式密态数据库。

分布式密态数据库一旦形成，可以提供这样的服务：用户想要根据关键词（例如查询年龄大于18岁的男生）查询数据库，将其查询的关键字送给所有云数据库，云数据库通过执行一个安全多方计算协议来输出得到查询结果，并将查询结果返回给用户。在这个过程中，用户不会知道数据库中隐私数据，云数据库也不会泄露数据的隐私，这种范式称为**Database Query for Secret Shared Data**。

目前，两方云数据库和三方云数据库被广泛考虑，MPC团队的谢永杰师兄就考虑三方云数据库，其并没有使用上述**加性秘密共享**技术，而是使用**复制秘密共享**技术。

## 1.2 基于复制秘密共享的密态数据库查询

TODO：增加一些简单的介绍


## 1.3 相关论文

+ ***[DSZ15]ABY-A framework for efficient mixed-protocol secure two-party computation***
  + 混合协议开篇之作，ABY：算术秘密份额（A）、布尔秘密份额（B）和姚氏秘密份额（Y）
  + 发表在NDSS 2015，论文链接见[NDSS 2015](https://www.ndss-symposium.org/ndss2015/ndss-2015-programme/aby-framework-efficient-mixed-protocol-secure-two-party-computation/)，[encryptogroup](http://thomaschneider.de/papers/DSZ15.pdf)
+ :triangular_flag_on_post: ***[MR18]ABY3: A Mixed Protocol Framework for Machine Learning***
  + 利用**复制秘密共享**技术提出了恶意模型下基于混合协议的安全三方计算通用框架ABY3，但仅在半诚实模型下实现了线性回归、逻辑回归和神经网络的安全计算
  + 论文发表在CCS 2018，论文链接见[ACM CCS](https://dl.acm.org/doi/abs/10.1145/3243734.3243760)，[eprint](https://eprint.iacr.org/2018/403)
+ :triangular_flag_on_post: ***[MRR20]Fast Database Joins and PSI for Secret Shared Data***
  + 数据库查询论文
  + 论文发表在CCS 2020，论文链接见[ACM CCS](https://dl.acm.org/doi/10.1145/3372297.3423358)，[eprint](https://eprint.iacr.org/2019/518)
+ ***[PSSY21]ABY2.0: Improved Mixed-Protocol Secure Two-Party Computation***
  + 在ABY框架的基础上进一步减少了秘密份额转换的开销，降低了协议的通信开销
  + 论文发表在USENIX 2021，论文链接见[USENIX](https://www.usenix.org/conference/usenixsecurity21/presentation/patra)，[eprint](https://eprint.iacr.org/2020/1225)
+ :triangular_flag_on_post: ***[LKF+21]Secrecy-Secure collaborative analytics on secret-shared data***
  + 数据库查询论文
  + 论文在[Arxiv](https://arxiv.org/abs/2102.01048)
  
**📜【MRR 2020】*Fast Database Joins and PSI for Secret Shared Data***

- *Author(s)：*[Payman Mohassel](https://paymanmohassel.com/)，[Peter Rindal](https://ladnir.github.io/)，[Mike Rosulek](https://web.engr.oregonstate.edu/~rosulekm/)
- *Venue*：CCS
- *Materials：*[PDF](https://eprint.iacr.org/2019/518.pdf)，[Video](https://dl.acm.org/doi/10.1145/3372297.3423358)，[Code](https://github.com/ladnir/aby3)

---

**📜【BDGRR 2022】*Secret-Shared Joins with Multiplicity from Aggregation Trees***

- *Author(s)：*[Saikrishna Badrinarayanan](https://dl.acm.org/profile/99659027273)，[Sourav Das ](https://sourav1547.github.io/)，[Gayathri Garimella](https://gayathrigarimella.github.io/)，Srinivasan Raghuramam，[Peter Rindal](https://ladnir.github.io/)
- *Venue*：CCS
- *Materials：*[PDF](https://eprint.iacr.org/2022/1600.pdf)

---

**📜【BDGRR 2022】*Waldo: A Private Time-Series Database from Function Secret Sharing***

- *Author(s)：*[Emma Dauterman](https://dl.acm.org/profile/99659027273)，[Mayank Rathee](https://mayank0403.github.io/)，[Raluca Ada Popa](https://people.eecs.berkeley.edu/~raluca/)，[Ion Stoica](http://people.eecs.berkeley.edu/~istoica/)
- *Venue*：S&P
- *Materials：*[PDF](https://eprint.iacr.org/2021/1661.pdf)，[Slides](https://people.eecs.berkeley.edu/~edauterman/sp22_slides_waldo.pdf)，[Video1](https://www.youtube.com/watch?v=ygUZ61JZEE4)，[Video2](https://soroco.com/waldo-a-private-time-series-database-from-function-secret-sharing/)，[Video3](https://www.youtube.com/watch?v=_X5tm_9pe8w)，[Code](https://github.com/ucbrise/waldo)

# 2. 隐私信息检索（Private Information Retrieval，PIR）

隐私信息检索(Private Information Retrieval，PIR，也称匿踪查询)是安全多方计算中很实用的一项技术，用来保护用户的查询隐私。其目的是保证用户向服务器（数据源方）提交查询请求时，在用户查询信息不被泄漏的条件下完成查询，即整个查询过程中服务器不知道用户具体查询信息及查询出的数据项。

> 进一步了解，请参考[隐语小课｜私有信息检索(PIR)及其应用场景](https://mp.weixin.qq.com/s/Vf5AFep2JKztXpOt95WW8g)


# 3. 隐私频繁项查询

隐私频繁项查询（Private Heavy Hitters）
