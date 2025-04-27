# NDSS中MPC相关论文

## NDSS 2025

> 详见[NDSS 2025 accepted-papers](https://www.ndss-symposium.org/ndss2025/accepted-papers/)

<details>
<summary>以下是NDSS 2023中MPC相关论文，请点击展开</summary>
  
+ ***[ZYH+25]Secure Transformer Inference Made Non-interactive***
  + 基于同态加密的非交互Transformer推理
  + 论文链接见[NDSS 2025](https://www.ndss-symposium.org/ndss-paper/secure-transformer-inference-made-non-interactive/)
+ ***BumbleBee: Secure Two-party Inference Framework for Large Transformers***
  + 基于半诚实安全两方计算的Transformer推理
  + 论文链接见[NDSS 2025](https://www.ndss-symposium.org/ndss-paper/bumblebee-secure-two-party-inference-framework-for-large-transformers/)
+ ***Distributed Function Secret Sharing and Applications***
  + 高效地实现了函数秘密共享的离线阶段，并基于此实现了许多基础模块
  + 论文链接见[NDSS 2025](https://www.ndss-symposium.org/ndss-paper/distributed-function-secret-sharing-and-applications/)
+ ***A New PPML Paradigm for Quantized Models***
  + 基于私有查找表评估的半诚实两方量化神经网络推理
  + 论文链接见[NDSS 2025](https://www.ndss-symposium.org/ndss-paper/a-new-ppml-paradigm-for-quantized-models/)
+ ***Siniel: Distributed Privacy-Preserving zkSNARK***
  + 分布式隐私保护zkSNARK
  + 论文链接见[NDSS 2025](https://www.ndss-symposium.org/ndss-paper/siniel-distributed-privacy-preserving-zksnark/)

</details>

## NDSS 2023

> 详见[NDSS 2023 accepted-papers](https://www.ndss-symposium.org/ndss2023/accepted-papers/)

<details>
<summary>以下是NDSS 2023中MPC相关论文，请点击展开</summary>

+ ***[KBM23]Faster Secure Comparisons with Offline Phase for Efficient Private Set Intersection***
  + 在隐私集合求交（PSI）协议中，Alice和Bob计算他们各自集合的交集，而不公开任何不在交集中的元素。PSI协议在文献中得到了广泛的研究，并在工业中得到了部署。随着最先进的协议实现最佳渐近复杂度，性能改进很少，只能提高复杂度常数。在本文中，我们提出了一种新的私有的、非常有效的比较协议，该协议导致了具有低常数的PSI协议。我们的比较协议的一个有用特性是，它可以分为在线和离线阶段。所有昂贵的加密操作都是在离线阶段执行的，而在线阶段每次比较只执行四个快速字段操作。这导致了令人难以置信的快速在线阶段，我们的评估表明，它优于相关工作，包括KKRT（CCS’16）、VOLE-PSI（EuroCrypt’21）和OKVS（Crypto’21）。我们还评估了使用不同信任假设实现离线阶段的标准方法：加密、硬件和第三方（“经销商模型”）。
  + 论文链接见[NDSS 2023](https://www.ndss-symposium.org/ndss-paper/faster-secure-comparisons-with-offline-phase-for-efficient-private-set-intersection/), [arxiv](https://arxiv.org/abs/2209.13913)
+ ***[DWL+23]Fusion: Efficient and Secure Inference Resilient to Malicious Servers***
  + 基于Mix-and-Check技术实现的恶意安全两方计算学习推理，能够抵御恶意服务器
  + 论文链接见[NDSS 2023](https://www.ndss-symposium.org/ndss-paper/fusion-efficient-and-secure-inference-resilient-to-malicious-servers/), [arxiv](https://arxiv.org/abs/2205.03040)
</details>

## NDSS 2022

> 详见[NDSS 2022 accepted-papers](https://www.ndss-symposium.org/ndss2022/accepted-papers/)

<details>
<summary>以下是NDSS 2022中MPC相关论文，请点击展开</summary>

+ [Binary Search in Secure Computation](https://eprint.iacr.org/2021/1049.pdf)
  + 作者&机构：Marina Blanton and Chen Yuan (University at Buffalo (SUNY))
  + 主要内容：安全二分查找算法
+ [hbACSS: How to Robustly Share Many Secrets](https://eprint.iacr.org/2021/159.pdf)
  + 作者&机构：Thomas Yurek and Licheng Luo (University of Illinois at Urbana-Champaign); Jaiden Fairoze (University of California, Berkeley); Aniket Kate (Purdue University); Andrew Miller (University of Illinois at Urbana-Champaign)
  + 主要内容：利用可认证(鲁棒)秘密共享实现秘密分发
+ [Tetrad: Actively Secure 4PC for Secure Training and Inference](https://arxiv.org/abs/2106.02850)
  + 作者&机构：Nishat Koti and Arpita Patra (IISc Bangalore); Rahul Rachuri (Aarhus University, Denmark); Ajith Suresh (IISc, Bangalore)
  + 主要内容：基于恶意安全四方计算的隐私机器学习训练和推理
+ [To Trust or Not to Trust: Hybrid Multi-party Computation with Trusted Execution Environment](https://www.ndss-symposium.org/wp-content/uploads/2022-173-paper.pdf)
  + 作者&机构：Pengfei Wu and Ee-Chien Chang (School of Computing, National University of Singapore); Jianting Ning (Fujian Normal University); Hongbin Wang and Jiamin Shen (School of Computing, National University of Singapore)
  + 主要内容：结合可信执行环境和安全多方计算

</details>
