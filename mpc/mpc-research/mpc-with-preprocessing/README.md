# 预处理模型下的安全多方计算协议
（Secure Multi-Party Computation in the Pre-processing model）

在预处理模型（Preprocessing Model）中，协议被分为预处理阶段（Preprocessing Phase）和在线阶段（Online Phase）。在预处理阶段（也称为设置阶段（Setup Phase）、离线阶段（Offline Phase）），各个参与方共同运行一个与数据独立安全协议来产生相关随机性（correlated randomness），这些相关值可以辅助完成计算任务；在线阶段则利用预处理阶段提供的相关值，基于参与方的数据来计算功能函数。这种基于预处理模型的两阶段协议的优点在于将在线阶段的大量计算移到预处理阶段，从而使得在线阶段的效率较高，由于在预处理阶段不需要知道参与者的输入，因此预处理阶段可以在目标计算任务之前的任何时间执行。

## 相关论文

+ 
