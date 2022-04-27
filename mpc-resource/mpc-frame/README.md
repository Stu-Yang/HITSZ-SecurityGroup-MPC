# 安全多方计算(MPC)的基本框架

在这里将介绍安全多方计算(MPC)的基本框架以及学习路线，对应地，也会提供一些学习资源

## MPC基本框架

MPC的基本概念和构建协议的基础模块是MPC的基石，在此之上有一些通用安全多方计算协议，其可以用于计算任意的功能函数，利用这些通用协议并结合应用便形成了安全多方计算的应用研究。

![](.\mpc-frame.png)

## MPC的学习路线

+ 基本概念
  + MPC基本概念
  + 安全性定义
  + 安全性证明
+ 基础模块
  + 不经意传输(Oblivious Transfer, OT)：基础OT和OT扩展
  + 秘密共享(Secret Sharing, SS)：门限秘密共享和加性秘密共享
  + 混淆电路(Garbled Circuits, GC)
  + 剪切-选择技术(Cut-and-Choose)
  + 零知识证明(Zero Knowledge Proof)
  + 同态加密(Homomorphic Encryption)
+ 经典协议
  + 混淆电路协议[Yao86]
  + GMW协议[GMW87]
  + BGW协议[BGW88]
  + BMR协议[BMR90]
+ 通用协议框架
  + 基于混淆电路的MPC协议
  + 基于秘密共享的MPC协议
  + 基于同态加密的MPC协议
  + 混合协议
    + SPDZ框架：基于秘密共享和有限同态加密的协议框架
    + ABY系列：基于布尔电路、算术电路和混淆电路的协议框架，包括ABY、ABY3和ABY2.0
+ 应用研究
  + 隐私集合操作(Private Set Operation)
  + 隐私保护机器学习(Privacy Preserving Machine Learning)
  + ...
