# Covert Security 隐蔽安全性

## 1. 隐蔽安全介绍

在安全多方计算（Secure Multi-Party Computation, MPC）中，根据敌手的能力，通常将敌手划分为以下几类：
+ **半诚实敌手（Semi-Honest Adversaries）**：在半诚实敌手模型中，腐化参与方也会遵循协议流程执行协议，但敌手能够获取所有孵化参与方的内部状态（包括所有已接收消息的记录），并试图利用这些信息来获取本应保密的信息
+ **恶意敌手（Malicious Adversaries）**：在恶意敌手模型中，腐化参与方会根据敌方的指令任意地偏离协议流程
+ **隐蔽敌手（Covert Adversaries）**：在隐蔽敌手模型中，敌手可能会尝试破坏协议执行，但如果尝试攻击，会以一定的概率被检测到（例如，有80%的概率检测到恶意行为，该概率可根据具体应用进行调整）。注意，与恶意敌手模型不同，如果敌手的恶意行为未被检测到，则其可能成功作弊（例如，获取诚实方的输入）。

## 2. 隐蔽安全相关论文

+ :triangular_flag_on_post:***[AL07] Security Against Covert Adversaries: Efficient Protocols for Realistic Adversaries***
  + 提出隐蔽安全概念
  + 发表在TCC 2027, JoC 2010，论文链接见[IACR eprint](https://eprint.iacr.org/2007/060)
+ ***[GMS08] Efficient Two Party and Multi Party Computation Against Covert Adversaries***
  + 提出不诚实大多数隐蔽安全两方和多方计算协议，多方计算协议通过修改BMR Garbled Circuits (GC) 协议获得
  + 发表在EuroCrypt 2008，论文链接见[IACR](https://iacr.org/archive/eurocrypt2008/49650287/49650287.pdf), [Slides](https://www.iacr.org/conferences/eurocrypt2008/sessions/paymanMohosell_20080416.pdf)
