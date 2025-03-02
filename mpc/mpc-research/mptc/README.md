# Multi-Party Threshold Cryptography (MPTC)

> [NIST Computer Security Resource Center/Multi-Party Threshold Cryptography (MPTC)](https://csrc.nist.gov/projects/threshold-cryptography)

多方门限密码学（Multi-Party Threshold Cryptography, MPTC）项目由美国国家标准及技术研究所（National Institute of Standards and Technology，NIST）发起，旨在开发门限密码学方案。该方案通过将密钥分割成多个部分并分配给不同的参与者来分散信任，因此即使某些参与者被攻击或失效，整体安全性依然能保持不受影响。在方案中，密码操作（如签名或加密）通过多方计算执行，而无需重建密钥，这种方法通过避免单点故障来提高安全性。该项目的目标是为各种密码学原语（如密钥生成、签名和加密）应用这些门限方案提供指导和标准。

截至目前，NIST在MPTC项目方面发布了以下几份报告：​
+ [NIST IR 8214](https://csrc.nist.gov/pubs/ir/8214/final)：​这份报告探讨了门限密码学原语标准化和验证过程中的挑战与机遇。​
+ [NIST IR 8214A](https://csrc.nist.gov/pubs/ir/8214/a/final)：​该报告提供了NIST在门限方案标准化方面的路线图，定义了门限方案的标准化目标和方法。​
+ [NIST IR 8214B](https://csrc.nist.gov/pubs/ir/8214/b/ipd)：​这份报告分析了门限EdDSA/Schnorr签名方案的技术细节，讨论了相关协议方法和自适应安全性的解决方案。​
+ [NIST IR 8214C](https://csrc.nist.gov/pubs/ir/8214/c/ipd)：​该报告发布了对多方门限方案的公开征集，旨在收集公众对门限方案的反馈，以支持NIST制定未来的建议和指南。​

这些报告共同推进了NIST在多方门限密码学领域的标准化和研究工作。 
