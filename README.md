# HITSZ安全组—MPC团队
多学习，多思考，多实践！

## 什么是安全多方计算？

安全多方计算(Secure Multi-Party Computation，MPC)起源于姚期智提出的“百万富翁问题”，并发展至今，成为了隐私计算领域的一项重要工具。姚期智在1982年借百万富翁问题提出安全两方计算的概念，并在1986年引入混淆电路协议(Garbled Circuits Protocol，GC)初步解决安全两方计算的问题，混淆电路协议至今都是许多最有效的MPC实现的基础，Goldreich等人在1987年针对多方参与的情况进行了分析。而后的20多年里，安全多方计算一直处于理论研究阶段，直至21世纪初，随着算法不断的改进和算力不断的提升，考虑使用通用多方计算(General purpose multiparty computation)构建实际系统变得现实。如今，安全多方计算在金融、医疗、银行、政务等领域已经有了广泛的应用。


## MPC知识学习

安全多方计算是一门复杂的学科，主要涉及近世代数、计算理论（特别是计算复杂性理论）、现代密码学、零知识证明、同态加密等，安全多方计算学习涉及书籍、论文和一些课程，[安全多方计算学习](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-learning)详细介绍了安全多方计算的基本框架和学习路线，并提供相关资源供大家学习。


## MPC课题研究

HITSZ安全组的MPC团队主要针对安全多方计算的理论与实践进行研究。
+ **理论研究**：关注协议的效率和安全性，提出/引入新技术，或者进行技术优化，从而提高协议的**效率**，或者加强协议的**安全性**
+ **实践研究**：将通用的安全多方计算协议结合实际应用场景，在协议落地过程中解决协议实用化过程中的**效率**和**安全性**方面的矛盾

[安全多方计算理论研究](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research)部分介绍一些研究的课题和可能的方向。[安全多方计算实践研究](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-practice)部分介绍了一些实践项目。


## 研究生经验总结

这部分，我们介绍了研究生学习期间关于课程学习、课题研究方面的一些经验，这部分会在[getting-started](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/getting-started)进行介绍。

## 关于我们

我们是HITSZ安全组MPC团队，致力于安全多方计算的理论研究和实践研究，目前我们的团队有以下成员
+ 2020级硕士生石松江、谢永杰
  + 石松江：主要研究具有隐私鲁棒性的安全四方计算协议
  + 谢永杰：主要研究基于ABY3的数据库安全查询协议
+ 2021级硕士生杨鹏：主要研究基于[函数秘密共享](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/function-secret-sharing)的高效安全两方计算协议，及其在隐私保护数据挖掘中的应用
+ 2022级硕士生庄杰航
+ 2020级本科生高世祺

## 常用索引
+ [安全多方计算理论研究](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research)
  + [conferences&journals](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/conferences%26journals)：介绍三大密码学会、四大安全顶会等重要会议中MPC相关的论文
  + [function-secret-sharing](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/function-secret-sharing)：介绍函数秘密共享，以及基于函数秘密共享实现安全两方计算协议。
    + [SyftNN](https://github.com/Stu-Yang/syftnn)：基于函数秘密共享的安全神经网络模型训练协议代码实现
  + [homomorphic-secret-sharing](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/homomorphic-secret-sharing)：介绍同态秘密共享，以及基于同态秘密共享的安全计算协议
+ [安全多方计算实践研究](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-practice)


