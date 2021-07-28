#CM-LOG-0x-Chinese.md
[中文] 社區日誌
================
**[中文] 社區日誌 0x1**
----------------------------------

我將分兩部分回答[Gimre](https://twitter.com/NCOSIGIMCITYNRE)、[Hatchet](https://twitter.com/0x6861746366574)和[Jaguar](https://twitter.com/Jaguar0625)進行的社區問答，這是第一個回答。

*關於超級節點計劃*

**01：超級節點計劃怎麼了？延遲的原因是什麼？投票費延遲怎麼辦？**

在 Talknomics 設計的早期階段，曾有過模擬前所未有的網絡價格和活動的假設，但考慮到這一點以及新子鏈概念的方向、網絡帶來的獎勵系統和經濟，我們正在重新審視是否需要調整以平衡身體安全。作為重建代幣和機制設計的一部分，超級節點計劃和投票獎勵都在審查中。
分析完成後將立即提供詳細報告，但請同時等待新的薪酬結構和計劃。

**02：網絡中的某些用戶是否與其他普通用戶區別對待？如果是這樣，為什麼？**

是的，NGL 和大約 30-40 個大型持有者（鯨魚）超級節點之間存在私人關係。最初它是通知大業主項目延誤的臨時渠道，但它仍然是無意的。兩個人已經離開了，Symbol 上線後就成了一個多餘的頻道。與我們[透明](https://www.discord.gg/xymcity)的指導原則相反，我們現在將[Discord](https://www.discord.gg/xymcity)用於一切。

 **關於技術**
 --------------------------------
 
**03：Hatchet最近經常提到私有和公有的交叉鏈，但是他們具體的前景和對XEM/XYM交叉鏈的用處的想法是什麼？請告訴我們。**

關於[這裡](https://docs.symbolplatform.com/handbook/index-ja.html)，請參考。我們相信子鏈可以提供一種更簡潔的方式來處理條件網絡。

**04：為什麼Symbol不需要智能合約？**

Symbol 也有[智能合約](https://www.fon.hum.uva.nl/rob/Courses/InformationInSpeech/CDROM/Literature/LOTwinterschool2006/szabo.best.vwh.net/smart_contracts_2.html)的概念，就像在比特幣中一樣。具體來說，Symbol 不具備的主要是循環中的圖靈完備性，從而避免了事務處理中的無限循環（=垃圾郵件）。以太坊對此的解決方案是對每次操作（稱為gas）收取額外費用。您執行的語句越多，“佣金”就越高。

具有非圖靈完備性的完整區塊鏈具有資源使用可預測、分析能力增強、域使用集中等優點。我們正在積極研究 Symbol 程序的可能性，但我們還沒有找到具體的路徑。但也許你可以在中間找到一個[解決方案](https://www.gwern.net/Turing-complete)。

**05：您認為 Symbol 的 Layer 2 目標與以太坊 2.0 有何不同？**

例如，它可能類似於[zk-Rollups](https://docs.ethhub.io/ethereum-roadmap/layer-2-scaling/zk-rollups/)或 STARK 電路方法。然而，在研究階段確定結構和實施差異還為時過早。

**06：你是否考慮引入多項式承諾/凱特（KZT）承諾，讓基於默克爾樹的狀態證明更簡單？**

[Verkle Trees](https://math.mit.edu/research/highschool/primes/materials/2018/Kuszmaul.pdf)（緊隨其後的是 Kate Commitment）是我們與零知識證明、zk-STARKs 和 zk-Rollups 一起研究的內容之一。我還沒有做出具體的決定，但是當我考慮擴大主鏈時，我認為這是三重結構的自然過程。
對於 Kate Commitment，[Aztec](https://aztec.network/)的 om Walton-Pocock 編寫了一本很好的[入門](https://hackmd.io/@tompocock/Hk2A7BD6U)書。

**07：您如何看待以太坊虛擬機兼容？**

我仍然不確定與以太坊虛擬機兼容的好處是什麼，但為什麼不將以太坊用於與[以太坊虛擬機](https://ethereum.org/en/developers/docs/evm/)相關的任何事情？如果您採取直接的方法，您可能希望在 Ethereum 和 Symbol 之間使用專用的子鏈來保持它們的聯繫。

重要的是要了解以太坊概念不會直接轉換為 Symbol。以太坊虛擬機是一個圖靈完備的虛擬機。還有其他用於加密網絡的虛擬機，例如[Rusk](https://ethereum.org/en/developers/docs/evm/)和[NeoVM](https://docs.neo.org/docs/en-us/basic/technology/neovm.html)。此外，其他[eBPF](https://www.infoq.com/articles/gentle-linux-ebpf-introduction/)也討論過類似的可能性。沒有將虛擬機引入 Symbol 的具體計劃，但研究正在進行中。

**08：NEM3.0會發布嗎？**

不會

**09：您想為 XEM / XYM 替換製作 DEX 嗎？**

XEM / XYM 交易所是流動性提供者（交易所等）的工作。但是，有計劃通過將 NIS1 作為子鏈引入 Symbol 來引入此功能。一個短期的解決方案（我們也會建立相應的市場）是使用其他流動性網絡，例如[Thorchain](https://thorchain.org/)和[Sushiswap](https://sushi.com/)。

**10：為什麼其他鏈不能跨鏈交換到Symbol並連接？**

協議開發人員很少負責與其他網絡實現跨鏈功能。如果你想考慮跨鏈交換，請先參考這個文檔。以太坊、比特幣及其相關分叉 SHA256d 可以進行互換。

**11：Apostille 特徵是一個非常重要的特徵。Symbol Wallet 何時會實施 Apostille 功能？**

如果您有功能請求，請在[此處](https://github.com/symbol/symbol-desktop-wallet/issues)添加。我們是 Apostille 功能的粉絲，但它可能並不那麼重要，因為還沒有人提出請求。

**12：你為什麼不多談技術？**

開發者和研究人員可以在此[Discord](https://discord.gg/xymcity)上加入項目和研究頻道。

**13：以後是否可以在我的錢包中添加分層確認功能？**

請在[此處](https://github.com/symbol/symbol-desktop-wallet/issues)提出請求。

**14：是否已經有一種在 Symbol 上創建和存儲 NFT 的標準方法？另外，你什麼時候計劃或什麼時候做？還是 Symbol 開發人員現在必須自己做和實現它？**

目前，當由社區創建時，我們已經確認他們中的大多數人的供應量為 1，並在其元數據中發布了帶有 IPFS 主題標籤的馬賽克。未來有計劃擴展馬賽克功能，以支持特定供應和單個單元的特定元數據，但沒有明確的時間表。

**15：mijin 我想問一下核心開發對私鏈的看法。**

我無法回答這個問題，因為我知道 Tech Bureau 並且沒有參與該私有鏈中發生的事情。

**16：是否可以在 Symbol 區塊鏈上發行代幣？**

可以。Symbol 令牌（類似於 NIS1）被稱為馬賽克(Mosaic)，但這種命名在未來可能會改變。

**17：有沒有更漸進的節點發布方式？Bootstrap 版本在服務器版本之後，Bootstrap 更新在服務器更新之後發布。明確區分它和主網/測試網版本。特別是當它作為服務器 1.0.1.0 的更新出現時，當 Bootstrap 版本為 1.0.6 時，很難判斷您是否正在運行正確的版本。**

Bootstrap 工具的應用速度比 Catapult 快，並遵循[語義版本控制](https://semver.org/)。Catapult 也是一個獨立的軟件，它根據通用版本方法對主網和測試網版本進行了明確區分。

自 1.0.0.0 版本以來測試網 / 主網的版本定義：

![](https://i.imgur.com/qbMyCxd.png)

請注意，testnet 並不總是獨立構建的，如果沒有新功能要測試，testnet 將構建與主網相同的。

**18：你什麼時候會做一個工具，讓普通大眾可以輕鬆使用加密貨幣？**

通常，該工具將是一個錢包。您可以[在此處](https://github.com/symbol/symbol-desktop-wallet/issues)請求功能，也可以在[Discord](https://discord.gg/xymcity)上參與討論和錢包開發。

**19：我想知道我是否能夠在 XYM 應用程序中看到 NFT**

請從[這裡](https://github.com/symbol/symbol-desktop-wallet/issues)請求功能。

**20：在我迷上 NEM 之前，我首先迷上了 NXT。原因是NXT的技術創新。NEM 團隊（開發、NGL 等）試圖阻止 NEM 變得像 NXT 一樣嗎？**

我們不打算放棄 Symbol 或 NIS1。但是，每個參與者都應該為這條鏈做出貢獻並取得整體成功。協議開發人員和他們的社區之間有明確的潛在承諾。如果我們不打算遵守這一基本承諾，我們就不會進行新的重組努力。

**關於 Talknomics 和市場價格**
---------------------------------------------

**21：我們可以討論與談話經濟學和抵押模型的進一步改進嗎？例如，DOT 對普通持有者（不是主節點）的回報率比 XYM 高得多。DOT 產生 12% 的 APY，但由於波動，Symbol 的 APY 難以估計。
我認為這是由於Talknomics的設計，但不是每個人都選擇DOT而不是XYM嗎？**

不可能比較具有不同目的的兩種代幣的談話經濟學。我們的談話經濟學是一個鼓勵在網絡上進行特定操作的框架，例如旋轉新塊和參與節點操作。隨著網絡的發展，加入網絡的盈利能力也在增長。它旨在調整反饋迴路，而不是隨心所欲的進行調整。
（事實上，我們經常想在不過度給予作為[經濟補償](https://drive.google.com/file/d/1pwt-EdnjhDLc_Mi2ydHus0_Cm14rs1Aq/view)方面進行調整。）

然而，既然鏈已經開始並作為一個團隊開始，我們也在審查talknomics的設計。

雖然很難估計，但下表是當一個持有 100,000 XYM 的賬戶在Symbol發布後立即開始收穫時的估計。
![](https://i.imgur.com/GWRYGvb.png)

0.95 因子 = 本地收穫 -（95% 費用 | 5% 網絡費用） 0.7 因子 = 委託收穫（70% 費用 | 25% 委託費用 | 5% 網絡費用）


對於本地收割機，第一年 APY 為 3.2%（預期下限估計）至 14.5%（預期上限估計），對於委託收割機，APY 為 2.3%（預期下限估計）至 10%（預期上限估計）（估計）。
在當前的網絡條件下，已經觀察到接近預期上限估計的結果。

**22：我推薦使用Symbol的公鏈，但是一些日本工程師已經想出了一種將數據存儲在鏈上的方法。如果這被廣泛使用並且公共區塊鏈過載並且系統關閉，那麼支持系統是什麼？如果你能說不會掉，請告訴我原因。**

一直可以“鏈上”存儲數據（即鑲嵌元數據字段在那裡）。關鍵是它在經濟上是否可行，是否實用。但是，我們期待看到日本社區將使用“Symbol”進行什麼樣的工作。如果您遇到任何問題，我們很樂意與社區合作，為您的節點快速分類和發布補丁（有關最新信息，請加入[Discord](https://www.discord.gg/xymcity)或關注我們的[Twitter](https://www.twitter.com/NEMOfficial) 帳戶）。

**23：Gimre 曾經說過，“我對市場價格不感興趣”，但其他核心對此有何看法？我認為市場價格是支持生態系統的最重要因素之一，例如 NGL 員工的工資和工程師的捐款。**

市場價格反映了網絡的需求。[正如](https://docs.symbolplatform.com/handbook/index-ja.html)我在這裡所寫的[那樣](https://docs.symbolplatform.com/handbook/index-ja.html)，發展網絡取決於生態系統中的每個人。在鏈上實現新功能是我們的工作（而不是由特定的人組成的團隊），而由用戶使用鏈上的應用程序並找到新的和創造性的方法來利用此功能的增加。如果您認為價格是您的網絡成功的關鍵之一，請加入我們並幫助使其更實用（或Symbol的地名）。

**24：你們有什麼措施提高市場價格嗎？託管代幣供應是可能的。團隊可以通過第三方管理市場價格。它還可能導致通貨緊縮和通貨膨脹。聘請第三方同意並提供幫助如何？法規和合規性是障礙嗎？**

由於列出了多個問題，為方便起見，我將分別回答。

Q:*你們有什麼措施提高市場價格嗎？*

A:見上文“問題23”，“市場價格反映網絡需求”
託管代幣供應是可能的。
市場決定供求關係。
不是我們。

Q:*能夠產生通貨緊縮和通貨膨脹的狀態和球隊是供應鏈相關*

A:控制通縮和通脹並不是在市場的影響下“反复無常”。我們的通貨膨脹率非常小，在區塊 31410299 可以忽略不計。
如上所述，我們正在審查談話經濟學。

Q:*為什麼為了調整市場價格，或者說沒有聘請第三方*

A:這不是協議開發團隊的責任，也不是生態系統中的道德問題。您所關注的市場是您網絡健康和功能的直接反映，您可以在“[退出和語音](https://en.wikipedia.org/wiki/Exit,_Voice,_and_Loyalty)”的幫助下自由加入或離開加密網絡。它不符合該方法的機制的存在，並且可以自由地抱怨、抱怨、改變並嘗試修復或改進。
如果您正在談論做市（縮小交易中的點差），您可以使用[Hummingbot](https://docs.hummingbot.io/miner/liquidity-mining/current-rewards&terms/) 之類的程序自己完成。

**關於教育**
-----------------------------------------------

**25：我認為提供一些基本指南和簡單的編程練習來幫助您開始使用 Symbol 是很棒的。有很多可用的文檔，但不適合初學者。團隊中有人可以解決這個問題嗎？**

[我們](https://github.com/symbol/symbol-docs/issues)建議您在[此處](https://github.com/symbol/symbol-docs/issues)請求特定功能。我們也鼓勵社區參與[指南](https://docs.symbolplatform.com/guides/index.html)的創建。這裡已經有一些很好的資源，技術文檔中有一些[指南](https://docs.symbolplatform.com/guides/index.html)可以幫助您入門。

**26：我想問你是否打算創建一個教程來向你展示如何存入你的 Xym 錢包。我在幾個地方搜索了這方面的信息，但找不到。**

本[指南](https://docs.symbolplatform.com/guides/transfer/sending-a-transfer-transaction.html)介紹瞭如何使用 CLI、SDK 和錢包執行此操作。

**關於透明度**
---------------------------------

**27：承諾的AMA在哪裡？**

這裡是。你現在正在閱讀它。

**28：請告訴我們XYM在幣安(Binance)上幣的情況。**

一般來說，項目團隊無法控制幣在交易所上市的時間。準備就緒後，Binance 有信心將上架 XYM。

29：核心開發者為何隱藏？有人說這對信用不利。

問問中本聰你的想法。此外，匿名是項目負責人的一個共同特徵——CryptoNote 中的[Nicolas van Saberhagen](https://en.wikipedia.org/wiki/CryptoNote)；Sushi 中的[Chef Nomi](https://coinmarketcap.com/alexandria/people/chef-nomi)和[0x Maki](https://twitter.com/0xMaki)。
來自 [Mimble Wimble 的 Tom Elvis Jedusor](來自 Mimble Wimble 的 Tom Elvis Jedusor)。今天，有些風險投資公司完全由匿名合夥人組成。還有一些[風險投資公司支持匿名創始人](https://www.egirlcapital.com/)。有關於[假名經濟的力量的講座](https://www.youtube.com/watch?v=urtXRg9Nl3k)，[有些人甚至認為匿名會增加你行為的可信度](https://twitter.com/MikeAbundo/status/1342258232610312192?s=20)。

總之，合法性可以通過產出來衡量，而不是身份。我們認為這不會對項目產生負面影響。


**關於治理**
------------------------------

**30：我需要一個治理令牌來對這個問題進行投票。**

[治理代幣](https://insights.deribit.com/market-research/why-i-have-changed-my-mind-on-tokens/)有助於引導程序的流動性，您同意用戶是尋找自己聲音的重要信號機制，但治理代幣已經存在。這稱為 XYM。如果您正在閱讀本文，您可能會擁有它。

我們目前正在尋找為 XYM 提供治理目標的方法。其中之一是引入 Quadratic Funding 平台，該平台允許社區資助被認為對網絡最有益的公共產品。

了解與 Symbol 相關的治理含義也很重要（每個加密網絡都有自己的規則）。沒有硬性規定，我們和社區一起建立，但有時我們不能依靠群眾的智慧。一個很好的例子是高級技術決策，例如使用哪條 BLS 曲線。

我們同意透明度不是項目歷史上最好的，並且正在努力減輕它。例如，發布[類似於 ETC 的透明報告](https://etccooperative.org/ETC-Coop-Board-Package-January-February-2021.pdf)，詳細說明支出。我們取得的另一項進步是開放與 Discord 的所有內部溝通，並使我們的手冊可公開訪問和開源。

**31：等級制度和權力下放的概念如何結合在一起？**

需要一個更傳統的指揮和控制層次結構來克服要發射的最後一個里程碑。然而，傳統的分層與權力下放的概念格格不入。這就是為什麼我們要發展為遵循[Flatland 模式](https://www.researchgate.net/publication/282395703_Valve's_Way)的組織。

**32：有多少資金可用於開發 Symbol 和 NIS1？**

所有這些信息都可以在區塊鏈上找到。2020年，核心資金全部轉移至信託。該信託包括 16 億 XYM 和 28 億 XEM。（按今天的價格計算為 6.3 億美元）。XYM 比 XEM 少 12 億，因為它用於 Symbol 的區塊獎勵。

**33：NEM的核心團隊是一個什麼樣的群體，資金比較大？在日本，也有觀點認為，風險之一是核心團隊資金龐大。**

與 EOS 和以太坊基金會等相比，資金池相對較小。所有資金目前都存儲在受多重簽名帳戶保護的信託中。他們的角色和使命是“支持和發展 NEM 生態系統及其相關的區塊鏈、本地貨幣和技術”。目前，這意味著 Symbol 和 NIS1 的開發。 


**關於營銷/品牌/合作夥伴關係**
------------------------------------

**34：我想知道未來的營銷計劃。**

[正如此處](https://docs.symbolplatform.com/handbook/index-ja.html)所解釋的，社區及其大使有[責任](https://docs.symbolplatform.com/handbook/index-ja.html)提高對該項目的認識並發展生態系統。當社區建立了一個非凡的項目時，媒體自然會關注它並伸手談論它。除此之外，一些團隊成員在社交媒體上都非常活躍，出現在播客、脫口秀甚至電視上。

**35：為什麼國外不討論NEM和Symbol？**

我們毫無頭緒。

**36：為什麼這個品牌問題幾個月前沒有消失？您是如何決定不按照建議創建 Symbol 社交媒體帳戶的？
**
我們不能代表 NEM 集團及其前身。但是，社區現在正在通過 Twitter 和 Discord 發表評論。我們鼓勵您參與這些討論。我們同意我們的內部和外部社區、我們的業務合作夥伴和合作夥伴對“NEM”存在混淆。我們傾聽討論並思考最好的方法。

**37：你想模仿卡爾達諾(ADA)並發布技術更新嗎？** https://twitter.com/cardano_updates

Twitter 機器人發布的 GitHub 統計數據毫無意義。我希望您直接查看我們的 GitHub。

**38：是否可以創建每週一次的英文技術更新？我們的 NEM HUB 版主可以翻譯成他們的母語。（除了最常用的8種語言外，還涵蓋日語和其他幾種語言）NEM HUB還可以提供即時聊天室（Messenger）和參與直播，您可以在線播放常規的NEM節目。你覺得這個想法怎麼樣？**


社區已經開始將流行的推文、博客和帖子翻譯成他們的 Twitter 帳戶和[社區運營的博客](https://symbolblog.com/)。我們所有的工作都是在 Discord 和 GitHub 上完成的，因此社區可以就技術更新進行協作。

**39：很多人還是覺得XEM為主，XYM是加分，那為什麼不把NEM的標誌改成Symbol的標誌呢？**

參見問題 #36 的答案。

**40：我認為我們應該積極推動NEM（NIS1）和Symbol的差異和未來潛力。**

如[手冊](https://docs.symbolplatform.com/handbook/index-ja.html)所述，NIS1 是 Symbol 的子鏈。

**41：您未來的營銷前景如何？**

不幸的是，我沒有水晶球。

**42：在日本，加密資產仍被視為一種投資，但如果我們推出呼籲Symbol實力的電視廣告和網絡廣告，區塊鏈，並從現在開始在日本傳播區塊鏈=Symbol的形象。我想我絕對可以擊敗以太坊。我期待著一個大膽的營銷策略。**


這不是一個問題，但感謝您的熱情和建議。

**43：我想讓你多談談 DeFi。**


是的。關注我們的 Twitter 帳戶 [1](https://twitter.com/Jaguar0625) '[2](https://twitter.com/0x6861746366574) '[3](https://twitter.com/NCOSIGIMCITYNRE) 或加入[Discord](https://discord.gg/xymcity)，以獲取有關 DeFi 主題的更多想法、意見和研究。

**44：你是否與其他區塊鏈社區互動？他們對NEM感興趣嗎？**

是的。在我們三個人中，[Hatchet](https://twitter.com/0x6861746366574)是互動最多的。總的來說，其他區塊鏈項目對 NEM 的興趣不大。通過參與加密貨幣中使用的技術（例如 zk-SNARK 和 zk-Rollups）的研究和開發，並開始更多地談論 Symbol 的機制設計和架構。我認為隨著這個，興趣會增加。

**45：你認為日本對待新經濟的方法的好處是什麼？另外，您認為應該怎麼做才能將其傳播到日本以外？**

我們喜歡日本社區的熱情和實驗。我想在世界各地看到更多這樣的東西。除此之外，我們相信我們可以通過使用 Symbol 增加思想領導力、優秀文章、創新研究和產品來提高對該項目的認識。

**46：自 Symbol 推出以來已經三個多月了 我們預期的許多交易所尚未上市。為什麼？**

我們不知道。交易所有一個內部流程，可以根據市場需求優先考慮代幣。Binance 提供了一些上市[指南](https://www.binance.com/en/blog/421499824684902218/Binance-Listing-Tips-from-CZ)來幫助完成此過程，但不能保證您的代幣會被上市。幣安相信，一旦準備好，它就會上架 XYM。

**47：我想知道NEM是否考慮進入lq區塊鏈的NFT領域。它可以作為 XYM Unstake 和 Stake Stakin Special 的要求實施嗎？**

不，我不是在想。

**48：Nem 和 Symbol 用例沒有增加，所以新聞中根本沒有談論它。你不認為你發布新聞的計劃有問題嗎？**

不，我們強烈反對“以新聞換新聞”。這是一個歷史上反復出現的問題，對 NEM 已變得有害而不是有益。推動 Symbol 的採用取決於我們所有人，而不僅僅是協議團隊。如果您想查看更多新聞和媒體活動，請加入我們。在本地聚會上談論 Symbol，在會議上談論共識算法，在鏈上構建創新用例，並成為早期的先驅之一。如果您認為缺少新聞是個問題，請參與解決。

**49：我希望 Symbol 傳播得更快。**

我們也想這樣做。但好事需要時間。
您想如何實現這一目標？

**50：聘請會說英語以外的語言的影響者（例如YouTuber）以加強公司內的溝通是否有任何障礙？**

我們不會付錢給有影響力的人、名人或媒體，以讓 Symbol 獲得錯誤的榮譽。
這不符合我們的道德規範。我們希望系統地發展我們的社區，並因其實用性和創新性而獲得全世界的關注。

**51：您打算如何改善和加強NEM公司與新興技術國家之間的交流？**

在比特幣和以太坊中，“如果你建造它，他們就會來”的口頭禪已被證明是正確的。
最好的方法是改進或增強內置於鏈中的 Symbol 的功能。

**52：什麼是NEM公司？**

沒有明確的框架，但有效利用NIS1和Symbol的，是像公司這樣的組織。
