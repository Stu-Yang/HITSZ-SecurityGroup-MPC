# 私有函数评估（Private Function Evaluation，PFE）

私有函数评估（Private Function Evaluation，PFE）是一种密码学技术，旨在允许参与方在不泄露输入数据和函数内容的前提下，安全地评估一个函数。PFE的典型场景是多个参与方分别持有自己的私有数据和一个需要评估的函数，其中函数的内容对于输入方也是保密的。PFE确保在计算过程中，输入方无法得知函数的具体形式，而函数持有方也无法获取输入数据的详细信息。

<img width="600" alt="image" src="https://github.com/user-attachments/assets/2466aeee-ea00-4c63-89cb-466157b1feff">

另外，Semi-Private Function Evaluation (SPFE)被提出，与 PFE 不同，SPFE 不会隐藏整个函数，而是会泄露某些子函数的拓扑。SPFE 可应用于特定函数组件已公开的 PFE 场景，这种方法在某些函数细节已公开的情况下特别有用，通常用于促销目的。汽车保险公司为经验丰富的驾驶员提供折扣就是一个例子。

# 1. PFE学习路线

相比于安全函数评估（Secure Function Evaluation， SFE），私有函数评估（Private Function Evaluation，PFE）研究较少，主要通过论文进行学习，在下面的相关论文中，对现有的PFE技术路线进行了分类，下面用表格的形式进行总结。

+ **UC-based PFE**：基于Universal Circuit的PFE，该方法将PFE归约到SFE，但是电路大小为$O(n \log n)$，$n$是原电路大小，而且现有构造已经达到了最常见UC构造方式的下限，因此预计不会有显著的改进。（如Table 1所示）
+ **OT-based PFE**：基于OT的PFE采用oblivious evaluation of a switching network技术来隐藏布尔电路的拓扑结构，然而现有基于OT的构造通信量会比基于UC的构造大
+ **HE-based PFE**：基于HE的PFE利用同态加密（但不是全同态加密）来隐藏布尔电路的拓扑结构，尽管看起来比较笨重，但是现有结果表明该构造是实用的
+ **TEE-based PFE**：基于TEE的PFE需要依赖特定的硬件，例如 Intel SGX，而且适合电路较小的情况（目前正在研究的TDX能够在一定程度上能支持较大电路的计算）

<img width="600" alt="image" src="https://github.com/user-attachments/assets/be7f328c-2a41-49f6-be25-264335cef3b5">

* Table 1来自于 [[DGS+23]Breaking the Size Barrier: Universal Circuits meet Lookup Tables](https://eprint.iacr.org/2022/1652.pdf)
* 上述总结的结论来自于[[HKRS20]Linear-Complexity Private Function Evaluation is Practical](https://eprint.iacr.org/2020/853)


# 2. PFE相关论文

|  Protocol   | Methodology |  Num. of Parties | Security Model |     Round     | Circuits Complexity |
|:-----------:|:-----------:|:----------------:|:--------------:|:--------------:|:-----------------:|




|    [LWY22]  |      OT     |         2        | Mal. and PVC   | Constant      |         O(n)       |

* SH stands for Semi-Honest, Mal. stands for Malicious, and PVC stands for Publicly Verifiable Covertly

## 2.1 基于UC的PFE

+ ***[ZYZL19]Valiant’s Universal Circuits Revisited: an Overall Improvement and a Lower Bound***
  + 提出了电路大小为4.5n log n的UC构造，其中n是原模拟电路大小
  + 论文发表在ASIACRYPT 2019，论文链接见[eprint](https://eprint.iacr.org/2018/943)
+ ***[AGKS20]Effcient and Scalable Universal Circuits***
  + ZYZL19的优化和实现
  + 论文发表在JOC 2020，论文链接见[eprint](https://eprint.iacr.org/2019/348)
+ ***[LYZ+20]Pushing the Limits of Valiant's Universal Circuits: Simpler, Tighter and More Compact***
  + 提出了电路大小为∼3n log n的UC构造
  + 论文发表在CRYPTO 2020，论文链接见[eprint](https://eprint.iacr.org/2020/161.pdf)
+ ***[DGS+23]Breaking the Size Barrier: Universal Circuits meet Lookup Tables***
  + 提出了电路大小为1.5ρn log n的UC构造，其中ρ是查找表的输入个数
  + 论文发表在ASIACRYPT 2023，论文链接见[eprint](https://eprint.iacr.org/2022/1652)


## 2.2 基于OT的PFE

+ ***[MS13]How to Hide Circuits in MPC: An Efficient Framework for Private Function Evaluation***
  + 提出了基于oblivious switching network evaluation (OSN)的半诚实安全多方和两方PFE
  + 论文发表在EUROCRYPT 2013，论文链接见[eprint](https://eprint.iacr.org/2013/137)
+ ***[BBKL18]An Efficient 2-Party Private Function Evaluation Protocol Based on Half Gates***
  + 基于Half-Gates技术将MS13中的安全两方PFE中OT数量减少到原来的一半
  + 发表在The Computer Journal 2018，论文链接见[eprint](https://eprint.iacr.org/2017/415)

注：根据AGKS20的实现，实验显示MS13和BBKL18的通信效率都比基于UC的PFE差。而且，基于UC的PFE和基于OSN的PFE方案不可避免地会产生对数开销。见AGKS20图17和18（如下）

<img width="600" alt="image" src="https://github.com/user-attachments/assets/86087c99-d94e-4d4a-9dfe-1a6b346d8869">

+ ***[ZXZ22]Topology-hiding garbled circuits without universal circuits***
  + 通过提出拓扑隐藏的GC协议，设计了两轮的PFE协议
  + 发表在International Journal of Information Security，论文链接见[springer](https://link.springer.com/article/10.1007/s10207-021-00556-5)
+ ***[LWY22]Making Private Function Evaluation Safer, Faster, and Simpler***
  + 基于OSN和ZK实现了恶意安全和公开可验证隐蔽安全两方计算协议，同时保持常数轮和线性复杂度
  + 论文发表在PKC 2022，论文链接见[eprint](https://eprint.iacr.org/2021/1682)
+ ***[JLL+22]Generic 2-Party PFE with Constant Rounds and Linear Active Security, and Efficient Instantiation***
  + LWY22的优化，去掉了可重用属性，但使得第一次执行很高效
  + 发表在SecureComm 2022，论文链接见[springer](https://link.springer.com/chapter/10.1007/978-3-031-25538-0_21)
+ ***[XJL+23]Constant-Round Multiparty Private Function Evaluation with (Quasi-)Linear Complexities***
  + 基于OSN和HE实现了常数轮的多方半诚实PFE协议
  + 发表在ACNS 2023，论文链接见[springer](https://link.springer.com/chapter/10.1007/978-3-031-33491-7_5)


## 2.3 基于HE的PFE

+ ***[KM11]Constant-Round Private Function Evaluation with Linear Complexity***
  + 提出用同态加密来隐藏电路拓扑结构，基于混淆电路来实现常数轮的具有线性复杂度的PFE
  + 论文发表在ASIACRYPT 2011，论文链接见[eprint](https://eprint.iacr.org/2010/528)
+ ***[MSS14]Actively Secure Private Function Evaluation***
  + 在KM11的基础上基于零知识证明提出了恶意PFE，且具有线性复杂度
  + 论文发表在ASIACRYPT 2014，论文链接见[eprint](https://eprint.iacr.org/2014/102)
+ ***[BBKL18]Highly-Efficient and Reusable Private Function Evaluation with Linear Complexity***
  + 基于KM11提出了可重用的线性复杂度的两方PFE，该PFE构造具有可重用的属性。相比于KMM，其在第一次执行时总通信量略低，但在线计算量比KM11高出约四倍。后续运行具有相同函数的协议在通信和计算方面都比KM11更高效。
  + 论文发表在TDSC 2020，论文链接见[IEEE](https://ieeexplore.ieee.org/document/9141372), [eprint](https://eprint.iacr.org/2018/515)
+ ***[XJL+23]Constant-Round Multiparty Private Function Evaluation with (Quasi-)Linear Complexities***
  + 基于OSN和HE实现了常数轮的多方半诚实PFE协议
  + 发表在ACNS 2023，论文链接见[springer](https://link.springer.com/chapter/10.1007/978-3-031-33491-7_5)


## 2.4 基于TEE的PFE

+ ***[FKSW19]Secure and Private Function Evaluation with Intel SGX***
  + 将Intel SGX作为可信执行环境，利用基于UC的构造实现PFE
  + 论文发表在CCSW 2019，论文链接见[ACM CCSW](https://dl.acm.org/doi/10.1145/3338466.3358919)
+ ***[SRS+20]Private Function Evaluation Using Intel’s SGX***
  + 在Intel SGX中实现了基于UC和GC的PFE
  + 论文发表在SCN 2020，论文链接见[ACM](https://dl.acm.org/doi/abs/10.1155/2020/3042642)，[WILEY](https://onlinelibrary.wiley.com/doi/10.1155/2020/3042642，[code](https://github.com/maanrachid/PFE-SGX)


## 2.5 Semi-PFE

注：这部分工作主要关注电路隐藏

+ ***[PSS09]Practical Secure Evaluation of Semi-Private Functions***
  + 首次提出Semi-PFE，其提供了几个构建块，这些构建块可以用一类函数中的一个函数进行编程（例如，ADD/SUB 的电路具有相同的拓扑结构）
  + 论文发表于ACNS 2009，论文链接见[eprint](https://eprint.iacr.org/2009/124)
+ ***[GKSS19]Framework for Semi-Private Function Evaluation with Application to Secure Insurance Rate Calculation***
  + 提出SPFE 框架，该框架允许将函数拆分为公共和私有组件，将私有组件嵌入到 UC 中，并将它们合并为一个布尔电路，通过 MPC 进行评估。
  + 论文发表于CCS 2019（作为Poster进行展示），论文链接见[Encrypto-web](https://encrypto.de/papers/GKSS19.pdf)，[ACM CCS](https://dl.acm.org/doi/10.1145/3319535.3363251)，[code](https://github.com/danguenther/spfe-framework)


## 2.z 基于PFE的应用
+ ***OPFE: Outsourcing Computation for Private Function Evaluation***
  + 面向PFE的外包计算，协议分别可以抵御半诚实、隐蔽和恶意敌手
  + 论文发表在IJICS 2019（CCF C期刊），论文链接见[eprint](https://eprint.iacr.org/2016/067)
+ ***[JZLR22]Multi-party Private Function Evaluation for RAM***
  + 基于安全四方PFE的安全ORAM应用
  + 论文发表在TIFS 2023，论文链接见[IEEE TIF](https://ieeexplore.ieee.org/document/10015843)，[eprint](https://eprint.iacr.org/2022/939)
