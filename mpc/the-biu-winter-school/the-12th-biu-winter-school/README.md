# The 12th BIU Winter School on Cryptography

> 部分Slide资料可能无法现在，请前往[addingIce/12th-BIU](https://github.com/addingIce/The-12th-BIU-Winter-School-on-Cryptography)进行下载。

## Advances in Secure Computation

## January 23-26, 2022

### **School Overview**

Secure computation allows a set of parties to compute some joint function of their private inputs, while guaranteeing privacy (i.e., the parties learn the output and nothing more) and correctness (meaning the output is correctly distributed). Due to its generality, secure computation is a central tool in cryptography. In recent years, there is a surging interest in deploying secure computation to solve problems arising in practice. This requires designing light-weight and concretely-efficient protocols for problems of interest, such as accessing and searching over large outsourced databases, or threshold cryptographic primitives (such as signatures) that can be used to guarantee validity of transactions on the blockchain. 

In the 12th BIU Winter School on Cryptography, we will study recent advances in secure computation. The program will cover the following topics: advances in private-information retrieval and in oblivious RAM, function secret sharing and homomorphic secret sharing, vector oblivious linear evaluation, threshold signatures, and private set intersection.

The program aims to give a taste of key topics in the area, focusing on the state of the art. We expect the audience to already have knowledge on foundations of cryptography (e.g., what secure computation is, the basics of private information retrieval and oblivious RAM, etc.). The target audience for the school is graduate students and postdocs in cryptography (we will assume that participants have taken at least one university-level course in cryptography). However, all faculty, undergrads and professionals *with the necessary background* are welcome. The winter school is open to participants from all over the world; all talks will be in English.

### **School Lecturers** 

+ [**Gilad Asharov**](https://u.cs.biu.ac.il/~asharog/), Bar-Ilan University
+ **[Elette Boyle](https://cs.idc.ac.il/~elette/)**, Reichman University (IDC)
+ **[Henry Corrigan-Gibbs](https://people.csail.mit.edu/henrycg/)**, MIT
+ **[Rosario Gennaro](https://www-cs.ccny.cuny.edu/~rosario/)**, City College of New York and Protocol Labs
+ **[Yuval Ishai](https://scholar.google.com/citations?user=zc920lAAAAAJ&hl=en)**, Technion
+ [**Dima**](https://cs.stanford.edu/~dkogan/)**[ Kogan](https://cs.stanford.edu/~dkogan/)**, Arnac
+ **[Benny Pinkas](http://www.pinkas.net/)**, Bar-Ilan University
+ **[Peter Scholl](https://pascholl.github.io/)**, Aarhus University

### **Additional Information**

**Organizers**: [Carmit Hazay](http://www.eng.biu.ac.il/hazay/), Faculty of Engineering, [Benny Pinkas ](http://www.pinkas.net/), Department of Computer Science and [Mor Weiss](https://engineering.biu.ac.il/en/node/10016), Faculty of Engineering, Bar-Ilan University, Israel.

**Where**: Due to the COVID pandemic, the school will be held online via Zoom.

**When**: Sunday, January 23, 2022 to Wednesday, January 26, 2022

**Registration**: Participation is limited to registered users and is free. Only those who have applied to the school and have been confirmed by the organizers can be considered registered and receive updates and lecture links. 

**Please apply by January 20, 2022** at: https://winter-school2022.forms-wizard.biz/

**Travel to Israel**: COVID related travel restrictions can be found at [https://corona.health.gov.il/en/country-status/](https://eur02.safelinks.protection.outlook.com/?url=https%3A%2F%2Fcorona.health.gov.il%2Fen%2Fcountry-status%2F&data=04|01|Yonit.Homburger%40biu.ac.il|bee28a86cb994094fd2208d9ba3cacd9|61234e145b874b67ac198feaa8ba8f12|1|0|637745592028632142|Unknown|TWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D|3000&sdata=Z36zXHcscbe4qlTU5PKtsnzq9VF7Mn5uDLriRveHM3U%3D&reserved=0). Since the identification of the Omicron variant in late November, non-Israeli citizens cannot enter Israel. This travel restriction will be lifted in the next few weeks. You can monitor the situation by checking the web page or by asking us.

**Contact**: For any questions or queries, please send an e-mail to: [winterschool.biu@gmail.com](mailto:winterschool.biu@gmail.com)

### **Program Schedule**

**The detailed schedule for the winter school can be downloaded [here](http://cyber.biu.ac.il/wp-content/uploads/2021/11/BIUCyberWinterSchool2022Program.pdf).**

#### **Sunday, January 23 – FSS + Prio + ORAM**

+ Opening remarks
+ Elette Boyle: Function Secret Sharing – part 1 ([Slides parts 1-3](http://cyber.biu.ac.il/wp-content/uploads/2021/11/FSS-2022-BIU-WinterSchool_Elette.pdf)) ([Video](https://www.youtube.com/watch?v=fAXlOOs2t88))
+ Elette Boyle: Function Secret Sharing – part 2 ([Video](https://www.youtube.com/watch?v=Zm-MUVve2_w))
+ Elette Boyle: Function Secret Sharing – part 3 ([Video](https://www.youtube.com/watch?v=ORBLeo3lB4U&t=9s))
+ Henry Corrigan-Gibbs: Private Analytics Techniques and Applications – part 1 ([Video](https://www.youtube.com/watch?v=1xu-vVQozRo&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=4&t=6s))
+ Henry Corrigan-Gibbs: Private Analytics Techniques and Applications – part 2 ([Video](https://www.youtube.com/watch?v=JP9CNjC2iUo&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=5&t=4s))
+ Gilad Asharov: Oblivious RAM – part 1 ([Slides](http://cyber.biu.ac.il/wp-content/uploads/2021/11/Part1-lowerBoundTreeBased.pdf)) ([Video](https://www.youtube.com/watch?v=2Dhtzyr6KTM&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=6))

**Monday, January 24 – ORAM + VOLE**

+ Gilad Asharov: Oblivious RAM – part 2 ([Slides](http://cyber.biu.ac.il/wp-content/uploads/2021/11/Part2-oblivious-sorts.pdf)) ([Video](https://www.youtube.com/watch?v=913Syx1Q6AQ&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=7&t=3s))
+ Gilad Asharov: Oblivious RAM – part 3 ([Slides](http://cyber.biu.ac.il/wp-content/uploads/2021/11/Part3-OptimalConstruction.pdf)) ([Video](https://www.youtube.com/watch?v=caPHoqZhyuk&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=8&t=992s))
+ Peter Scholl: Vector Oblivious Linear Evaluation – part 1 ([Slides](http://cyber.biu.ac.il/wp-content/uploads/2021/11/Vector_Oblivious_Linear_Evaluation-1.pdf)) ([Video](https://www.youtube.com/watch?v=ZfdXY_oLhSo&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=9&t=9s))
+ Peter Scholl: Vector Oblivious Linear Evaluation – part 2 ([Slides](http://cyber.biu.ac.il/wp-content/uploads/2021/11/Vector_Oblivious_Linear_Evaluation-2.pdf)) ([Video](https://www.youtube.com/watch?v=i0Y6wdOgRR8&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=10&t=4s))

**Tuesday, January 25 – PCG + VOLE + Signatures**

+ Yuval Ishai: Pseudorandom Correlation Generators – part 1 ([Slides parts 1-2](http://cyber.biu.ac.il/wp-content/uploads/2021/11/pcg-Yuval_Ishai.pdf)) ([Video](https://www.youtube.com/watch?v=A2jWB6mlUPE&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=11&t=5s))
+ Yuval Ishai: Pseudorandom Correlation Generators – part 2 ([Video](https://www.youtube.com/watch?v=AkfRu0yYkGU&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=12&t=3s))
+ Dima Kogan: Introduction to Private Information Retrieval  ([Slides Parts 1-2](http://cyber.biu.ac.il/wp-content/uploads/2021/11/PIR_Dima_Kogan.pdf)) ([Video](https://www.youtube.com/watch?v=JBVP3_PmbsI&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=13&t=1s))
+ Dima Kogan: Offline/Online Private Information Retrieval ([Video](https://www.youtube.com/watch?v=lk2Ki5cq_fk&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=14&t=1s))
+ Rosario Gennaro: Threshold Signatures – Discrete Log Based Schemes – part 1 ([Slides parts 1-3](http://cyber.biu.ac.il/wp-content/uploads/2021/11/Threshold_Sinature_Schemes_Rosario_Gennaro.pdf)) ([Video](https://www.youtube.com/watch?v=Tz3-ZBXxraI&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=15&t=1s))
+ Rosario Gennaro: Threshold Signatures – Discrete Log Based Schemes – part 2 ([Video](https://www.youtube.com/watch?v=VRyHg2FjsoI&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=16&t=7s))

**Wednesday, January 26 – PIR + PSI + Signatures** 

+ Benny Pinkas: Private Set Intersection (PSI) – ORPF/Diffie Hellman PSI, and the Apple CSAM Detection System ([Slides](http://cyber.biu.ac.il/wp-content/uploads/2022/01/PSI-talk-1.pdf)) ([Video](https://www.youtube.com/watch?v=1bkaE9RodeQ&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=17&t=1s))
+ Benny Pinkas: Private Set Intersection (PSI) – Malicious Security, and Probability Amplification  ([Slides](http://cyber.biu.ac.il/wp-content/uploads/2021/11/PSI-talk-2-malicious-security.pdf)) ([Video](https://www.youtube.com/watch?v=bNGMvPR563o&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=18&t=3s))
+ Peter Scholl: Silent OT and VOLE from LPN  ([Slides](http://cyber.biu.ac.il/wp-content/uploads/2021/11/pcg-3.pdf)) ([Video](https://www.youtube.com/watch?v=OxXBa-pUwa4&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=19))
+ Peter Scholl: Pseudorandom Correlation Functions from Paillier ([Slides](http://cyber.biu.ac.il/wp-content/uploads/2021/11/pcg-4.pdf)) ([Video](https://www.youtube.com/watch?v=TbUQa-bJAHM&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=20&t=1s))
+ Rosario Gennaro: Threshold Signatures – Discrete Log Based Schemes – part 3 ([Video](https://www.youtube.com/watch?v=shHNvP94IAA&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=21&t=1s))
+ Rosario Gennaro: Threshold Signatures – RSA Signatures ([Slides](http://cyber.biu.ac.il/wp-content/uploads/2022/01/Threshold_Signatures-RSA.pdf)) ([Video](https://www.youtube.com/watch?v=rz78hRliZDA&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=22&t=1s))
+ Rosario Gennaro: Threshold Signatures – Quantum Resistant Schemes ([Slides](http://cyber.biu.ac.il/wp-content/uploads/2021/11/Threshold_Signatures-Quantum-Resistant.pdf)) ([Video](https://www.youtube.com/watch?v=sFiyBaODyUA&list=PL8Vt-7cSFnw1F7bBFws2kWA-7JVFkqKTy&index=23))

 

#### **This winter school is graciously supported by**

The BIU Center for Research in Applied Cryptography and Cyber Security in conjunction with the Israel National Cyber Bureau in the Prime Minister’s Office and the Alter Family.
