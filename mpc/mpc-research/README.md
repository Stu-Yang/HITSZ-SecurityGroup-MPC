# 安全多方计算课题研究

安全多方计算理论研究和实践应用研究主要针对协议的效率和安全性进行优化和提高。

## 索引

+ [paper-reading](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/paper-reading)：介绍如何查找、阅读论文
+ [research-field](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/research-field)：安全组目前的研究方向
+ [collection&miscellaneous](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/collection%26miscellaneous)：包括了以下各个主题的论文，以及一些重要且有价值的论文
  + [mpc-survery](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/mpc-survery)：安全多方计算领域的综述，带你了解安全多方计算的研究现状和趋势
  + [privacy-preserving-data-mining](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/privacy-preserving-data-mining)：介绍隐私保护数据挖掘应用
  + [malicious-mpc](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/malicious-mpc)：介绍恶意模型下的安全多方计算协议
  + [mpc-with-preprocessing](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/mpc-with-preprocessing)：介绍预处理模型下的安全多方计算协议
  + [function-secret-sharing](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/function-secret-sharing)：介绍函数秘密共享，以及基于函数秘密共享实现安全两方计算协议。
  + [homomorphic-secret-sharing](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/homomorphic-secret-sharing)：介绍同态秘密共享，以及基于同态秘密共享的安全计算协议
+ [conferences&journals](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/conferences%26journals)：介绍三大密码学会、四大安全顶会等重要会议和期刊中MPC相关的论文
  + [Eurocrypt 2022](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/conferences%26journals/Eurocrypt-2022)
  + [S&P 2022](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/conferences%26journals/S&P-2022)
  + [NDSS 2022](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/conferences%26journals/NDSS-2022)
  + [AsicaCCS 2022](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/conferences%26journals/AsiaCCS-2022)

## 如何开始研究生涯？
+ 可以看看[如何开始研究生生涯?](http://muchong.com/t-14899063-1)体会一下
+ 研究生涯的几个阶段
  + Assistance
  + Dependence
  + Independence
  + Leadership
+ 选择研究方向：MPC组目前的研究方向参见[HITSZ安全组MPC团队研究方向](https://github.com/Stu-Yang/HITSZ-SecurityGroup-MPC/tree/main/mpc/mpc-research/research-field)

## 如何做研究？
+ 科学问题：如何找到自己的研究方向
  + 多读论文，一般来说大方向50-100篇，小领域30篇左右
  + 如何发现科学问题：可以参考[如何提出科学问题?](https://news.sciencenet.cn/sbhtmlnews/2015/1/295864.shtm)
+ 如何开始做研究？
  + 找到自己的研究课题：看文献找到待解决的问题
  + 针对这个问题进行调研（该问题至少要有两个关键词，比如我想进行“预处理模型下MPC协议相关随机性研究”包括两个关键词**预处理模型下**、**相关随机性**），了解该领域的研究现状和未来的趋势：
    + 首先，找到领域内所有的相关论文（如果这时候找到了一篇比较新的符合自己主题的综述，那就可以针对该综述进行研究，并加以补充即可）
    + 分析这些论文的逻辑关系并进行分类，厘清该问题的技术路线，并掌握现有工作的研究状态（例如预处理模型下MPC协议有几种技术可以实现，每条技术路线有哪些文章，研究到哪个阶段了？）
    + 总结和分析这些论文，或者厘清该论文有实现和没有实现的技术点，尝试找到有待解决的问题（例如现有工作只实现了半诚实模型下的预处理模型下MPC协议）
    + 如果还是不懂，不要焦虑，看看毕导的[学术菜鸡如何速成3000字文献综述？论文再不写就完犊子了！](https://mp.weixin.qq.com/s/32zJ2WS6I4uKOZgNVPe-vw)，看完不一定会写，但是看完会开心一点也好
  + 针对这些问题提出自己的研究内容和研究计划，形成自己的研究课题，主要包括以下几部分内容
    + 研究对象：你想解决什么问题？
    + 研究目的和意义：研究该问题的意义？
    + 研究现状：前人研究现状和遗留问题。
    + 研究方案：确定研究方法和研究安排。
+ 如何推动课题研究：有了研究课题之后，便可以开展相关研究了，记住：**我们所研究的80%的问题都可以在论文中找到答案！**
  + 将自己的研究内容细分成一个一个子任务，子任务可以不断往下细分，直到你自己可以直接解决
  + 如何划分成子任务？：针对研究内容，不断问自己：“是什么？为什么？怎么办？”，一定要合理地有逻辑地将自己的研究任务转化为更小的子模块。



