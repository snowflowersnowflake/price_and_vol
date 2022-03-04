# price_and_vol

在参数化策略的实现中，控制思想应用在策略中并不是一个新鲜的话题。有学者和卖方研究人员将量化交易比作核工程，以模型和系统支持数据等为核工程系统，以策略信号到交易逻辑执行部分为核武器。虽然这两者在很多方面都大相径庭，但是从系统的非稳定性和对实际工程经验的依赖来说，依然存在许多思想上可迁移的相似性。在核工程系统中有效的局部以及整体到局部的控制方法论是关键，因此在工程控制上颇有造诣的钱学森在理论和实践基础都不完备的早期贡献了诸多核工程和火箭工程应用，在其著作《工程控制论》中**论证了如何用可靠度低的零件组成可靠度高的系统**。

Qian Xuesen contributed many nuclear engineering and rocket engineering applications in the early stage when the theoretical and practical foundation was not complete. 

In his work Cybernetics of Engineering, he demonstrated how to use components with low reliability to form a system with high reliability.

![img1](img1.png)

上图是经典的通用有前馈的PID模型，我们策略的框架本质上也可以抽象为如此的控制系统。D部分相当于前馈系统，如策略在市场中根据传入信号$u(t)$对盘口进行实时的成本计算和下单就是一个典型的前馈系统。A部分就是反馈系统，类似BP网络，在很多参数化策略中，比如根据因子暴露度调节因子在策略中的可投资价值都可以看做一个反馈系统。

So we could make a Parameterization trading strategy like that PID system.

将市场进行微分，并确保策略在每一段区间上盈利。

Differentiate the market and make sure the strategy is profitable on each segment.

![img2](img2.png)
