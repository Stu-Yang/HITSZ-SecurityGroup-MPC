## 安全多方计算相关库（Library about MPC）


+ 安全多方计算通用库
  + [PySyft](https://github.com/OpenMined/PySyft)：Syft是OpenMined的开源库，可在Python中提供安全、隐私的数据技术
  + [SyMPC](https://github.com/OpenMined/SyMPC)：SyMPC是一个扩展 PySyft ≥0.3 并支持 SMPC 的库。它允许对加密数据进行计算，并训练和评估神经网络
  + [SecretFlow隐语](https://github.com/secretflow/secretflow)：SecretFlow 是用于隐私保护数据智能和机器学习的统一框架
  + [ABY](https://github.com/encryptogroup/ABY)：论文[ABY](https://www.ndss-symposium.org/ndss2015/ndss-2015-programme/aby-framework-efficient-mixed-protocol-secure-two-party-computation/)的实现
  + [SecureNN](https://github.com/snwagh/securenn-public)：论文[SecureNN](https://eprint.iacr.org/2018/442)中协议的实现
  + [Piranha](https://github.com/ucbrise/piranha)：Piranha 是一个基于 C++ 的平台，用于以独立于协议的方式在 GPU 上加速安全多方计算 (MPC) 协议参见USENIX 2022论文[Piranha: A GPU Platform for Secure Computation](https://eprint.iacr.org/2022/892)
+ 函数秘密共享库
  + [AriaNN](https://github.com/LaRiffle/ariann)：论文[AriaNN](https://petsymposium.org/popets/2022/popets-2022-0015.php)的开源代码，同时其利用了[PySyft分支](https://github.com/OpenMined/PySyft/tree/a73b13aa84a8a9ad0923d87ff1b6c8c2facdeaa6)
  + [Sycret](https://github.com/OpenMined/sycret)：用于函数秘密共享的Python库，具有使用AES-NI硬件加速的高效Rust后端。它在PySyft中用于AriaNN
    + 文档[Sycret documentation](https://openmined.github.io/sycret/)
    + 说明：同该开源库是和PySyft集成的，Python包是从PySyft调用的，见[PySyft分支](https://github.com/OpenMined/PySyft/blob/49b1d03de1ba82c4043dc63772ed0ebba7aad6c7)
