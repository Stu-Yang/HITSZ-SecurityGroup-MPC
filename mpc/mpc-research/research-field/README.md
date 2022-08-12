# HITSZ安全组MPC团队研究方向

安全多方计算（Secure Multi-Party Computation，MPC）允许多个互不信任的参与方共同计算一个功能函数并各自得到函数计算结果，在这个过程中需要保证各方输入的隐私性和计算结果的正确性。安全多方计算起源于1982年姚期智提出的“百万富翁问题”，自此许多学者针对安全多方计算在理论上的可行性展开了大量的工作。2004年，第一个通用安全多方计算平台Fairplay的诞生拉开了实用安全多方计算的序幕。目前安全多方计算领域主要针对安全多方计算协议的安全性和效率进行研究：在安全性方面，信息论安全的安全多方多方计算协议的通信下界问题一直是理论研究中的开放问题，同时随着研究的深入，更多的安全多方计算协议开始考虑抵抗恶意敌手的攻击，并讨论不诚实大多数的情形；而随着分布式计算的广泛应用，分布式计算任务的安全性成为了关注的热点，并衍生出隐私计算的概念，在隐私计算应用场景下，安全多方计算协议能够保证计算过程中数据的隐私性和计算任务结果的正确性，因此如何设计隐私应用场景下高效的安全多方计算成为了研究热点。

> **不诚实大多数**
> 
> 设有$n$个参与方，其中恶意敌手最多控制$t$个参与方，不诚实大多数指$t \ge n/2$的情形，最极端的情况是$t=n-1$，此时只有一个参与方未被控制。

针对安全多方计算的安全性问题和效率问题，目前安全组MPC团队的研究主要针对于**恶意模型下安全多方计算协议及其在隐私计算场景下的应用**。具体来说，有以下几点：

+ 诚实大多数的恶意安全多方计算研究；
+ 预处理模型下不诚实大多数的恶意安全多方计算研究；
+ 基于安全多方计算的隐私计算协议。

下面，我们基于上述研究方向，分别针对其中的研究问题和研究内容进行阐述。

## 诚实大多数的恶意安全多方计算研究

在恶意模型下的安全多方计算协议中，许多研究主要针对于诚实大多数的情形，此时敌手控制参与方的数量严格小于参与方总数的一半。恶意模型下，敌手可以以任意的行为来破坏协议的执行，若不考虑诚实大多数的条件，很难限制敌手的行为。在诚实大多数的假设下，已经证明可以为任意功能函数构造信息论安全的安全多方计算协议，而且该假设可以极大地提高协议的性能。

目前的研究难点在于在诚实大多数的假设下，如何实现满足更多安全性要求的安全多方计算协议。隐私性和正确性是安全多方计算协议最基本的安全性要求，进一步地，许多场景还要求公平性（若攻击者可以获得输出，那么诚实参与方也可以获得输出）、保证输出交付（所有诚实参与方都可以获得输出）等。为了获得更强的安全性，大量工作关注安全三方计算、安全四方计算等情形，在这些协议中被敌手控制的参与方只有一个，而诚实参与方则超过两个，因此可以利用零知识证明、交叉验证、协议跳转等技术来实现鲁棒的恶意安全协议。

综上所述，诚实大多数假设下，**如何设计更鲁棒、满足更多安全性要求的恶意安全多方计算协议**是主要的方向，要想解决这一问题，可以首先针对小数量参与方（小于7个）的情形进行研究，利用传统的零知识证明、Cut-and-Choose技术，并结合小数量参与方这一特性设计特定技术来实现安全性。

## 预处理模型下不诚实大多数的恶意安全多方计算研究

目前的研究工作还关注不诚实大多数情况下的恶意安全多方计算研究，可以证明，不诚实大多数下的恶意安全协议不能保证输出交付、而且协议需要允许中止等，因此不诚实大多数下的安全多方计算希恶意主要关注带中止安全性（security with abort）。在不诚实大多数的假设下，协议的通信成本非常大，因此许多工作考虑预处理模型，来实现高效的在线阶段。SPDZ类协议是目前十分高效的不诚实大多数的恶意安全多方计算协议，这类协议基于预处理模型，将大量通信和计算移到预处理阶段，然后利用信息论安全的消息认证码来检测是否存在恶意行为，从而保证安全性。值得一提地是，SPDZ类协议即使在诚实参与方只有1个的情况下也能保证协议最基本的安全性。

不过，预处理模型下的恶意安全多方计算协议的通信效率问题仍是一个有待解决的问题，其原因主要在于通用安全多方计算协议分别基于算术电路和布尔电路来进行计算，当计算任务同时包含算术运算和非算术运算时，依靠单一电路的安全多方计算协议无法实现高效计算，而基于混合协议的安全多方计算协议目前还只能抵抗半诚实敌手。在SPDZ类协议中，协议的通信开销来源于算术电路下的乘法和布尔电路下的与门计算，进一步降低这两类运算的通信开销，就必须更好地利用预处理模型中的相关随机性（以及高效地生成相关随机性），设计出可以支持复杂算术运算和非算术运算的高效协议，近些年提出函数秘密共享概念则可以在一定程度上解决该问题。

> **函数秘密共享**
> 
> 函数秘密共享和传统的秘密共享是一个“对偶”的概念，其指将待计算函数分成若干份，作为秘密份额发送到各个参与方，然后分别让各个参与方在本地计算函数的秘密份额。该计算可以高效计算非线性函数，尽管理论结果证明基于函数秘密共享可以计算任意函数，但目前仅有针对比较、指数、激活函数等非线性运算等高效方案。

总得来说，目前主要的研究内容集中于**如何设计预处理模型下，更低通信复杂度、恶意安全的安全多方计算协议**，而这一问题可以针对下面几点进行深入研究：
+ 预处理模型下相关随机性的应用研究
+ 基于函数秘密共享的恶意安全两方计算

## 基于安全多方计算的隐私计算协议

近些年，以隐私集合求交、隐私保护机器学习、隐私保护数据库查询、隐私信息检索为代表的隐私计算应用需求巨大，而安全多方计算协议可以解决分布式计算任务的隐私问题，为隐私计算应用场景提供技术解。基于安全多方计算的隐私计算协议主要针对安全多方计算在隐私保护应用的效率问题和安全性问题进行研究，主要的难点在于平衡协议的安全性和效率。

在半诚实模型下，许多协议已经有了非常好的理论性能，但仍然需要克服实用化过程中存在的问题。目前许多工作集中于如何让协议更好地支持小数运算、复杂算术运算、非线性函数计算等。在这些问题上，基于混合协议的安全多方计算表现出好的性能，需要改进的地方则是基于混合协议范式的协议转换效率，以及协议的安全性。在恶意模型下，大部分实用的安全协议都采用预处理模型，预处理模型下的安全多方计算协议主要的性能开销是在线阶段乘法的通信开销，和预处理阶段相关随机性的生成开销。同样地，这一问题需要针对相关随机性的高效利用和生成进行更加深入的研究。

另外，针对特定应用场景，上述通用安全多方计算协议往往因为忽略应用特性而不能获得更好的性能。因此以应用为中心的安全多方计算协议也是目前的研究热点，其针对实际应用设计具有较高安全性的高效协议，目前涌现的隐私保护机器学习、多服务器隐私信息检索等应用还有许多可以提升的空间。值得一提地，该方向还通常会结合同态加密、联邦学习等技术设计更加切实有效的协议。

基于安全多方计算的隐私计算协议在安全性和效率上都需要与特定应用场景进行适配，未来的研究方向主要有：
+ 基于混合协议的恶意安全多方计算
+ 预处理模型下面向复杂运算的安全多方计算协议
+ 基于同态秘密共享和函数秘密共享的隐私保护数据挖掘
+ 基于函数秘密共享的多服务器隐私信息检索


## 总结

总而言之，无论是安全多方计算的理论还是应用，都一直关注协议的安全性和性能。到目前为止，安全性的理论研究主要集中于恶意模型下的安全多方计算，如何发现和限制恶意行为一直是研究的难点，研究诚实大多数情形下和不诚实大多数情形下的安全多方计算协议意义重大；而性能方面则与实用安全多方计算的发展息息相关，基于安全多方计算的隐私计算协议不仅需要协调好安全性和效率的关系，而且还要特别关注协议的通信开销和计算量，设计低通信复杂度的恶意安全多方计算协议面临巨大的挑战。