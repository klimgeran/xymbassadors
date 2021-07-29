# CM-LOG-0x1-Turkish.md

[![hackmd-github-sync-badge](https://hackmd.io/5DKQauofReyikmXVboi9fg/badge)](https://hackmd.io/5DKQauofReyikmXVboi9fg)


Bu, [Gimre](https://twitter.com/NCOSIGIMCITYNRE), [Hatchet](https://twitter.com/0x6861746366574) & [Jaguar](https://twitter.com/Jaguar0625) ile iki bölümden oluşan bir topluluk Soru-Cevap bölümünün ilk bölümüdür.

# Süper Node Programı

**01: SuperNode programında neler oluyor? Gecikme sebebi? Oylama ödülleri neden ertelendi?**

İlk Tokençalışması sırasında, ağ fiyatı ve etkinliği üzerinde modellenen ve (şimdiye kadar) mevcut ağda gözlemlediğimiz davranış olmayan bazı varsayımlar vardı. Bunun ve alt Zincirlerin yeni yönünün ışığında, ağ tarafından sağlanan ekonomik güvenliğe karşı ödülleri ve ücretleri daha iyi dengelemek için ayarlamaların gerekip gerekmediğini görmek için token ve mekanizma tasarımımızı yeniden gözden geçiriyoruz. Oylama ödülleri ve SuperNode programı da bu çabanın bir parçası olarak yeniden gözden geçiriliyor. 


Analizimizi bitirdiğimizde tam bir rapor sunacağız, ancak biz bitirene kadar herhangi bir yeni ödeme veya program beklemeyin.

**02:Ağın bazı kullanıcılarına topluluğun geri kalanına göre farklı davranılıyor mu? Öyleyse neden?**

Evet. Yaklaşık 30-40 "balina" içeren özel bir NGL :: SN kanalı var. Başlangıçta proje gecikmelerini büyük paydaşlarla iletmek için kısa ömürlü bir kanal olması amaçlandı, ancak o zamandan beri amacını kaybetti. Symbol'ün piyasaya sürülmesinden sonra gereksiz hale geldi ve ikimiz onu çoktan terk ettik. Temel şeffaflık ilkelerimize aykırıdır. Artık tüm zamanımızı [Discord'ta](https://discord.com/invite/xymcity) geçiriyoruz..

# Teknoloji

**03: Son zamanlarda, Hatchet özel ve kamu zincirlerinin çapraz zincirlenmesinden çok bahsetti. Beklentileriniz tam olarak nedir ve XEM/XYM çapraz zincirlemenin kullanışlılığı hakkındaki düşüncelerinizi duymak isterim.**

Daha fazla bilgi için [buraya](https://docs.symbolplatform.com/handbook/) bakın; alt Zincirlerin izin verilen ağları ele almanın daha temiz bir yolunu sağladığını düşünüyoruz.

**04: Symbol neden başarılı olmak için akıllı sözleşmelere ihtiyaç duymuyor?**

Symbol, tıpkı Bitcoin gibi, [akıllı sözleşmeler](https://www.fon.hum.uva.nl/rob/Courses/InformationInSpeech/CDROM/Literature/LOTwinterschool2006/szabo.best.vwh.net/smart_contracts_2.html) kavramının bir versiyonuna sahiptir. Spesifik olarak, Symbol'ün sahip olmadığı şey, tamlıktır - ana işlevsellik döngülerdir. Bunun yararı, işlem doğrulaması (yani spam) sırasında sonsuz döngülerden kaçınmasıdır. Ethereum'un buna çözümü, her işlem (gas olarak adlandırılır) için ek ücretler getirmekti - ne kadar çok ifade yürütülürse, o kadar fazla 'ücret'. 

Turing tam olmayan blok zincirlerin faydaları vardır: öngörülebilir kaynak kullanımı; geliştirilmiş analiz; odaklı etki alanı kullanımı. Bununla birlikte, Symbol'ün programlanabilirliğini genişletmenin yollarını aktif olarak araştırıyoruz, ancak henüz ileriye dönük tanımlanmış bir yolumuz yok. Belki [arada bir yerde](https://www.gwern.net/Turing-complete) bir çözüm ortaya çıkabilir.

**05: Symbol'ün Layer2 hedefinin Ethereum 2.0'a kıyasla nasıl farklı olacağını düşünüyorsunuz?**

Yaklaşımda benzerlikler olabilir (örneğin, [zk-Rollup](https://docs.ethhub.io/ethereum-roadmap/layer-2-scaling/zk-rollups/) ve STARK devreleri), ancak mimari ve uygulamadaki farklılıkları belirlemek için araştırma aşamasında henüz çok erken. 

**06:Merkle ağaç tabanlı durum provasını daha kompakt hale getirmek için polinom taahhüdü sunmayı planlıyor musunuz? / Kate (KZG)**

Taahhüdü [Verkle ağaçları](https://math.mit.edu/research/highschool/primes/materials/2018/Kuszmaul.pdf) (ve ardından Kate Taahhütleri), sıfır bilgi kanıtları, zk-STARK'lar ve zk-Toplamalar ile birlikte araştırdığımız şeylerden biridir. Henüz somut bir karar vermemiş olsak da, mainChain'i ölçeklendirmeyi düşündüğümüzde bu, trie mimarisi için doğal bir ilerlemedir. 

*[Aztec'ten](https://aztec.network/). Tom Walton-Pocock tarafından Kate Taahhütleri üzerine iyi bir başlangıç [buradan](https://hackmd.io/@tompocock/Hk2A7BD6U), bulunabilir. *

**07:EVM uyumluluğu hakkındaki düşünceleriniz nelerdir?**

[EVM](https://ethereum.org/en/developers/docs/evm/) uyumluluğunun faydasının ne olacağı görülmeye devam ediyor - sonuçta, Ethereum'u sadece EVM ile ilgili faaliyetler için kullanmaz mıydınız? Daha temiz bir yaklaşım, LP'lere daha fazla eşleştirme sağlamak için Ethereum ve Symbol arasındaki işlemleri kolaylaştıran özel bir alt Zincir olabilir..

Ethereum kavramlarının doğal olarak Symbol'e dönüşmediğini anlamak önemlidir: EVM, tam bir sanal makinedir. [Rusk](https://dusk.network/news/rusk-abi-rc) ve ya  [NeoVM](https://docs.neo.org/docs/en-us/basic/technology/neovm.html) gibi kripto ağları için başka sanal makineler de var. [eBPF](https://www.infoq.com/articles/gentle-linux-ebpf-introduction/) gibi diğer olasılıkları da tartıştık. Henüz Symbol'de sanal bir makine sunmak için somut bir planımız yok, ancak aktif olarak araştırıyoruz.

**08: NEM 3.0 çıkacak mı?**

Hayır.

**09: XEM/XYM'yi Swap için bir DEX oluşturacak mısınız?**

XEM'i XYM'ye Swap, bir likidite sağlayıcısının işi olacaktır. Evet, NIS1'in bir alt Zincir olarak (karşılık gelen bir pazar yeri ile birlikte) tanıtılmasıyla bu işlevi Symbol'e getirme planı var. Kısa vadeli çözümler, [Thorchain](https://thorchain.org/) veya Sushiswap gibi diğer likidite ağlarının kullanımını görebilir.

**10:Diğer zincirler neden Symbol ve NEM'e çapraz zincirlerle bağlanmıyor?**

Diğer kripto ağlar ile zincirler arası işlevselliği uygulamak nadiren protokol geliştiricilerinin sorumluluğundadır. Zincirler arası takasları keşfetmek istiyorsanız,  [buradaki belgeler](https://docs.symbolplatform.com/guides/secretlock/atomic-cross-chain-swap-between-NEM-public-and-private-chain.html) başlamak için iyi bir yerdir. Ethereum, Bitcoin ve ilgili çatalları için SHA256d ile bir takas mümkün olabilir.

**11: Apostil özelliği çok önemli bir özelliktir. Symbol cüzdanında apostil özelliğini ne zaman uygulayacaksınız?**

Herhangi bir özellik isteği [buraya](https://github.com/symbol/symbol-desktop-wallet/issues) eklenmelidir. Apostil taraftarı olsak da, henüz kimse bir dava açmadığı için o kadar da önemli görünmüyor.


**12: Neden daha fazla teknik tartışmaya açmıyorsunuz?**

[Discord kanalımıza](https://discord.gg/xymcity) gidin - tüm çalışmalarımız ve günlük sohbetimiz herkes tarafından görülebilir; bir geliştirici veya araştırmacıysanız, Projeler veya Araştırma kanalımıza katılabilirsiniz.

**13: Gelecekteki cüzdanlara hiyerarşik deterministik işlevler eklemek mümkün müdür?**

Kesinlikle. Lütfen [buraya](https://github.com/symbol/symbol-desktop-wallet/issues) bir özellik isteği ekleyin. .

**14:Symbol on NFT'yi oluşturmak ve yönetmek için zaten standart bir yolunuz var mı, bunu yapmayı planlıyor musunuz, ne kadar yakında veya kısacası Symbol ile çalışan geliştiriciler için kendi NFT on Symbol uygulamalarımızı oluşturmalıyız. bizim mantığımıza göre?**

Topluluğun, metadatada 1 kaynağı ve bir IPFS karması ile mozaik oluşturma standardını çoğunlukla benimsediğini gözlemledik. Bunun ötesinde, mozaik işlevselliğini belirli bir tedarikin bireysel birimi başına benzersiz meta verileri destekleyecek şekilde genişletme planları vardır, ancak tanımlanmış bir zaman çizelgesi yoktur. 

**15: Özel zincir (mijin) hakkında ne düşünüyorsunuz?**.

Core-dev'e sormak istiyorum. TechBureau ile yollarımız ayrıldı ve daha önce özel olarak konuşlandırılmış bir zincirin kullanıcıları olarak hareket etmediğimiz için bu soruya cevap veremiyoruz.

**16: Symbol blok zincirinde bir Token başlatmak mümkün müdür?**

Evet, Symbol tokenlerine (NIS1 durumunda olduğu gibi) mozaik denir. Bu isim gelecekte değişebilir.

**17: Node sürümlerine daha yapılandırılmış bir yaklaşım getirebilir miyiz? Önyükleme güncellemesinin sunucu güncellemesinden hemen sonra yayınlandığı sunucu sürümünü izleyen önyükleme sürümü. Mainnet/testnet sürümleri arasında net bir ayrım ile. Şu anda çok kafa karıştırıcı, özellikle de sunucu 1.0.1.0 için bir güncelleme olarak duyurulduğunda ve önyükleme 1.0.6'daysa, doğru sürümü çalıştırıp çalıştırmadığımı anlamak zor.**

Hayır. Önyükleme aracı, Catapult'tan daha hızlı yinelenir ve anlamsal sürüm oluşturma şemasını izler. Catapult, ana ağ ve test ağı sürümleri arasında net bir ayrım ile bağımsız yazılımlar için daha yaygın olan sürüm oluşturmayı takip eder.

Testnet/mainnet için sunucu versiyonlaması 1.0.0.0 sürümü ile tanımlanmıştır:

![](https://i.imgur.com/C67voqO.png)

*Testnet'in her zaman ayrı bir yapıya sahip olmadığını unutmayın. Test edilecek yeni bir özellik olmaması durumunda, ana ağ ile aynı yapıyı çalıştıracaktır.*

**18: Tokenlerin kullanımını ortalama bir kişi için daha uygun hale getiren bir araç ne zaman oluşturacaksınız?**

Bu araç genellikle cüzdan olarak bilinir. Özellik isteklerini [buradan](https://github.com/symbol/symbol-desktop-wallet/issues) gönderebilir veya [Discord'taki](https://discord.gg/xymcity)tartışmaya katılarak cüzdanın geliştirilmesine katılabilirsiniz. .

**19: Xym uygulamasından nft'yi görüp göremeyeceğimizi bilmek istiyorum.**

Bunu bir özellik isteği olarak [buradan](https://github.com/symbol/symbol-desktop-wallet/issues) gönderebilirsiniz.

**20: Teknolojinin yenilikçi doğası nedeniyle NEM'e girmeden önce NXT'deydim - her ikisi de kendi yollarında öncü. NEM ekiplerinin (geliştirme, ngl, vb.) NEM'in NXT gibi (terk edilmiş ve unutulmuş) gibi bitmemesini sağlamak için gösterdiği çaba nedir?**

Symbol veya NIS1'den vazgeçmeyi planlamıyoruz, ancak zincire katkıda bulunmak ve onu kolektif bir başarıya götürmek herkesin sorumluluğundadır. Bir protokolün geliştiricileri ile topluluğu arasında açık bir sosyal sözleşme vardır - ve bu sosyal sözleşmeyi sürdürme niyetinde olmasaydık, başka bir yeniden yapılanma çabasına girmezdik.
# 
# Tokenomi ve Fiyat

**21: Token ve Stake modelinde daha fazla iyileştirmeyi tartışabilir miyiz? Örneğin, DOT normal staker için (ana node değil) XYM'den çok daha karlı. 60 bin yatırım varsayarsak, DOT %12 APY üretirken, Symbol'ün tutarlı olmadığı için hesaplanması bile zor. Bunun tokenomics'in bir parçası olduğunu varsayıyorum, öyleyse neden biri DOT yerine XYM'yi tercih etsin?**

Farklı amaçları olan iki coinin tokenomiklerini karşılaştıramazsınız. Tokenlerimiz, ağdaki belirli davranışları teşvik etmek için bir çerçevedir (örneğin, yeni blokların veya çalışan düğümlerin basılmasına katılım). Ağ büyüdükçe, ağa katılmanın karlılığı da artar. Bir geri bildirim döngüsü oluşturmak için tasarlanmıştır, bir hevesle 'ayarladığınız' bir şey değil, çünkü başka bir coin daha karlıdır (aslında, [ekonomik güvenlik](https://drive.google.com/file/d/1pwt-EdnjhDLc_Mi2ydHus0_Cm14rs1Aq/view) için fazla ödeme yapmadığınızdan emin olmak için sık sık yeniden ayarlamak istersiniz.) 

Bununla birlikte, zinciri başlatmak ve bir ekip olarak birlikte çalışmaya başlamak için zamanımız olduğu için şu anda tokenomik tasarımımızı gözden geçiriyoruz. Hesaplaması zor olan noktanıza göre, aşağıdaki tablo, Symbol'ün piyasaya sürülmesinden kısa bir süre sonra hasat etmeye başlayan 100K XYM hesabı için kaba bir tahmin sunmaktadır:


![](https://i.imgur.com/ZXQCieI.png)

* 0.95 Faktör = Harvesting - (95% of Ücretler | 5% Ağ ücretleri)
* 0.7 Faktör = Delegated Harvesting (70% Ücretler | 25% Harvester | 5% Ağ ücreti)


---

Yerli Harvest makinesi için, ilk yıl için APY %3.2 (kötümser) ile %14,5 (iyimser) arasındadır; yetkilendirilmiş hasat makinesi için APY %2,3 (karamsar) ile %10 (iyimser) arasındadır. Mevcut ağ koşullarımızda iyimser sonuçlar gözlemliyoruz.

**22: Symbol genel blok zincirini kullanmanızı önerdiniz, ancak zincir üzerinde veri depolamanın bir yolunu bulan bir Japon mühendis var. Bu yaygın olarak kullanılıyorsa, genel blok zinciri yükünün artması ve sistemin durması durumunda destek sisteminiz nedir? Düşmeyeceğini söyleyebilirseniz, lütfen nedenini açıklayın.**

Verileri "zincir üzerinde" depolamak her zaman mümkün olmuştur (sonuçta mozaiklerdeki meta veri alanı bunun içindir). Bu, ekonomik olarak uygun olup olmadığı ve fayda açısından pratik olup olmadığı sorusudur. Bununla birlikte, Japon topluluğunun Symbol ile neler yarattığını dört gözle bekliyoruz. Herhangi bir sorunla karşılaşılırsa, hızlı bir şekilde öncelik belirlemek ve düğümler için bir yama yayınlamak için toplulukla birlikte çalışırız (lütfen [Discord kanalımıza ](https://www.discord.gg/xymcity) katılın ve güncellemeler için [Resmi Twitter](https://www.twitter.com/NEMOfficial) hesabımızı takip edin). 

**23: Gimre bir keresinde “Fiyatla ilgilenmiyorum” demişti. Diğer çekirdek geliştiriciler bu konuda ne düşünüyor? NGL maaşları ve mühendislere yapılan bağışlar da dahil olmak üzere, ekosistemi destekleyen en önemli faktörlerden birinin fiyat olduğunu düşünüyorum.**

Fiyat, ağın faydasının bir fonksiyonudur. [Burada](https://docs.symbolplatform.com/handbook/) yazdığımız gibi, ağı büyütmek için birlikte çalışmak ekosistemdeki çeşitli grupların sorumluluğundadır (belirli bir taraf değil). Zincire yeni işlevler eklemek bizim işimiz ve zincir üstü uygulamalar aracılığıyla bu işlevi kullanmanın yeni ve yaratıcı yollarını bulmak da kullanıcıların işidir. Fiyatın ağın başarısı için en önemli faktörlerden biri olduğunu düşünüyorsanız, katılın ve faydayı artırmaya yardımcı olun (veya Symbol'ün görünürlüğünü artırın). 

**24: Fiyatı yükseltme planınız var mı? Bunu, kontrol ettiğiniz token arz ve talebi yoluyla yapabilirsiniz. Ekip, piyasa değeri yönetimi yapmak için üçüncü bir taraf bulabilir. Ekipler ayrıca deflasyon veya enflasyon yaratarak arzı kontrol edebilir. Bunu sizin için değerlendirip size yardımcı olması için neden üçüncü bir taraf tutmuyorsunuz? Düzenleme/uyum sorunları engel mi?**

Burada birden fazla soru olduğu için, kolaylık sağlamak için onları ayıracağız.

Fiyatı yükseltmek gibi bir planınız var mı? 

Yukarıya bakın - fiyat, ağın faydasının bir fonksiyonudur. 

Bunu, kontrol ettiğiniz token arz ve talebi yoluyla yapabilirsiniz. 

Arz ve talebi piyasa kontrol eder, biz değil. 

Ekipler ayrıca deflasyon veya enflasyon yaratarak arzı kontrol edebilir.

Deflasyon veya enflasyon daki değişiklikler, piyasa güçlerine yanıt olarak "bir hevesle" yaptığınız şeyler değildir. Enflasyonumuz oldukça küçük ve 31410299 blokta ihmal edilebilir hale gelecek. Belirttiğimiz gibi, tokenomiklerimizi gözden geçiriyoruz. 

Ekip, piyasa değeri yönetimi yapmak için üçüncü bir taraf bulabilir. (…) Neden bunu sizin için değerlendirip size yardımcı olması için üçüncü bir taraf tutmuyorsunuz?

Bu ne protokol ekibinin sorumluluğundadır ne de ekosistem için etik bir şeydir. Pazarınız, ağ sağlığına ve işlevselliğine doğrudan bir yanıttır ve buna müdahale etmek, kripto ağlardaki '[çıkış ve ses](https://en.wikipedia.org/wiki/Exit,_Voice,_and_Loyalty)' mekanizmalarının amacını ortadan kaldırır. 

Piyasa yapıcılığı faaliyetlerinden (işlemler arasındaki yayılmayı azaltmaya yardımcı olan) bahsediyorsanız, [Hummingbot](https://docs.hummingbot.io/miner/liquidity-mining/current-rewards&terms/) gibi programları kullanarak bu faaliyetlere bir kullanıcı olarak kendiniz katılabilirsiniz.


# Eğitim

**Symbol'ü kullanmaya başlamak için bazı temel kılavuzlar ve basit programlama alıştırmaları sağlamak harika olurdu. Mevcut birçok belge var, ancak acemiler için fazla bir şey yok. Belki ekipten biri bunun üzerinde çalışabilir?**

[Burada](https://github.com/symbol/symbol-docs/issues) belirli bir özellik isteğinde bulunmanızı öneririz. Ayrıca topluluğu kılavuz oluşturmaya katılmaya teşvik ediyoruz - [burada](https://symbolblog.com/) zaten harika kaynaklar var ve teknik belgelerde başlamanıza yardımcı olacak bazı [kılavuzlar](https://docs.symbolplatform.com/guides/index.html) var. 

**26: Xym cüzdanına nasıl para yatırılacağını görmemizi sağlayacak bir tür eğitim oluşturmayı planlıyor musunuz diye sormak istiyorum, bunu söylüyorum çünkü bu konuda bilgi almak için birkaç yeri aradım ve bulamadım.**

[Bu](https://docs.symbolplatform.com/guides/transfer/sending-a-transfer-transaction.html) kılavuz, bunun CLI, SDK ve cüzdan ile nasıl yapılacağını açıklar.

# Şeffaflık

**27: Söz verilen AMA nerede?**

Burada. Onu okuyorsun.

**28: Binance listeleme XYM'nin durumu nedir?**

Genel olarak, proje ekiplerinin bir kripto paranın borsada listelenmesi için geçen süre üzerinde hiçbir kontrolü yoktur. Binance'in hazır olduklarında XYM'yi listeleyeceğinden eminiz.

**29: Çekirdek geliştiriciler neden yüzlerini göstermiyor?**

Bazıları bunun güven için kötü olduğunu söylüyor. Lütfen Satoshi'ye ne düşündüğünü sorun. Ayrıca, anonimlik proje liderleri arasında ortak bir özelliktir - [CryptoNote'tan Nicolas van Saberhagen](https://en.wikipedia.org/wiki/CryptoNote); Sushi’den [Chef Nomi](https://coinmarketcap.com/alexandria/people/chef-nomi) ve [0xMaki](https://twitter.com/0xMaki); MimbleWimble'dan [Tom Elvis Jedusor](https://scalingbitcoin.org/papers/mimblewimble.txt). Bugün artık sadece [anonim ortaklardan](https://www.egirlcapital.com/) oluşan [risk sermayesi şirketleri](https://cypherpunkholdings.com/investment-thesis/) var; ve anonim kurucuları destekleyen risk sermayesi şirketleri. Takma ad ekonomisinin gücü üzerine dersler var ve [hatta bazıları anonimliğin eylemlerinizi daha fazla inandırıcı hale getirdiğine inanıyor](https://twitter.com/MikeAbundo/status/1342258232610312192?s=20). 

Özetle - meşruiyeti kimliğe göre değil, çıktıya göre ölçersiniz. Bunun projeye olumsuz bir etkisi olmadığını düşünüyoruz.


# Yönetim

**30:Sorunları oylamak için bir yönetim belirtecine ihtiyacımız var.**

[Yönetişim tokenlerinin likiditeyi önyüklemeye yardımcı olduğu](https://insights.deribit.com/market-research/why-i-have-changed-my-mind-on-tokens/) ve kullanıcıların seslerini bulmaları için önemli bir sinyal mekanizması olduğu konusunda hemfikir olsak da, yönetim için zaten bir tokeniniz var - buna XYM deniyor. Eğer bunu okuyorsan, elinde tutma ihtimalin var. 

Şimdi XYM'ye yönetimde bir amaç vermenin yollarını arıyoruz - bunlardan biri, topluluğun ağ için en faydalı olduğunu düşündükleri kamu mallarını finanse etmesini sağlayacak ikinci dereceden bir finansman platformunun tanıtılması yoluyla.

Symbol açısından yönetişimin ne anlama geldiğini anlamak da önemlidir (her kripto ağ kendi kurallarına sahiptir). Kesin ve hızlı kurallarımız olmasa da ve bu toplulukla birlikte inşa edeceğimiz bir şey olsa da, kalabalığın bilgeliğine bırakılmaması gereken bazı şeyler var - harika bir örnek, hangi BLS eğrisinin kullanılacağı gibi son derece teknik kararlardır. 

Şeffaflığın proje tarihindeki en iyi şey olmadığı konusunda hemfikiriz ve bunu hafifletmek için adımlar atıyoruz. Örneğin, [harcamaları detaylandıran ETC'ye](https://etccooperative.org/ETC-Coop-Board-Package-January-February-2021.pdf) benzer şeffaflık raporları yayınlayacağız. Attığımız diğer bir adım ise tüm iç iletişimimizi Discord'a açmak ve şirket el kitabımızı herkesin erişimine açık ve açık kaynak haline getirmek.


**31: Hiyerarşi kavramı, merkeziyetsiz olma kavramına nasıl uyuyor?**

Fırlatmak için son kilometreyi geçmemiz için daha geleneksel bir komuta ve kontrol hiyerarşisine ihtiyacımız vardı. Ancak geleneksel hiyerarşi, ademi merkeziyetçilik kavramına uymuyor, bu yüzden organizasyonumuzu [Flatland modeliyl](https://www.researchgate.net/publication/282395703_Valve's_Way)e daha tutarlı bir şeye dönüştürmek istiyoruz. 

**32: Symbol & NIS1 geliştirme için ne kadar fon mevcut ve hangi süre için?**

Tüm bu bilgiler blok zincirinde bulunabilir. 2020'de tüm 'çekirdek fonlar' (yani ilk öncül fon) bir Tröst'e taşındı. Toplamda, Trust kabaca 1,6 milyar XYM ve 2,8 milyar XEM içeriyor (bugünün fiyatlarıyla yaklaşık ~630 milyon USD). XEM'den 1,2 milyar daha az XYM var çünkü bunlar Symbol için blok ödüllerine dönüştürüldü.

**33: Nispeten büyük bir fona sahip NEM'in çekirdek ekibi nasıl bir gruptur? **

Bazı Japonlar, ekibin çok büyük bir fona sahip olmasının risklerden biri olduğunu düşünüyor. EOS veya Ethereum Vakfı gibi bir şeye kıyasla, fon havuzu nispeten küçüktür. 

Tüm fonlar şu anda multisig hesaplar aracılığıyla korunan Tröstlerde tutulmaktadır; rolleri ve misyonları, bu fonları "NEM ekosistemini, onunla ilişkili blok zincirlerini, yerel para birimlerini ve teknolojileri desteklemek ve geliştirmek için" kullanmaktır. Şu anda bu, Symbol ve NIS1'in geliştirilmesi anlamına geliyor.


# Pazarlama/Markalaşma/Ortaklıklar

**34: Gelecekteki pazarlama planları hakkında bilgi edinmek istiyorum.**

[Burada](https://docs.symbolplatform.com/handbook/) detaylandırdığımız gibi, projeye görünürlük kazandırmak ve ekosistemi büyütmek topluluğun ve Elçilerinin sorumluluğundadır. Topluluk dikkate değer projeler inşa ederken, medya da doğal olarak onlara görünürlük sağlayacak ve proje hakkında konuşmak için onlara ulaşacaktır. Buna ek olarak, bazı ekip üyelerimiz hem sosyal medyada çok aktif hem de podcast'lerde, talkshow'larda ve hatta televizyonda yer alıyor. 

**35: NEM veya Symbol Japonya dışında neden konuşulmuyor?**

私 た ち に は 手 掛 か り が あ り ま せ ん. (Hiçbir Fikrimiz Yok.)

**36: Bu marka sorunları neden aylar önce çözülmedi? Symbol sosyal medya hesaplarının önerildiği gibi açılmamasına neden olan süreç neydi?**

NEM Group ve öncülleri adına konuşamıyoruz - ancak topluluk şu anda Twitter ve Discord aracılığıyla görüşlerini dile getiriyor. Bu tartışmalara katılmanızı öneririz. Hem topluluğumuzda hem de borsalar ve ortaklar arasında dahili ve harici olarak 'NEM' konusunda bir miktar kafa karışıklığı olduğu konusunda hemfikiriz. Tartışmayı dinliyoruz ve ileriye dönük en iyi yolu düşünüyoruz. 

**37: Neden Cardano'nun liderliğini takip etmiyoruz ve teknik güncellemeleri tweetlemiyoruz?örnek;** 

https://twitter.com/cardano_updates

Bu Twitter botu çoğunlukla anlamsız GitHub istatistikleri yayınlıyor. Doğrudan GitHub'ımıza bakmanızı tercih ederiz. 

**38: Tüm teknik güncellemelerin haftalık bir özetini İngilizce olarak üretebilir miyiz? NEM HUB modlarımız kendi ana dillerine çevrilebilir (en çok konuşulan 8 dil, ayrıca Japonca ve diğerleri). NEMHUB anlık sohbet odası (Messenger) sağlayabilir, ayrıca canlı yayına katılabilir, NEM programlarını çevrimiçi olarak düzenli olarak yayınlayabilir. Ne düşünüyorsun?**

Topluluğumuz, hem [Twitter hesapları](https://docs.google.com/document/d/1rNUdM4z0pI_BldoWoT8jkTjP9PFXBdPRyapHbLcXWEQ/edit?usp=drivesdk) hem de topluluk tarafından işletilen [bloglar](https://symbolblog.com/) aracılığıyla popüler tweet'leri, blogları ve gönderileri çevirmeye başladı bile. Tüm çalışmalarımız Discord ve GitHub'da olduğu için topluluk, toplu teknik güncellemeler yapmak için birlikte çalışabilir.

**39: Hala XEM'in ana olduğunu ve XYM'nin sadece bir bonus olduğunu düşünen birçok insan var, neden NEM logosunu Symbol logosuna değiştirmiyoruz? **

#36. soruya verdiğimiz yanıta bakın. 

**40: Bence NEM (NIS1) ve Symbol arasındaki farkları ve onların gelecek beklentilerini aktif olarak pazarlamalıyız.**

[El kitabında](https://docs.symbolplatform.com/handbook/) detaylandırıldığı gibi, NIS1, bir Sembolün alt Zinciri olacaktır.

**41: Gelecekte daha fazla pazarlama olasılığı bilmek istiyorum.**

Maalesef çalışan bir kristal topumuz yok. 

**42:Japonya'da kripto varlıklar hala bir yatırım olarak görülüyor, ancak sembolün gücü olan blok zincirine hitap eden TV reklamları ve çevrimiçi reklamlar başlatırsak ve bundan sonra Japonya'da blok zinciri = Symbol imajını aşılarsak , kesinlikle Ethereum'u yenebiliriz. Cesur pazarlama stratejinizi dört gözle bekliyoruz.**

Bir soru olmasa da, coşku ve öneri için teşekkür ederiz.

**43: DeFi hakkında daha fazla konuşun.**

Yapacağız. DeFi konusunda daha fazla düşünce, görüş ve araştırma için Twitter hesaplarımızı [[1]](https://twitter.com/Jaguar0625)[[2]](https://twitter.com/0x6861746366574)[[3]](https://twitter.com/NCOSIGIMCITYNRE)takip edebilir veya [Discord](https://discord.gg/xymcity)'a katılabilirsiniz.

**44: Diğer blockchain topluluklarıyla etkileşime giriyor musunuz? NEM ile ilgileniyorlar mı?**

Evet. Üçümüz arasında en çok maruz kalan kişi [Hatchet](https://twitter.com/0x6861746366574); Genel olarak, diğer blockchain projelerinin NEM'e ilgisi düşüktür. Cryptocurrency genelinde kullanılan teknolojilerin (zk-SNARKs ve zk-Rollups gibi) araştırılmasına ve geliştirilmesine katılmaya başladığımızda ve ayrıca Symbol'ün mekanizma tasarımı ve mimarisi hakkında daha fazla konuşmaya başladığımızda bunun zamanla artacağını düşünüyoruz. 

**45: Japonya'nın NEM'e yaklaşımı hakkında ne düşünüyorsunuz? Ayrıca, Japonya'nın ötesine yayılması için sizce ne yapılmalı?**

Japon topluluğunun coşkusunu ve deneyimlerini seviyoruz. Bunun dünya çapında daha fazlasını görmek istiyoruz. Bunun ötesinde, daha fazla düşünce liderliği, iyi yazılmış makaleler, yenilikçi araştırmalar ve Symbol kullanan ürünlerin projeye daha iyi görünürlük kazandırabileceğini düşünüyoruz.

**46: Symbol'ün piyasaya sürülmesinden bu yana üç aydan fazla zaman geçti. Ancak, umduğum kadar borsada listelenmedi. Neden?**

Emin değiliz. Borsaların, piyasa talebine göre coinlere öncelik vermelerini sağlayan dahili bir süreci vardır. Binance, sürece yardımcı olmak için bazı listeleme yönergeleri sağlarken, madeni paranızın listeleneceğinin garantisi yoktur. Binance'in hazır olduklarında XYM'yi listeleyeceğini düşünüyoruz. 

**47: NEM'in lq Blockchain içindeki NFT dünyasına girmeyi düşünüp düşünmediğini ve XYM $'lık Stake ve Stake için Stakin Specials için bir gereklilik olarak uygulanabileceğini bilmek istiyorum.**

Hayır

**48: Nem veya Symbol’un kullanım vakalarının sayısı artmadığı için haberlerde hiç konuşulmuyor. Bu haberi yayınlamak için yapılan planda bir sorun olabileceğini düşünmüyor musunuz?**

Hayır. “Haber olsun diye haber yapılmasına” şiddetle karşıyız. Bu tarihsel, tekrar eden bir sorun olmuştur ve NEM'e yardım etmekten çok zarar vermiştir. 

Symbol'ün benimsenmesini sağlamak yalnızca protokol ekibinin değil, hepimizin görevidir. Haberlerde veya medyada daha fazla etkinlik görmek istiyorsanız, katılın! Yerel buluşmanızda Symbol hakkında konuşun; konferanslarda fikir birliği algoritması hakkında konuşmak; zincir üzerinde yenilikçi kullanım alanları oluşturun ve ilk öncülerden biri olun. Haber eksikliğinin bir sorun olduğunu düşünüyorsanız, sizi çözümün bir parçası olmaya davet ediyoruz. 


**49: Symbol'ü daha hızlı popüler hale getirmeni istiyorum!**

Biz de yaparız! Ama güzel şeyler zaman alır. Bunun nasıl olmasını istiyorsun? 

**50: Şirketin iletişimini güçlendirmek için İngilizce dışında bir dil konuşan etkili birini (örneğin bir youtuber) işe almanın herhangi bir sakıncası var mı?**

Hayır. Symbol'e yanlış güvenilirlik kazandırmak için etkileyicilere, ünlülere veya medyaya ödeme yapmayız. Bu bizim ahlakımıza uygun değil. Topluluğumuzu organik olarak büyütmek ve faydamız ve yenilikçiliğimiz nedeniyle küresel ilgi çekmek istiyoruz.

**51: NEM şirketinin gelişen teknolojiye sahip ülkelerle iletişimini nasıl geliştirmeyi ve güçlendirmeyi düşünüyorsunuz?**

Hem Bitcoin hem de Ethereum, “eğer inşa ederseniz gelecekler” mantrasının doğru olduğunu kanıtladı. Symbol'ün zincirle inşa etme yeteneklerini geliştirmenin ve güçlendirmenin en iyi yolu. 

**52: NEM şirketi nedir?**

Emin değiliz ama bu, NIS1 veya Symbol kullanan bir şirkete benziyor.










