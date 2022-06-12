# 重要会议中MPC相关论文

## [Eurocrypt 2022](https://eurocrypt.iacr.org/2022/acceptedpapers.php)
+ [Single-Server Private Information Retrieval with Sublinear Amortized Time](https://eprint.iacr.org/2022/081.pdf)
  + 作者&机构：Henry Corrigan-Gibbs, Alexandra Henzinger, Dmitry Kogan(MIT)
  + 主要内容：隐私信息检索
+ [EpiGRAM: Practical Garbled RAM]()
  + 作者&机构：David Heath, Vladimir Kolesnikov, Rafail Ostrovsky
+ [Garbled Circuits With Sublinear Evaluator](https://link.springer.com/chapter/10.1007/978-3-031-06944-4_2)
  + 作者&机构：Abida Haque, David Heath, Vladimir Kolesnikov, Steve Lu, Rafail Ostrovsky, Akash Shah
  + 主要内容：混淆电路优化
+ [Round-Optimal and Communication-Efficient Multiparty Computation](https://eprint.iacr.org/2020/1437.pdf)
  + 作者&机构：Michele Ciampi, Rafail Ostrovsky, Hendrik Waldner, Vassilis Zikas
  + 主要内容：安全多方计算优化
+ [Highly Efficient OT-Based Multiplication Protocols](https://eprint.iacr.org/2021/1373.pdf)
  + 作者&机构：Iftach Haitner, Nikolaos Makriyannis, Samuel Ranellucci, Eliad Tsfadia
  + 主要内容：基于OT的高效乘法协议
+ [Batch-OT with Optimal Rate]()
  + 作者&机构：Zvika Brakerski, Pedro Branco, Nico Döttling, Sihang Pu
  + 主要内容：OT优化
+ [Adaptively Secure Computation for RAM Programs](https://link.springer.com/chapter/10.1007/978-3-031-07085-3_7)
  + 作者&机构：Laasya Bangalore, Rafail Ostrovsky, Oxana Poburinnaya, Muthuramakrishnan Venkitasubramaniam
+ [Round-Optimal Multi-Party Computation with Identifiable Abort](https://eprint.iacr.org/2022/645.pdf)
  + 作者&机构：Michele Ciampi, Divya Ravi, Luisa Siniscalchi, Hendrik Waldner
+ [Secure Multiparty Computation with Free Branching](https://link.springer.com/chapter/10.1007/978-3-031-06944-4_14)
  + Aarushi Goel, Mathias Hall-Andersen, Aditya Hegde, Abhishek Jain
+ [Secure Multiparty Computation with Sublinear Preprocessing](ttps://link.springer.com/chapter/10.1007/978-3-031-06944-4_15)
  + 作者&机构：Elette Boyle, Niv Gilboa, Yuval Ishai, Ariel Nof

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

## [S&P 2022](https://www.ieee-security.org/TC/SP2022/program-papers.html)
+ [Multi-Server Verifiable Computation of Low-Degree Polynomials](https://www.computer.org/csdl/proceedings-article/sp/2022/131600b499/1A4Q4ozkJbi)
  + 作者&机构：Liang Feng Zhang (ShanghaiTech University), Huaxiong Wang (Nanyang Technological University)
  + 主要研究内容：可验证计算允许计算能力较弱的用户将复杂计算任务委托（外包）给计算资源密集的云服务器并对云服务器计算过程的正确性进行验证。更多介绍见[信息学院张良峰课题组在多服务器非交互式可验证计算研究方面取得重要进展](https://sist.shanghaitech.edu.cn/2021/1129/c2858a166288/page.htm)
  + 相关工作：[Two-Server Verifiable Homomorphic Secret Sharing for High-Degree Polynomials](https://arxiv.org/abs/2104.12163)
+ [Private Nearest Neighbor Search with Sublinear Communication and Malicious Security](https://eprint.iacr.org/archive/2021/1157/20211217:135438)
  + 作者&机构：Sacha Servan-Schreiber (Massachusetts Institute of Technology), Simon Langowski (Massachusetts Institute of Technology), Srinivas Devadas (Massachusetts Institute of Technology)
  + 主要研究内容：具有**次线性通信**和恶意安全的隐私最近邻搜索(轻量级)
+ [Publicly Accountable Robust Multi-Party Computation](https://eprint.iacr.org/2022/436.pdf)
  + 作者&机构：Marc Rivinius (University of Stuttgart), Pascal Reisert (University of Stuttgart), Daniel Rausch (University of Stuttgart), Ralf Küsters (University of Stuttgart)
  + 主要内容：恶意安全多方计算协议
+ [SecFloat: Accurate Floating-Point meets Secure 2-Party Computation](https://www.microsoft.com/en-us/research/uploads/prod/2022/04/main-6266710a3c049.pdf)
  + 作者&机构：Deevashwer Rathee (UC Berkeley), Anwesh Bhattacharya (Microsoft Research India), Rahul Sharma (Microsoft Research India), Divya Gupta (Microsoft Research India), Nishanth Chandran (Microsoft Research India), Aseem Rastogi (Microsoft Research India)
  + 主要研究内容：支持浮点数的安全两方计算协议
+ [Sphinx: Enabling Privacy-Preserving Online Learning over the Cloud](https://cse.hkust.edu.hk/~kaichen/papers/sphinx-sp22.pdf)
  + 作者&机构：Han Tian (Hong Kong University of Science and Technology), Chaoliang Zeng (Hong Kong University of Science and Technology), Zhenghang Ren (Hong Kong University of Science and Technology), Di Chai (Hong Kong University of Science and Technology), Junxue ZHANG (Hong Kong University of Science and Technology), Kai Chen (Hong Kong University of Science and Technology), Qiang Yang (Hong Kong University of Science and Technology)
  + 主要研究内容：该研究提出了一种隐私保护在线深度学习框架 Sphinx，该学习框架无需任何受信任的第三方，并且在训练和推理中较之前方案都有明显提升。Sphinx 将其神经网络模型中的线性参数 (linear) 保持为明文，并使用差分隐私技术进行隐私保护；其加和偏差部分模型参数 (bias) 使用同态加密技术进行加密保护。Sphinx 结合同态加密、差分隐私和秘密共享多种隐私保护技术，根据训练和推理的具体任务特点提出了定制且兼容的训练和推理混合协议，从而实现快速的训练和推理计算。Sphinx 通过对隐私保护场景下推理和训练协议进行系统优化，在模型性能、计算效率和隐私保护之间取得平衡
  + 更多内容详见[IEEE S&P 2022丨速度提升达4-6个数量级，港科大、星云Clustar联合提出隐私保护的在线机器学习新框架](https://cloud.tencent.com/developer/article/1964982)
+ [Spiral: Fast, High-Rate Single-Server PIR via FHE Composition](https://eprint.iacr.org/2022/368.pdf)
  + 作者&机构：Samir Jordan Menon (None), David J. Wu (UT Austin)
  + 主要研究内容：针对单服务器隐私信息检索问题，利用同态加密技术，在不泄露用户隐私的情况下完成隐私检索任务
+ [Waldo: A Private Time-Series Database from Function Secret Sharing]()
  + 作者&机构：Emma Dauterman (UC Berkeley), Mayank Rathee (UC Berkeley), Raluca Popa (UC Berkeley), Ion Stoica (UC Berkeley)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

## [NDSS 2022](https://www.ndss-symposium.org/ndss2022/accepted-papers/)
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

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

## [AsicaCCS 2022](https://www.ndss-symposium.org/ndss2022/accepted-papers/)
+ [Secure-Computation-Friendly Private Set Intersection from Oblivious Compact Graph Evaluation](https://dl.acm.org/doi/10.1145/3488932.3501278)
  + 作者&机构：J. Ma; S. Chow
  + 主要内容：隐私集合求交
+ [Byzantine-Robust Private Information Retrieval with Low Communication and Efficient Decoding](https://dl.acm.org/doi/10.1145/3488932.3497773)
  + 作者&机构：L. Zhang; H. Wang
  + 主要内容：隐私信息检索
+ [Privacy-Preserving Deep Sequential Model with Matrix Homomorphic Encryption](https://dl.acm.org/doi/10.1145/3488932.3523253)
  + 作者&机构：J. Jang; A. Kim; B. Na; Y. Lee; D. Yhee; B. Lee; J. Cheon; S. Yoon
  + 主要内容：隐私保护深度序列模型
+ [PSImple: Practical Multiparty Maliciously-Secure Private Set Intersection](https://dl.acm.org/doi/10.1145/3488932.3523254)
  + 作者&机构：A. Efraim; O. Nissenbaum; E. Omri; A. Paskin-Cherniavsky
  + 主要内容：实用隐私集合求交
+ [Adversarial Level Agreements for Two-Party Protocols](https://dl.acm.org/doi/10.1145/3488932.3517385)
  + 作者&机构：M. George; S. Kamara
  + 主要内容：考虑隐蔽敌手（理性敌手）的安全两方计算协议
+ [Iterative Oblivious Pseudo-Random Functions and Applications](https://dl.acm.org/doi/10.1145/3488932.3517403)
  + 作者&机构：E. Blass; F. Kerschbaum; T. Mayberry
  + 主要内容：
+ [Hunter: HE-Friendly Structured Pruning for Efficient Privacy-Preserving Deep Learning]()
  + 作者&机构：Y. Cai; Q. Zhang; R. Ning; C. Xin; H. Wu
  + 主要内容：
+ [Easy-to-Implement Two-Server based Anonymous Communication with Simulation Security](https://dl.acm.org/doi/10.1145/3488932.3523264)
  + 作者&机构：A. Bowers; J. Du; D. Lin; W. Jiang
  + 主要内容：提出了一种简单而新颖的 SMC 方法来建立匿名通信，该方法可以通过两个仅具有通信和存储相关功能的非共谋服务器轻松实现。
+ [Memory and Round-Efficient MPC Primitives in the Pre-Processing Model from Unit Vectorization](https://dl.acm.org/doi/abs/10.1145/3488932.3517407)
  + 作者&机构：N. Attrapadung; H. Morita; K. Ohara; J. Schuldt; K. Tozawa
  + 主要内容：
+ [Scalable Private Decision Tree Evaluation with Sublinear Communication](https://arxiv.org/pdf/2205.01284)
  + 作者&机构：J. Bai; X. Song; S. Cui; E. Chang; G. Russello
  + 主要内容：隐私保护决策树算法









