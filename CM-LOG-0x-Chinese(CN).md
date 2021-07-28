#CM-LOG-0x-Chinese.md
[中文] 社区日志
================
**[中文] 社区日志 0x1**
----------------------------------

我将分两部分回答[Gimre](https://twitter.com/NCOSIGIMCITYNRE)、[Hatchet](https://twitter.com/0x6861746366574)和[Jaguar](https://twitter.com/Jaguar0625)进行的社区问答，这是第一个回答。

*关于超级节点计划*

01：超级节点计划怎么了？延迟的原因是什么？投票费延迟怎么办？ **

* 在 Talknomics 设计的早期阶段，曾有过模拟前所未有的网络价格和活动的假设，但考虑到这一点以及新子链概念的方向、网络带来的奖励系统和经济，我们正在重新审视是否需要调整以平衡身体安全。作为重建代币和机制设计的一部分，超级节点计划和投票奖励都在审查中。
分析完成后将立即提供详细报告，但请同时等待新的薪酬结构和计划。

02：网络中的某些用户是否与其他普通用户区别对待？如果是这样，为什么？ **

* 是的，NGL 和大约 30-40 个大型持有者（鲸鱼）超级节点之间存在私人关系。最初它是通知大业主项目延误的临时渠道，但它仍然是无意的。两个人已经离开了，Symbol 上线后就成了一个多余的频道。与我们[透明](https://www.discord.gg/xymcity)的指导原则相反，我们现在将[Discord](https://www.discord.gg/xymcity)用于一切。

 **关于技术**
 --------------------------------
 
03：Hatchet最近经常提到私有和公有的交叉链，但是他们具体的前景和对XEM/XYM交叉链的用处的想法是什么？请告诉我们。 **

* 关于[这里](https://docs.symbolplatform.com/handbook/index-ja.html)，请参考。我们相信子链可以提供一种更简洁的方式来处理条件网络。

04：为什么Symbol不需要智能合约？ **

* Symbol 也有[智能合约](https://www.fon.hum.uva.nl/rob/Courses/InformationInSpeech/CDROM/Literature/LOTwinterschool2006/szabo.best.vwh.net/smart_contracts_2.html)的概念，就像在比特币中一样。具体来说，Symbol 不具备的主要是循环中的图灵完备性，从而避免了事务处理中的无限循环（=垃圾邮件）。以太坊对此的解决方案是对每次操作（称为gas）收取额外费用。您执行的语句越多，“佣金”就越高。

* 具有非图灵完备性的完整区块链具有资源使用可预测、分析能力增强、域使用集中等优点。我们正在积极研究 Symbol 程序的可能性，但我们还没有找到具体的路径。但也许你可以在中间找到一个[解决方案](https://www.gwern.net/Turing-complete)。

05：您认为 Symbol 的 Layer 2 目标与以太坊 2.0 有何不同？ **

* 例如，它可能类似于[zk-Rollups](https://docs.ethhub.io/ethereum-roadmap/layer-2-scaling/zk-rollups/)或 STARK 电路方法。然而，在研究阶段确定结构和实施差异还为时过早。

06：你是否考虑引入多项式承诺/凯特（KZT）承诺，让基于默克尔树的状态证明更简单？ **

* [Verkle Trees](https://math.mit.edu/research/highschool/primes/materials/2018/Kuszmaul.pdf)（紧随其后的是 Kate Commitment）是我们与零知识证明、zk-STARKs 和 zk-Rollups 一起研究的内容之一。我还没有做出具体的决定，但是当我考虑扩大主链时，我认为这是三重结构的自然过程。
对于 Kate Commitment，[Aztec](https://aztec.network/)的 om Walton-Pocock 编写了一本很好的[入门](https://hackmd.io/@tompocock/Hk2A7BD6U)书。

07：您如何看待以太坊虚拟机兼容？ **

* 我仍然不确定与以太坊虚拟机兼容的好处是什么，但为什么不将以太坊用于与[以太坊虚拟机](https://ethereum.org/en/developers/docs/evm/)相关的任何事情？如果您采取直接的方法，您可能希望在 Ethereum 和 Symbol 之间使用专用的子链来保持它们的联系。

* 重要的是要了解以太坊概念不会直接转换为 Symbol。以太坊虚拟机是一个图灵完备的虚拟机。还有其他用于加密网络的虚拟机，例如[Rusk](https://ethereum.org/en/developers/docs/evm/)和[NeoVM](https://docs.neo.org/docs/en-us/basic/technology/neovm.html)。此外，其他[eBPF](https://www.infoq.com/articles/gentle-linux-ebpf-introduction/)也讨论过类似的可能性。没有将虚拟机引入 Symbol 的具体计划，但研究正在进行中。

08：NEM3.0会发布吗？ **

* 不会

09：您想为 XEM / XYM 替换制作 DEX 吗？ **

* XEM / XYM 交易所是流动性提供者（交易所等）的工作。但是，有计划通过将 NIS1 作为子链引入 Symbol 来引入此功能。一个短期的解决方案（我们也会建立相应的市场）是使用其他流动性网络，例如[Thorchain](https://thorchain.org/)和[Sushiswap](https://sushi.com/)。

10：为什么其他链不能跨链交换到Symbol并连接？ **

* 协议开发人员很少负责与其他网络实现跨链功能。如果你想考虑跨链交换，请先参考这个文档。以太坊、比特币及其相关分叉 SHA256d 可以进行互换。

11：Apostille 特征是一个非常重要的特征。 Symbol Wallet 何时会实施 Apostille 功能？ **

* 如果您有功能请求，请在[此处](https://github.com/symbol/symbol-desktop-wallet/issues)添加。我们是 Apostille 功能的粉丝，但它可能并不那么重要，因为还没有人提出请求。

12：你为什么不多谈技术？ **

* 开发者和研究人员可以在此[Discord](https://discord.gg/xymcity)上加入项目和研究频道。

13：以后是否可以在我的钱包中添加分层确认功能？ **

* 请在[此处](https://github.com/symbol/symbol-desktop-wallet/issues)提出请求。

14：是否已经有一种在 Symbol 上创建和存储 NFT 的标准方法？另外，你什么时候计划或什么时候做？还是 Symbol 开发人员现在必须自己做和实现它？ **

* 目前，当由社区创建时，我们已经确认他们中的大多数人的供应量为 1，并在其元数据中发布了带有 IPFS 主题标签的马赛克。未来有计划扩展马赛克功能，以支持特定供应和单个单元的特定元数据，但没有明确的时间表。

15：mijin 我想问一下核心开发对私链的看法。 **

* 我无法回答这个问题，因为我知道 Tech Bureau 并且没有参与该私有链中发生的事情。

16：是否可以在 Symbol 区块链上发行代币？ **

* 可以。 Symbol 令牌（类似于 NIS1）被称为马赛克(Mosaic)，但这种命名在未来可能会改变。

17：有没有更渐进的节点发布方式？ Bootstrap 版本在服务器版本之后，Bootstrap 更新在服务器更新之后发布。明确区分它和主网/测试网版本。特别是当它作为服务器 1.0.1.0 的更新出现时，当 Bootstrap 版本为 1.0.6 时，很难判断您是否正在运行正确的版本。 **

* Bootstrap 工具的应用速度比 Catapult 快，并遵循[语义版本控制](https://semver.org/)。 Catapult 也是一个独立的软件，它根据通用版本方法对主网和测试网版本进行了明确区分。

* 自 1.0.0.0 版本以来测试网 / 主网的版本定义：

![](https://i.imgur.com/qbMyCxd.png)

* 请注意，testnet 并不总是独立构建的，如果没有新功能要测试，testnet 将构建与主网相同的。

18：你什么时候会做一个工具，让普通大众可以轻松使用加密货币？ **

* 通常，该工具将是一个钱包。您可以[在此处](https://github.com/symbol/symbol-desktop-wallet/issues)请求功能，也可以在[Discord](https://discord.gg/xymcity)上参与讨论和钱包开发。

19：我想知道我是否能够在 XYM 应用程序中看到 NFT**

* 请从[这里](https://github.com/symbol/symbol-desktop-wallet/issues)请求功能。

20：在我迷上 NEM 之前，我首先迷上了 NXT。原因是NXT的技术创新。 NEM 团队（开发、NGL 等）试图阻止 NEM 变得像 NXT 一样吗？ **

* 我们不打算放弃 Symbol 或 NIS1。但是，每个参与者都应该为这条链做出贡献并取得整体成功。协议开发人员和他们的社区之间有明确的潜在承诺。如果我们不打算遵守这一基本承诺，我们就不会进行新的重组努力。

**关于 Talknomics 和市场价格**
---------------------------------------------

21：我们可以讨论与谈话经济学和抵押模型的进一步改进吗？例如，DOT 对普通持有者（不是主节点）的回报率比 XYM 高得多。 DOT 产生 12% 的 APY，但由于波动，Symbol 的 APY 难以估计。我认为这是由于Talknomics的设计，但不是每个人都选择DOT而不是XYM吗？ **

* 不可能比较具有不同目的的两种代币的谈话经济学。我们的谈话经济学是一个鼓励在网络上进行特定操作的框架，例如旋转新块和参与节点操作。随着网络的发展，加入网络的盈利能力也在增长。它旨在调整反馈回路，而不是随心所欲的进行调整。
（事实上，我们经常想在不过度给予作为[经济补偿](https://drive.google.com/file/d/1pwt-EdnjhDLc_Mi2ydHus0_Cm14rs1Aq/view)方面进行调整。）

* 然而，既然链已经开始并作为一个团队开始，我们也在审查talknomics的设计。

* 虽然很难估计，但下表是当一个持有 100,000 XYM 的账户在Symbol发布后立即开始收获时的估计。
![](https://i.imgur.com/GWRYGvb.png)

* 0.95 因子 = 本地收获 -（95% 费用 | 5% 网络费用） 0.7 因子 = 委托收获（70% 费用 | 25% 委托费用 | 5% 网络费用）


* 对于本地收割机，第一年 APY 为 3.2%（预期下限估计）至 14.5%（预期上限估计），对于委托收割机，APY 为 2.3%（预期下限估计）至 10%（预期上限估计）（估计）。
在当前的网络条件下，已经观察到接近预期上限估计的结果。

22：我推荐使用Symbol的公链，但是一些日本工程师已经想出了一种将数据存储在链上的方法。如果这被广泛使用并且公共区块链过载并且系统关闭，那么支持系统是什么？如果你能说不会掉，请告诉我原因。 **

* 一直可以“链上”存储数据（即镶嵌元数据字段在那里）。关键是它在经济上是否可行，是否实用。但是，我们期待看到日本社区将使用“Symbol”进行什么样的工作。如果您遇到任何问题，我们很乐意与社区合作，为您的节点快速分类和发布补丁（有关最新信息，请加入[Discord](https://www.discord.gg/xymcity)或关注我们的[Twitter](https://www.twitter.com/NEMOfficial) 帐户）。

23：Gimre 曾经说过，“我对市场价格不感兴趣”，但其他核心对此有何看法？我认为市场价格是支持生态系统的最重要因素之一，例如 NGL 员工的工资和工程师的捐款。 **

* 市场价格反映了网络的需求。 [正如](https://docs.symbolplatform.com/handbook/index-ja.html)我在这里所写的[那样](https://docs.symbolplatform.com/handbook/index-ja.html)，发展网络取决于生态系统中的每个人。在链上实现新功能是我们的工作（而不是由特定的人组成的团队），而由用户使用链上的应用程序并找到新的和创造性的方法来利用此功能的增加。如果您认为价格是您的网络成功的关键之一，请加入我们并帮助使其更实用（或Symbol的地名）。

24：你们有什么措施提高市场价格吗？托管代币供应是可能的。团队可以通过第三方管理市场价格。它还可能导致通货紧缩和通货膨胀。聘请第三方同意并提供帮助如何？法规和合规性是障碍吗？ **

由于列出了多个问题，为方便起见，我将分别回答。
* Q:*你们有什么措施提高市场价格吗？ *
* A:见上文“问题23”，“市场价格反映网络需求”托管代币供应是可能的,市场决定供求关系,不是我们。

* Q:*能够产生通货紧缩和通货膨胀的状态和球队是供应链相关*

* A:控制通缩和通胀并不是在市场的影响下“反复无常”。我们的通货膨胀率非常小，在区块 31410299 可以忽略不计,如上所述，我们正在审查谈话经济学。

* Q:*为什么为了调整市场价格，或者说没有聘请第三方*

* A:这不是协议开发团队的责任，也不是生态系统中的道德问题。您所关注的市场是您网络健康和功能的直接反映，您可以在“[退出和语音](https://en.wikipedia.org/wiki/Exit,_Voice,_and_Loyalty)”的帮助下自由加入或离开加密网络。它不符合该方法的机制的存在，并且可以自由地抱怨、抱怨、改变并尝试修复或改进。
如果您正在谈论做市（缩小交易中的点差），您可以使用[Hummingbot](https://docs.hummingbot.io/miner/liquidity-mining/current-rewards&terms/) 之类的程序自己完成。

**关于教育**
-----------------------------------------------

25：我认为提供一些基本指南和简单的编程练习来帮助您开始使用 Symbol 是很棒的。有很多可用的文档，但不适合初学者。团队中有人可以解决这个问题吗？ **

* [我们](https://github.com/symbol/symbol-docs/issues)建议您在[此处](https://github.com/symbol/symbol-docs/issues)请求特定功能。我们也鼓励社区参与[指南](https://docs.symbolplatform.com/guides/index.html)的创建。这里已经有一些很好的资源，技术文档中有一些[指南](https://docs.symbolplatform.com/guides/index.html)可以帮助您入门。

26：我想问你是否打算创建一个教程来向你展示如何存入你的 Xym 钱包。我在几个地方搜索了这方面的信息，但找不到。 **

* 本[指南](https://docs.symbolplatform.com/guides/transfer/sending-a-transfer-transaction.html)介绍了如何使用 CLI、SDK 和钱包执行此操作。

**关于透明度**
---------------------------------

27：承诺的AMA在哪里？ **

* 这里是。你现在正在阅读它。

28：请告诉我们XYM在币安(Binance)上币的情况。 **

* 一般来说，项目团队无法控制币在交易所上市的时间。准备就绪后，Binance 有信心将上架 XYM。

29：核心开发者为何隐藏？有人说这对信用不利。 **

* 问问中本聪你的想法。此外，匿名是项目负责人的一个共同特征——CryptoNote 中的[Nicolas van Saberhagen](https://en.wikipedia.org/wiki/CryptoNote)；Sushi 中的[Chef Nomi](https://coinmarketcap.com/alexandria/people/chef-nomi)和[0x Maki](https://twitter.com/0xMaki)。
来自 [Mimble Wimble 的 Tom Elvis Jedusor](来自 Mimble Wimble 的 Tom Elvis Jedusor)。今天，有些风险投资公司完全由匿名合伙人组成。还有一些[风险投资公司支持匿名创始人](https://www.egirlcapital.com/)。有关于[假名经济的力量的讲座](https://www.youtube.com/watch?v=urtXRg9Nl3k)，[有些人甚至认为匿名会增加你行为的可信度](https://twitter.com/MikeAbundo/status/1342258232610312192?s=20)。

* 总之，合法性可以通过产出来衡量，而不是身份。我们认为这不会对项目产生负面影响。


**关于治理**
------------------------------

30：我需要一个治理令牌来对这个问题进行投票。 **

* [治理代币](https://insights.deribit.com/market-research/why-i-have-changed-my-mind-on-tokens/)有助于引导程序的流动性，您同意用户是寻找自己声音的重要信号机制，但治理代币已经存在。这称为 XYM。如果您正在阅读本文，您可能会拥有它。
* 我们目前正在寻找为 XYM 提供治理目标的方法。其中之一是引入 Quadratic Funding 平台，该平台允许社区资助被认为对网络最有益的公共产品。
* 了解与 Symbol 相关的治理含义也很重要（每个加密网络都有自己的规则）。没有硬性规定，我们和社区一起建立，但有时我们不能依靠群众的智慧。一个很好的例子是高级技术决策，例如使用哪条 BLS 曲线。
* 我们同意透明度不是项目历史上最好的，并且正在努力减轻它。例如，发布[类似于 ETC 的透明报告](https://etccooperative.org/ETC-Coop-Board-Package-January-February-2021.pdf)，详细说明支出。我们取得的另一项进步是开放与 Discord 的所有内部沟通，并使我们的手册可公开访问和开源。

31：等级制度和权力下放的概念如何结合在一起？ **

* 需要一个更传统的指挥和控制层次结构来克服要发射的最后一个里程碑。然而，传统的分层与权力下放的概念格格不入。这就是为什么我们要发展为遵循[Flatland 模式](https://www.researchgate.net/publication/282395703_Valve's_Way)的组织。

32：有多少资金可用于开发 Symbol 和 NIS1？ **

* 所有这些信息都可以在区块链上找到。 2020年，核心资金全部转移至信托。该信托包括 16 亿 XYM 和 28 亿 XEM。 （按今天的价格计算为 6.3 亿美元）。 XYM 比 XEM 少 12 亿，因为它用于 Symbol 的区块奖励。

33：NEM的核心团队是一个什么样的群体，资金比较大？
在日本，也有观点认为，风险之一是核心团队资金庞大。 **

* 与 EOS 和以太坊基金会等相比，资金池相对较小。所有资金目前都存储在受多重签名帐户保护的信托中。他们的角色和使命是“支持和发展 NEM 生态系统及其相关的区块链、本地货币和技术”。目前，这意味着 Symbol 和 NIS1 的开发。


**关于营销/品牌/合作伙伴关系**
------------------------------------

34：我想知道未来的营销计划。 **

* [正如此处](https://docs.symbolplatform.com/handbook/index-ja.html)所解释的，社区及其大使有[责任](https://docs.symbolplatform.com/handbook/index-ja.html)提高对该项目的认识并发展生态系统。当社区建立了一个非凡的项目时，媒体自然会关注它并伸手谈论它。除此之外，一些团队成员在社交媒体上都非常活跃，出现在播客、脱口秀甚至电视上。

35：为什么国外不讨论NEM和Symbol？ **

* 我们毫无头绪。

36：为什么这个品牌问题几个月前没有消失？您是如何决定不按照建议创建 Symbol 社交媒体帐户的？ **


* 我们不能代表 NEM 集团及其前身。但是，社区现在正在通过 Twitter 和 Discord 发表评论。我们鼓励您参与这些讨论。我们同意我们的内部和外部社区、我们的业务合作伙伴和合作伙伴对“NEM”存在混淆。我们倾听讨论并思考最好的方法。

37：你想模仿卡尔达诺(ADA)并发布技术更新吗？ ** https://twitter.com/cardano_updates

* Twitter 机器人发布的 GitHub 统计数据毫无意义。我希望您直接查看我们的 GitHub。

38：是否可以创建每周一次的英文技术更新？我们的 NEM HUB 版主可以翻译成他们的母语。 （除了最常用的8种语言外，还涵盖日语和其他几种语言）NEM HUB还可以提供即时聊天室（Messenger）和参与直播，您可以在线播放常规的NEM节目。你觉得这个想法怎么样？ **


* 社区已经开始将流行的推文、博客和帖子翻译成他们的 Twitter 帐户和[社区运营的博客](https://symbolblog.com/)。我们所有的工作都是在 Discord 和 GitHub 上完成的，因此社区可以就技术更新进行协作。

39：很多人还是觉得XEM为主，XYM是加分，那为什么不把NEM的标志改成Symbol的标志呢？ **

* 参见问题 #36 的答案。

40：我认为我们应该积极推动NEM（NIS1）和Symbol的差异和未来潜力。 **

* 如[手册](https://docs.symbolplatform.com/handbook/index-ja.html)所述，NIS1 是 Symbol 的子链。

41：您未来的营销前景如何？ **

* 不幸的是，我没有水晶球。

42：在日本，加密资产仍被视为一种投资，但如果我们推出呼吁Symbol实力的电视广告和网络广告，区块链，并从现在开始在日本传播区块链=Symbol的形象。我想我绝对可以击败以太坊。我期待着一个大胆的营销策略。 **


* 这不是一个问题，但感谢您的热情和建议。

43：我想让你多谈谈 DeFi。 **


* 是的。关注我们的 Twitter 帐户 [1](https://twitter.com/Jaguar0625) '[2](https://twitter.com/0x6861746366574) '[3](https://twitter.com/NCOSIGIMCITYNRE) 或加入[Discord](https://discord.gg/xymcity)，以获取有关 DeFi 主题的更多想法、意见和研究。

44：你是否与其他区块链社区互动？他们对NEM感兴趣吗？ **

* 是的。在我们三个人中，[Hatchet](https://twitter.com/0x6861746366574)是互动最多的。总的来说，其他区块链项目对 NEM 的兴趣不大。通过参与加密货币中使用的技术（例如 zk-SNARK 和 zk-Rollups）的研究和开发，并开始更多地谈论 Symbol 的机制设计和架构。我认为随着这个，兴趣会增加。

45：你认为日本对待新经济的方法的好处是什么？另外，您认为应该怎么做才能将其传播到日本以外？ **

* 我们喜欢日本社区的热情和实验。我想在世界各地看到更多这样的东西。除此之外，我们相信我们可以通过使用 Symbol 增加思想领导力、优秀文章、创新研究和产品来提高对该项目的认识。

46：自 Symbol 推出以来已经三个多月了 我们预期的许多交易所尚未上市。为什么？ **

* 我们不知道。交易所有一个内部流程，可以根据市场需求优先考虑代币。 Binance 提供了一些上市[指南](https://www.binance.com/en/blog/421499824684902218/Binance-Listing-Tips-from-CZ)来帮助完成此过程，但不能保证您的代币会被上市。币安相信，一旦准备好，它就会上架 XYM。

47：我想知道NEM是否考虑进入lq区块链的NFT领域。它可以作为 XYM Unstake 和 Stake Stakin Special 的要求实施吗？ **

* 不，我不是在想。

48：Nem 和 Symbol 用例没有增加，所以新闻中根本没有谈论它。你不认为你发布新闻的计划有问题吗？ **

* 不，我们强烈反对“以新闻换新闻”。这是一个历史上反复出现的问题，对 NEM 已变得有害而不是有益。推动 Symbol 的采用取决于我们所有人，而不仅仅是协议团队。如果您想查看更多新闻和媒体活动，请加入我们。在本地聚会上谈论 Symbol，在会议上谈论共识算法，在链上构建创新用例，并成为早期的先驱之一。如果您认为缺少新闻是个问题，请参与解决。

49：我希望 Symbol 传播得更快。 **

* 我们也想这样做。但好事需要时间。
您想如何实现这一目标？

50：聘请会说英语以外的语言的影响者（例如YouTuber）以加强公司内的沟通是否有任何障碍？ **

* 我们不会付钱给有影响力的人、名人或媒体，以让 Symbol 获得错误的荣誉。
这不符合我们的道德规范。我们希望系统地发展我们的社区，并因其实用性和创新性而获得全世界的关注。

51：您打算如何改善和加强NEM公司与新兴技术国家之间的交流？ **

* 在比特币和以太坊中，“如果你建造它，他们就会来”的口头禅已被证明是正确的。
最好的方法是改进或增强内置于链中的 Symbol 的功能。

52：什么是NEM公司？ **

* 没有明确的框架，但有效利用NIS1和Symbol的，是像公司这样的组织。
