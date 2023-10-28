## 安全多方计算开源框架（Library about MPC）

> MPC代码实现可参考[隐私保护机器学习中，应用MPC进行实验碰到的常见问题与解答](https://mp.weixin.qq.com/s/ynnKuPoh2RC4tP_oWHN5Tg)，和[基于安全多方计算的隐私保护机器学习有哪些比较好入门学习的代码？](https://www.zhihu.com/question/559735424)，[多方计算实验中不同网络环境(LAN和WAN)的模拟方法](https://mp.weixin.qq.com/s/iV0wHKw7gDEr92CbeOwIZg)

+ **安全计算原理相关代码**
  + Private Deep Learning with MPC: [A Simple Tutorial from Scratch](https://mortendahl.github.io/2017/04/17/private-deep-learning-with-mpc/)
+ **安全多方计算通用库**
  + [PySyft](https://github.com/OpenMined/PySyft)：Syft是OpenMined的开源库，可在Python中提供安全、隐私的数据技术
    + (2022年10月18日)最新版是v0.6.0
    + 文档见[PySyft’s documentation](https://openmined.github.io/PySyft/)
  + [SyMPC](https://github.com/OpenMined/SyMPC)：SyMPC是一个扩展 PySyft ≥0.3 并支持 SMPC 的库。它允许对加密数据进行计算，并训练和评估神经网络
    + 支持ABY3、Falcon、FSS和SPDZ等协议
  + [SecretFlow隐语](https://github.com/secretflow/secretflow)：SecretFlow 是用于隐私保护数据智能和机器学习的统一框架
  + [ABY](https://github.com/encryptogroup/ABY)：论文[ABY](https://www.ndss-symposium.org/ndss2015/ndss-2015-programme/aby-framework-efficient-mixed-protocol-secure-two-party-computation/)的实现
  + [SecureNN](https://github.com/snwagh/securenn-public)：论文[SecureNN](https://eprint.iacr.org/2018/442)中协议的实现
  + [Piranha](https://github.com/ucbrise/piranha)：Piranha 是一个基于 C++ 的平台，用于以独立于协议的方式在 GPU 上加速安全多方计算 (MPC) 协议参见USENIX 2022论文[Piranha: A GPU Platform for Secure Computation](https://eprint.iacr.org/2022/892)
  + [PrimiHub](https://github.com/primihub/primihub)：PrimiHub是一个支持多方计算、联邦学习、隐私求交(PSI)、隐私查询(PIR)特性的平台，支持数据源接入、数据消费、接入应用、语法、语义、安全协议多方面的扩展。
+ **函数秘密共享库**
  + [AriaNN](https://github.com/LaRiffle/ariann)：论文[AriaNN](https://petsymposium.org/popets/2022/popets-2022-0015.php)的开源代码，同时其利用了[PySyft分支](https://github.com/OpenMined/PySyft/tree/a73b13aa84a8a9ad0923d87ff1b6c8c2facdeaa6)
    + AriaNN使用了PySyft 0.2.0版本，这一点从AiraNN的[main.py](https://github.com/LaRiffle/ariann/blob/main/main.py)文件就可以看出，其中`hook = sy.TorchHook(torch)`（line 35）使用了`TorchHook()`方法，该方法在v0.3.0及以上版本不再出现。
  + [Sycret](https://github.com/OpenMined/sycret)：用于函数秘密共享的Python库，具有使用AES-NI硬件加速的高效Rust后端。它在PySyft中用于AriaNN
    + 文档：[Sycret documentation](https://openmined.github.io/sycret/)
    + 说明：同该开源库是和PySyft集成的，Python包是从PySyft调用的，见[PySyft分支](https://github.com/OpenMined/PySyft/blob/49b1d03de1ba82c4043dc63772ed0ebba7aad6c7)
+ **联邦学习框架**
  + [FATE](https://github.com/FederatedAI/FATE)：FATE（Federated AI Technology Enabler）是全球首个工业级联邦学习开源框架，使企业和机构能够在数据上进行协作，同时保护数据安全和隐私。
  + [CryptoFL](https://github.com/Ye-D/CryptoFL/tree/main)：联邦学习的加密安全聚合
