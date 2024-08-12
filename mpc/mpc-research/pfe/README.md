# 私有函数评估（Private Function Evaluation，PFE）

私有函数评估（Private Function Evaluation，PFE）是一种密码学技术，旨在允许参与方在不泄露输入数据和函数内容的前提下，安全地评估一个函数。PFE的典型场景是多个参与方分别持有自己的私有数据和一个需要评估的函数，其中函数的内容对于输入方也是保密的。PFE确保在计算过程中，输入方无法得知函数的具体形式，而函数持有方也无法获取输入数据的详细信息。

<img width="994" alt="image" src="https://github.com/user-attachments/assets/2466aeee-ea00-4c63-89cb-466157b1feff">

另外，Semi-Private Function Evaluation (SPFE)被提出，与 PFE 不同，SPFE 不会隐藏整个函数，而是会泄露某些子函数的拓扑。SPFE 可应用于特定函数组件已公开的 PFE 场景，这种方法在某些函数细节已公开的情况下特别有用，通常用于促销目的。汽车保险公司为经验丰富的驾驶员提供折扣就是一个例子。

# 1. PFE学习路线

相比于安全函数评估（Secure Function Evaluation， SFE），私有函数评估（Private Function Evaluation，PFE）研究较少，主要通过论文进行学习，在下面的相关论文中，对现有的PFE技术路线进行了分类，下面用表格的形式进行总结。

+ **UC-based PFE**：基于Universal Circuit的PFE，该方法将PFE归约到SFE，但是电路大小为$O(n \log n)$，$n$是原电路大小，而且现有构造已经达到了最常见UC构造方式的下限，因此预计不会有显著的改进。（如Table 1所示）
+ **OT-based PFE**：基于OT的PFE采用oblivious evaluation of a switching network技术来隐藏布尔电路的拓扑结构，然而现有基于OT的构造通信量会比基于UC的构造大
+ **HE-based PFE**：基于HE的PFE利用同态加密（但不是全同态加密）来隐藏布尔电路的拓扑结构，尽管看起来比较笨重，但是现有结果表明该构造是实用的
+ **TEE-based PFE**：基于TEE的PFE需要依赖特定的硬件，例如 Intel SGX，而且适合电路较小的情况（目前正在研究的TDX能够在一定程度上能支持较大电路的计算）

<img width="1215" alt="image" src="https://github.com/user-attachments/assets/be7f328c-2a41-49f6-be25-264335cef3b5">

* Table 1来自于 [[DGS+23]Breaking the Size Barrier: Universal Circuits meet Lookup Tables](https://eprint.iacr.org/2022/1652.pdf)
* 上述总结的结论来自于[[HKRS20]Linear-Complexity Private Function Evaluation is Practical](https://eprint.iacr.org/2020/853)

|  Protocol   | Methodology |  Num. of Parties | Security Model |     Round     | Circuits Complexity |
|:-----------:|:-----------:|:----------------:|:--------------:|:--------------:|:-----------------:|
|    [LWY22]  |      OT     |         2        | Mal. and PVC   | Constant      |         O(n)       |

* SH stands for Semi-Honest, Mal. stands for Malicious, and PVC stands for Publicly Verifiable Covertly


  

# 2. PFE相关论文

+ ******
  + 123
  + 论文发表在，论文链接见[]()
+ ******
  + 123
  + 论文发表在，论文链接见[]()
+ ******
  + 123
  + 论文发表在，论文链接见[]()
+ ******
  + 123
  + 论文发表在，论文链接见[]()
