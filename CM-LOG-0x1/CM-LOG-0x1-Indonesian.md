# LOG KOMUNITAS 0x1

[![hackmd-github-sync-badge](https://hackmd.io/5DKQauofReyikmXVboi9fg/badge)](https://hackmd.io/5DKQauofReyikmXVboi9fg)


Ini adalah bagian pertama dalam Q&A komunitas dua bagian dengan [Gimre](https://twitter.com/NCOSIGIMCITYNRE), [Hatchet](https://twitter.com/0x6861746366574) & [Jaguar](https://twitter.com/Jaguar0625).

# Program SuperNode

**01: Apa yang terjadi dengan program SuperNode? Mengapa penundaan? Mengapa hadiah voting ditunda?**

Selama pekerjaan tokenomik awal, ada beberapa asumsi yang dimodelkan pada harga jaringan dan aktivitas yang (sejauh ini) tidak menjadi perilaku yang kami amati pada jaringan saat ini. Mengingat hal ini, serta arah baru subRantai, kami meninjau kembali desain token dan mekanisme kami untuk melihat apakah penyesuaian diperlukan untuk lebih menyeimbangkan imbalan dan biaya vs keamanan ekonomi yang disediakan oleh jaringan. Hadiah pemungutan suara dan program SuperNode juga ditinjau kembali sebagai bagian dari upaya ini.

Kami akan memberikan laporan lengkap setelah kami menyelesaikan analisis kami, tetapi jangan mengharapkan pembayaran atau program baru sampai kami menyelesaikannya.

**02: Apakah beberapa pengguna jaringan diperlakukan berbeda dengan komunitas lainnya? Jika demikian, mengapa?**

Ya. Ada saluran NGL :: SN pribadi yang memiliki sekitar 30-40 'paus'. Awalnya dimaksudkan sebagai saluran berumur pendek untuk mengkomunikasikan penundaan proyek dengan pemangku kepentingan besar, tetapi sejak itu kehilangan tujuannya. Setelah peluncuran Simbol itu menjadi tidak perlu, dan kami berdua telah meninggalkannya. Ini bertentangan dengan prinsip inti transparansi kami. Kami sekarang menghabiskan seluruh waktu kami di [Discord](https://discord.com/invite/xymcity).

# Teknologi

**03: Akhir-akhir ini, Hatchet banyak menyebutkan tentang cross-chaining private dan public chain. Apa sebenarnya prospek Anda, dan saya ingin mendengar pendapat Anda tentang kegunaan rantai silang XEM/XYM.**

Lihat di [sini](https://docs.symbolplatform.com/handbook/) untuk informasi lebih lanjut; kami pikir subChain menyediakan cara yang lebih bersih untuk menangani jaringan yang diizinkan

**04: Mengapa Symbol tidak memerlukan kontrak pintar untuk berhasil?**

Symbol memang memiliki versi konsep kontrak pintar, sama seperti Bitcoin. Secara khusus, apa yang tidak dimiliki Symbol adalah kelengkapan turing - fungsionalitas utama adalah loop. Manfaatnya adalah menghindari loop tak terbatas selama verifikasi transaksi (yaitu spam). Solusi Ethereum untuk ini adalah memperkenalkan biaya tambahan untuk setiap operasi (disebut gas) - semakin banyak pernyataan yang akan dieksekusi, semakin banyak 'biaya'.

Ada manfaat dari blockchain lengkap non-turing: penggunaan sumber daya yang dapat diprediksi; analisis yang ditingkatkan; penggunaan domain terfokus. Karena itu, kami secara aktif meneliti cara untuk memperluas kemampuan program Symbol, tetapi kami belum memiliki jalur yang pasti ke depan. Mungkin solusi mungkin muncul di suatu tempat di [antara keduanya](https://www.gwern.net/Turing-complete).

**05: Menurut Anda bagaimana tujuan Symbol dari Layer2 akan berbeda dibandingkan dengan Ethereum 2.0?**

Mungkin ada kesamaan dalam pendekatan (misalnya, [zk-Rollup](https://docs.ethhub.io/ethereum-roadmap/layer-2-scaling/zk-rollups/) dan sirkuit STARK), tetapi terlalu dini dalam tahap penelitian untuk mengidentifikasi perbedaan dalam arsitektur dan implementasi.

**06: Apakah Anda berencana untuk memperkenalkan komitmen polinomial untuk membuat pemeriksaan status berbasis pohon Merkle lebih kompak? / Kate (KZG) Komitmen**

[Verkle Trees](https://math.mit.edu/research/highschool/primes/materials/2018/Kuszmaul.pdf) (dan selanjutnya, Kate Commitments) adalah salah satu hal yang telah kami teliti bersama dengan bukti tanpa pengetahuan, zk-STARK, dan zk-Rollup. Meskipun kami belum membuat keputusan konkret, ini adalah perkembangan alami untuk arsitektur trie ketika kami berpikir tentang penskalaan mainChain.

*Primer yang bagus tentang Komitmen Kate dapat ditemukan di [sini](https://hackmd.io/@tompocock/Hk2A7BD6U), oleh Tom Walton-Pocock dari [Aztec](https://aztec.network/).*

**07: Apa pendapat Anda tentang kompatibilitas EVM?**

Masih harus dilihat apa manfaat kompatibilitas [EVM](https://ethereum.org/en/developers/docs/evm/) - setelah semua, tidakkah Anda hanya menggunakan Ethereum untuk aktivitas terkait EVM? Pendekatan yang lebih bersih mungkin adalah subChain khusus yang memfasilitasi transaksi antara Ethereum dan Symbol, untuk memberikan lebih banyak pasangan kepada LP.

Penting untuk dipahami bahwa konsep Ethereum tidak secara alami diterjemahkan ke dalam Simbol: EVM adalah mesin virtual yang lengkap. Ada mesin virtual lain untuk jaringan kripto, seperti [Rusk](https://dusk.network/news/rusk-abi-rc) atau [NeoVM](https://docs.neo.org/docs/en-us/basic/technology/neovm.html). Kami juga telah membahas kemungkinan lain, seperti [eBPF](https://www.infoq.com/articles/gentle-linux-ebpf-introduction/). Kami belum memiliki rencana konkret untuk memperkenalkan mesin virtual di Symbol, tetapi kami secara aktif menelitinya.

**08: Apakah NEM 3.0 akan dirilis?**

Tidak.

**09: Apakah Anda akan membuat DEX untuk menukar XEM/XYM?**

Menukar XEM ke XYM akan menjadi tugas penyedia likuiditas. Ya, ada rencana untuk membawa fungsi ini ke Symbol dengan pengenalan NIS1 sebagai subChain (bersama dengan pasar yang sesuai). Solusi jangka pendek mungkin melihat penggunaan jaringan likuiditas lain, seperti [Thorchain](https://thorchain.org/) atau Sushiswap

**10: Mengapa rantai lain tidak terhubung dengan  cross-chains ke Symbol dan NEM?**

Jarang sekali tanggung jawab pengembang protokol untuk mengimplementasikan fungsionalitas rantai silang dengan jaringan kripto lainnya. Jika Anda ingin menjelajahi pertukaran lintas rantai, dokumentasi di [sini](https://docs.symbolplatform.com/guides/secretlock/atomic-cross-chain-swap-between-NEM-public-and-private-chain.html) adalah tempat yang baik untuk memulai. Pertukaran dapat dilakukan dengan SHA256d untuk Ethereum, Bitcoin, dan forks terkaitnya.

**11: Fitur apostille adalah fitur yang sangat penting. Kapan Anda akan menerapkan fitur apostille di dompet symbol?**

Setiap permintaan fitur harus ditambahkan di [sini](https://github.com/symbol/symbol-desktop-wallet/issues). Meskipun kami penggemar Apostille, tampaknya itu tidak terlalu penting karena belum ada yang mengajukan masalah.


**12: Mengapa Anda tidak membuka diri untuk lebih banyak diskusi teknologi?**

Buka [Discord](https://discord.gg/xymcity) - semua pekerjaan dan obrolan sehari-hari kami dapat dilihat oleh publik; jika Anda seorang pengembang atau peneliti, Anda dapat terlibat dalam Proyek atau saluran Penelitian kami.

**13: Apakah mungkin untuk menambahkan fungsi deterministik hierarkis di dompet masa depan?**

Tentu. Silakan tambahkan permintaan fitur di [sini](https://github.com/symbol/symbol-desktop-wallet/issues).

**14: Apakah kalian sudah memiliki cara standar untuk membuat dan mengelola NFT pada Symbol, apakah Anda berencana untuk melakukannya, seberapa cepat, atau singkatnya untuk saat ini bagi para pengembang yang bekerja dengan Symbol, kita harus membuat implementasi NFT sendiri pada Symbol di bawah logika kita?**

Kami telah mengamati bahwa komunitas sebagian besar telah mengadopsi standar pembuatan mosaik dengan pasokan 1 dan hash IPFS dalam metadata. Di luar ini, ada rencana lebih lanjut untuk memperluas fungsionalitas mosaik untuk mendukung metadata unik per unit individu dari pasokan tertentu, tetapi tidak ada garis waktu yang ditentukan.

**15: Apa pendapatmu tentang rantai pribadi (mijin)? Saya ingin bertanya pada core-dev**.

Jalur kami dengan TechBureau telah menyimpang, dan karena kami belum pernah bertindak sebagai pengguna rantai yang digunakan secara pribadi, kami tidak dapat menjawab pertanyaan itu.

**16: Apakah mungkin untuk meluncurkan token di blockchain Symbol?**

Ya, Token simbol (seperti dalam kasus NIS1) disebut mosaik. Penamaan ini mungkin akan berubah di masa mendatang.

**17: Bisakah kita mendapatkan pendekatan yang lebih terstruktur untuk rilis node? Versi bootstrap yang mengikuti versi server di mana pembaruan bootstrap dirilis tepat setelah pembaruan server. Dengan perbedaan yang jelas antara rilis mainnet/testnet. Terlalu membingungkan saat ini, terutama jika diumumkan sebagai pembaruan ke server 1.0.1.0 dan bootstrap berada di 1.0.6, sulit untuk mengetahui apakah saya menjalankan versi yang benar.**

Tidak. Alat bootstrap melakukan iterasi lebih cepat dari Catapult, dan mengikuti skema versi semantik. Catapult mengikuti pembuatan versi yang lebih umum untuk perangkat lunak mandiri, dengan perbedaan yang jelas antara rilis mainnet dan testnet.

Versi server untuk testnet/mainnet telah ditentukan dengan rilis 1.0.0.0:

![](https://i.imgur.com/C67voqO.png)

*Perhatikan bahwa testnet tidak selalu memiliki build terpisah. Jika tidak ada fitur baru untuk diuji, ia akan menjalankan bawaan yang sama seperti mainnet.*

**18: Kapan Anda akan membuat alat yang membuat penggunaan token lebih dapat diterapkan pada kebanyakan orang?**

Alat itu biasa disebut dompet. Anda dapat mengirimkan permintaan fitur di sini, atau Anda dapat terlibat dalam pengembangan dompet dengan bergabung dalam diskusi di [Discord](https://discord.gg/xymcity).

**19: Saya ingin tahu apakah kami dapat melihat nft dari aplikasi Xym.**

Anda dapat mengirimkannya sebagai permintaan fitur di [sini](https://github.com/symbol/symbol-desktop-wallet/issues).

**20: Saya masuk ke NXT terlebih dahulu sebelum saya masuk ke NEM karena sifat teknologi yang inovatif—keduanya adalah pionir dengan caranya sendiri. Apa upaya yang dilakukan oleh tim NEM (dev, ngl, dll) untuk memastikan NEM tidak berakhir seperti NXT (ditinggalkan dan dilupakan)?**

Kami tidak berencana untuk meninggalkan Symbol atau NIS1, tetapi merupakan tanggung jawab semua orang untuk berkontribusi pada rantai dan mendorongnya menuju kesuksesan bersama. Ada kontrak sosial yang jelas antara pengembang protokol dan komunitasnya - dan kami tidak akan melakukan upaya reorganisasi lain jika kami tidak bermaksud untuk menegakkan kontrak sosial itu.
# 
# Tokenomics dan Harga

**21: Bisakah kita mendiskusikan perbaikan lebih lanjut pada tokennomics dan model staking? Misalnya, DOT jauh lebih menguntungkan bagi staker biasa (bukan master node) daripada XYM. Dengan asumsi investasi 60rb, DOT menghasilkan 12% APY, sedangkan Symbol sulit untuk dihitung karena tidak konsisten. Saya berasumsi ini adalah bagian dari tokennomics, jadi mengapa seseorang memilih untuk mempertaruhkan XYM daripada DOT?**

Anda tidak dapat membandingkan tokennomics dari dua koin yang memiliki tujuan berbeda. Tokenomics kami adalah kerangka kerja untuk mendorong perilaku tertentu dalam jaringan (misalnya, partisipasi dalam pencetakan blok baru atau menjalankan node). Seiring pertumbuhan jaringan, profitabilitas berpartisipasi dalam jaringan juga tumbuh. Ini dirancang untuk membuat lingkaran umpan balik, bukan sesuatu yang Anda 'sesuaikan' dengan iseng karena koin lain lebih menguntungkan (pada kenyataannya, Anda sering ingin menyesuaikan kembali untuk memastikan Anda tidak membayar lebih untuk keamanan ekonomi.

Karena itu, saat ini kami sedang meninjau desain tokenomik kami karena kami memiliki waktu untuk meluncurkan rantai dan mulai bekerja bersama sebagai sebuah tim.

Untuk poin Anda tentang sulitnya perhitungan, tabel berikut menyajikan perkiraan kasar untuk akun 100K XYM yang mulai dipanen segera setelah peluncuran Symbol:

![](https://i.imgur.com/ZXQCieI.png)

* 0.95 Factor = Harvesting - (95% of Fees | 5% Network Fee)
* 0.7 Factor = Delegated Harvesting (70% of Fees | 25% Harvester | 5% Network Fee)


---

Untuk pemanen asli, APY untuk tahun pertama berkisar antara 3,2% (pesimis) hingga 14,5% (optimis); untuk pemanen yang didelegasikan, APY antara 2,3% (pesimis) dan 10% (optimis). Dalam kondisi jaringan kami saat ini, kami mengamati hasil yang optimis.

**22: Anda merekomendasikan untuk menggunakan blockchain publik Symbol, tetapi ada seorang insinyur Jepang yang telah menemukan cara untuk menyimpan data secara on-chain. Jika ini digunakan secara luas, apa sistem pendukung Anda jika beban blockchain publik meningkat dan sistem berhenti? Jika Anda dapat mengatakan itu tidak akan turun, tolong jelaskan mengapa.**

Menyimpan data 'on-chain' selalu memungkinkan *(bagaimanapun juga, untuk itulah bidang metadata dalam mosaik*). Ini adalah pertanyaan apakah itu layak secara ekonomi, dan praktis dari sudut pandang utilitas. Karena itu, kami menantikan apa yang dibuat komunitas Jepang dengan Symbol. Jika ada masalah yang ditemukan, kami akan bekerja dengan komunitas untuk segera melakukan triase dan mengeluarkan patch untuk node (silakan bergabung dengan [Discord](https://www.discord.gg/xymcity) kami dan ikuti akun [Twitter kami](https://www.twitter.com/NEMOfficial) untuk pembaruan apa pun).

**23: Gimre pernah berkata, "Saya tidak tertarik pada harga." Apa pendapat para pengembang inti lainnya tentang ini? Menurut saya harga adalah salah satu faktor terpenting dalam mendukung ekosistem, termasuk gaji NGL dan donasi kepada para insinyur.**

Harga adalah fungsi dari utilitas jaringan. Seperti yang kami tulis di [sini](https://docs.symbolplatform.com/handbook/), adalah tanggung jawab berbagai kelompok dalam ekosistem untuk bekerja sama mengembangkan jaringan (bukan satu pihak tertentu). Adalah tugas kami untuk menambahkan fungsionalitas baru ke rantai - dan tugas pengguna adalah menemukan cara baru dan kreatif untuk memanfaatkan fungsionalitas ini melalui aplikasi on-chain. Jika menurut Anda harga adalah salah satu faktor terpenting bagi keberhasilan jaringan, ikut serta dan bantu meningkatkan utilitas (atau, promosikan visibilitas Symbol).

**24: Apakah Anda memiliki rencana untuk menaikkan harga? Anda dapat melakukannya melalui penawaran dan permintaan token, yang Anda kendalikan. Tim dapat menemukan pihak ketiga untuk membuat manajemen nilai pasar. Tim juga dapat mengontrol pasokan, menciptakan deflasi atau inflasi. Mengapa Anda tidak menyewa pihak ketiga untuk mengevaluasi ini untuk Anda dan membantu Anda? Apakah masalah regulasi/kepatuhan menjadi kendala?**

Karena ada beberapa pertanyaan di sini, kami akan memecahnya untuk kenyamanan.

> Apakah Anda memiliki rencana untuk menaikkan harga?

Lihat di atas - harga adalah fungsi dari utilitas jaringan.

> Anda dapat melakukannya melalui penawaran dan permintaan token, yang Anda kendalikan.

Pasar mengendalikan penawaran dan permintaan, bukan kita.

> Tim juga dapat mengontrol pasokan, menciptakan deflasi atau inflasi.

Perubahan pada deflasi atau inflasi bukanlah hal yang Anda lakukan 'dengan iseng' dalam menanggapi kekuatan pasar. Inflasi kami cukup kecil, dan akan diabaikan di blok 31410299. Seperti yang telah kami nyatakan, kami sedang menjalani peninjauan tokenomik kami.

> Tim dapat menemukan pihak ketiga untuk membuat manajemen nilai pasar. (...) Mengapa Anda tidak menyewa pihak ketiga untuk mengevaluasi ini untuk Anda dan membantu Anda?

Itu bukan tanggung jawab tim protokol, juga bukan hal etis bagi ekosistem. Pasar Anda adalah respons langsung terhadap kesehatan dan fungsionalitas jaringan, dan campur tangan dengan itu mengalahkan tujuan mekanisme '[keluar dan suara](https://en.wikipedia.org/wiki/Exit,_Voice,_and_Loyalty)' di jaringan kripto.

Jika Anda berbicara tentang aktivitas pembuatan pasar (yang membantu mengurangi penyebaran antar transaksi), Anda dapat terlibat dalam aktivitas ini sendiri sebagai pengguna dengan memanfaatkan program seperti [Hummingbot](https://docs.hummingbot.io/miner/liquidity-mining/current-rewards&terms/).

# Pendidikan

**25: Akan sangat bagus untuk memberikan beberapa panduan dasar dan latihan pemrograman sederhana untuk memulai dengan Symbol. Ada banyak dokumentasi yang tersedia tetapi tidak banyak untuk pemula. Mungkin seseorang dalam tim akan dapat mengerjakan ini?**

Kami mendorong Anda untuk membuat permintaan fitur khusus di [sini]([https:/](https://github.com/symbol/symbol-docs/issues)/). Kami juga mendorong komunitas untuk berpartisipasi dalam membuat panduan - sudah ada beberapa sumber daya yang fantastis di [sini](https://symbolblog.com/) dan dokumentasi teknis memiliki beberapa [panduan](https://docs.symbolplatform.com/guides/index.html) untuk Anda mulai.

**26: Saya ingin bertanya kepada Anda apakah Anda berencana untuk membuat semacam tutorial yang memungkinkan kita melihat cara menyimpan di dompet Xym, saya mengatakan ini karena saya telah mencari di beberapa tempat untuk informasi tentangnya dan saya belum menemukannya .**

[Panduan ini](https://docs.symbolplatform.com/guides/transfer/sending-a-transfer-transaction.html) menjelaskan cara melakukannya melalui CLI, SDK, dan dompet.

# Transparansi

**27: Dimana AMA yang dijanjikan?**

Itu disini. Anda sedang membacanya.

**28: Apa status Binance listing XYM?**

Umumnya, tim proyek tidak memiliki kendali atas waktu yang diperlukan untuk mendaftarkan koin di bursa. Kami yakin Binance akan mencantumkan XYM saat mereka siap.

**29: Mengapa pengembang inti tidak menunjukkan wajah mereka? Beberapa orang mengatakan bahwa ini buruk untuk kepercayaan.**

Tolong tanyakan pada Satoshi apa yang dia pikirkan. Selain itu, anonimitas adalah ciri umum di antara pemimpin proyek - [Nicolas van Saberhagen dari CryptoNote](https://en.wikipedia.org/wiki/CryptoNote); [Chef Nomi](https://coinmarketcap.com/alexandria/people/chef-nomi) dan [0xMaki](https://twitter.com/0xMaki) dari Sushi; [Tom Elvis Jedusor dari MimbleWimble](https://scalingbitcoin.org/papers/mimblewimble.txt). Saat ini, sekarang ada perusahaan modal ventura yang secara [eksklusif terdiri dari mitra anonim](https://www.egirlcapital.com/); dan [perusahaan modal ventura yang mendukung pendiri anonim](https://cypherpunkholdings.com/investment-thesis/). Ada kuliah tentang kekuatan [ekonomi pseudonim](https://www.youtube.com/watch?v=urtXRg9Nl3k), dan beberapa [bahkan percaya anonimitas membuat tindakan Anda lebih kredibel](https://twitter.com/MikeAbundo/status/1342258232610312192?s=20).

Singkatnya - Anda mengukur legitimasi dengan output, bukan dengan identitas. Kami pikir ini tidak memiliki efek negatif pada proyek.

# Pemerintahan

**30: Kami membutuhkan token tata kelola untuk memberikan suara pada masalah.**

Meskipun kami setuju bahwa [token tata kelola membantu likuiditas bootstrap]([https:/](https://insights.deribit.com/market-research/why-i-have-changed-my-mind-on-tokens/)/) dan merupakan mekanisme pensinyalan penting bagi pengguna untuk menemukan suara mereka, Anda sudah memiliki token untuk tata kelola - ini disebut XYM. Jika Anda membaca ini, kemungkinan Anda memegangnya.

Kami sekarang mencari cara untuk memberi XYM tujuan dalam tata kelola - salah satunya adalah melalui pengenalan platform pendanaan kuadrat yang memungkinkan komunitas mendanai barang publik yang mereka rasa paling bermanfaat bagi jaringan.

Penting juga untuk memahami apa arti tata kelola dalam kaitannya dengan Symbol (setiap jaringan kripto memiliki aturannya sendiri). Meskipun kami tidak memiliki aturan yang tegas dan cepat dan ini adalah sesuatu yang akan kami bangun bersama komunitas, ada beberapa hal yang tidak boleh dibiarkan begitu saja - contoh yang bagus adalah keputusan yang sangat teknis, seperti kurva BLS yang digunakan.

Kami setuju bahwa transparansi bukanlah yang terbaik dalam sejarah proyek, dan kami mengambil langkah untuk mengatasi hal ini. Misalnya, kami akan menerbitkan laporan [transparansi yang mirip dengan ETC](https://etccooperative.org/ETC-Coop-Board-Package-January-February-2021.pdf) yang merinci pengeluaran. Langkah lain yang telah kami ambil adalah membuka semua komunikasi internal kami di Discord, serta membuat buku pegangan perusahaan kami dapat diakses publik dan open source.31: Bagaimana konsep hierarki cocok dengan konsep desentralisasi?

**31: Bagaimana konsep hierarki cocok dengan konsep desentralisasi?**

Kami membutuhkan hierarki perintah-dan-kontrol yang lebih tradisional untuk membawa kami melintasi mil terakhir untuk diluncurkan. Namun, hierarki tradisional tidak cocok dengan konsep desentralisasi, itulah sebabnya kami ingin mengembangkan organisasi kami menjadi sesuatu yang lebih konsisten dengan model Flatland.

**32: Berapa banyak dana yang tersedia untuk pengembangan Symbol & NIS1 dan dalam jangka waktu berapa?**

Semua informasi ini dapat ditemukan di blockchain. Pada tahun 2020, semua 'dana inti' (yaitu premi awal) dipindahkan ke Trust. Secara total, Trust berisi sekitar 1,6 miliar XYM dan 2,8 miliar XEM (sekitar ~630 juta USD pada harga hari ini). Ada 1,2B lebih sedikit XYM daripada XEM karena ini diubah menjadi hadiah blok untuk Symbol.

**33: Kelompok apa yang merupakan tim inti NEM dengan dana yang relatif besar? Beberapa orang Jepang memandang bahwa itu adalah salah satu risiko tim memiliki dana yang terlalu besar.**

Dibandingkan dengan sesuatu seperti EOS atau Ethereum Foundation, kumpulan dananya relatif kecil. Semua dana saat ini disimpan di Trust yang dilindungi melalui akun multisig; peran dan misi mereka adalah menggunakan dana ini 'untuk mendukung dan mengembangkan ekosistem NEM, blockchain terkait, mata uang asli, dan teknologi'. Saat ini, ini berarti pengembangan Symbol dan NIS1.

# Marketing/Branding/Partnerships

**34: Saya ingin tahu tentang rencana pemasaran masa depan.**

[Seperti yang kami jelaskan di sini](https://docs.symbolplatform.com/handbook/), adalah tanggung jawab komunitas dan Duta Besarnya untuk menghadirkan visibilitas ke proyek dan menumbuhkan ekosistem. Saat komunitas membangun proyek-proyek penting, media secara alami akan membawa visibilitas kepada mereka dan menjangkau untuk berbicara tentang proyek tersebut. Selain itu, beberapa anggota tim kami sangat aktif di media sosial dan muncul di podcast, talkshow, dan bahkan televisi.

**35: Mengapa NEM atau Symbol tidak dibicarakan di luar Jepang?**

私 た ち に は 手 掛 か り が あ り ま せ ん.

**36: Mengapa masalah branding ini tidak diselesaikan beberapa bulan yang lalu? Bagaimana proses yang menyebabkan tidak dibuatnya akun media sosial Symbol seperti yang diusulkan?**

Kami tidak dapat berbicara untuk NEM Group dan pendahulunya - namun, komunitas saat ini menyuarakan pendapat mereka melalui Twitter dan Discord. Kami mendorong Anda untuk terlibat dalam diskusi tersebut. Kami setuju ada beberapa kebingungan tentang 'NEM', secara internal dan eksternal, baik di komunitas kami maupun dengan pertukaran dan mitra. Kami mendengarkan diskusi dan memikirkan cara terbaik ke depan.

**37: Mengapa kita tidak mengikuti jejak Cardano dan men-tweet pembaruan teknologi? Contoh:** 

https://twitter.com/cardano_updates

Bot Twitter itu menerbitkan sebagian besar statistik GitHub yang tidak berarti. Kami lebih suka Anda melihat GitHub kami secara langsung.

**38: Bisakah kami membuat rangkuman mingguan semua pembaruan teknologi dalam bahasa Inggris? Mod NEM HUB kami dapat menerjemahkan ke dalam bahasa asli mereka (8 bahasa yang paling banyak digunakan, ditambah bahasa Jepang dan beberapa lainnya). NEMHUB dapat menyediakan ruang obrolan instan (Messenger), juga dapat bergabung dengan siaran langsung, secara teratur menyiarkan program NEM online. Bagaimana menurut anda?**

Komunitas kami telah mulai menerjemahkan tweet, blog, dan postingan populer melalui [akun Twitter](https://docs.google.com/document/d/1rNUdM4z0pI_BldoWoT8jkTjP9PFXBdPRyapHbLcXWEQ/edit?usp=drivesdk) mereka dan [blog yang dikelola komunitas](https://symbolblog.com/). Karena semua pekerjaan kami ada di Discord dan GitHub, komunitas dapat bekerja sama untuk melakukan pembaruan teknologi kolektif.

**39: Masih banyak orang yang menganggap XEM adalah yang utama dan XYM hanyalah bonus, kenapa tidak kita ganti logo NEM menjadi logo Symbol?**

Lihat jawaban kami untuk Pertanyaan #36.

**40: Saya pikir kita harus secara aktif memasarkan perbedaan antara NEM (NIS1) dan Symbol dan prospek masa depan mereka.**

Seperti yang dijelaskan dalam [buku pegangan](https://docs.symbolplatform.com/handbook/), NIS1 akan menjadi subRantai Simbol.

**41: Saya ingin tahu lebih banyak prospek pemasaran di masa depan.**

Sayangnya kami tidak memiliki bola kristal yang berfungsi.

**42: Di Jepang, aset kripto masih dipandang sebagai investasi, tetapi jika kita meluncurkan iklan TV dan iklan online yang menarik bagi blockchain, yang merupakan kekuatan simbol, dan mulai sekarang menanamkan citra blockchain = Symbol di Jepang , kita pasti bisa mengalahkan Ethereum. Kami menantikan strategi pemasaran Anda yang berani.**

Meskipun bukan pertanyaan, kami menghargai antusiasme dan sarannya.

**43: Bicara lebih banyak tentang DeFi.**

Kami akan. Anda dapat mengikuti akun Twitter kami [[1]](https://twitter.com/Jaguar0625)[[2]](https://twitter.com/0x6861746366574)[[3]](https://twitter.com/NCOSIGIMCITYNRE) atau bergabung dengan [Discord](https://discord.gg/xymcity) untuk mendapatkan lebih banyak pemikiran, opini, dan penelitian tentang topik DeFi.

**44: Apakah Anda berinteraksi dengan komunitas blockchain lainnya? Apakah mereka tertarik pada NEM?**

Ya. Dari kami bertiga, [Hatchet](https://twitter.com/0x6861746366574) memiliki eksposur paling banyak; umumnya, minat proyek blockchain lainnya di NEM rendah. Kami pikir ini akan meningkat seiring waktu saat kami mulai berpartisipasi dalam penelitian dan pengembangan teknologi yang digunakan di seluruh cryptocurrency (seperti zk-SNARK dan zk-Rollup) serta mulai berbicara lebih banyak tentang desain dan arsitektur mekanisme Symbol.

**45: Apa yang menurut Anda bagus tentang pendekatan Jepang terhadap NEM? Juga, menurut Anda apa yang harus dilakukan untuk menyebarkannya ke luar Jepang?**

Kami menyukai antusiasme dan eksperimentasi komunitas Jepang. Kami ingin melihat lebih banyak hal ini di seluruh dunia. Di luar itu, kami pikir lebih banyak kepemimpinan pemikiran, artikel yang ditulis dengan baik, penelitian inovatif, dan produk yang memanfaatkan Symbol dapat membawa visibilitas yang lebih baik ke proyek.

**45: Apa yang menurut Anda bagus tentang pendekatan Jepang terhadap NEM? Juga, menurut Anda apa yang harus dilakukan untuk menyebarkannya ke luar Jepang?**

Kami menyukai antusiasme dan eksperimentasi komunitas Jepang. Kami ingin melihat lebih banyak hal ini di seluruh dunia. Di luar itu, kami pikir lebih banyak pemikiran kepemimpinan, artikel yang ditulis dengan baik, penelitian inovatif, dan produk yang memanfaatkan Simbol dapat membawa visibilitas yang lebih baik ke proyek.

**46: Sudah lebih dari tiga bulan sejak Symbol diluncurkan. Namun, itu belum terdaftar di bursa sebanyak yang saya harapkan. Mengapa demikian?**

Kita tidak yakin. Pertukaran memiliki proses internal yang memungkinkan mereka untuk memprioritaskan koin berdasarkan permintaan pasar. Meskipun Binance memberikan beberapa panduan daftar untuk membantu prosesnya, tidak ada jaminan bahwa koin Anda akan terdaftar. Kami pikir Binance akan mencantumkan XYM saat mereka siap.

**47: Saya ingin tahu apakah NEM berpikir untuk masuk ke dunia NFT dalam lq Blockchain? dan mereka dapat diimplementasikan sebagai persyaratan untuk Stakin Specials for Unstake dan Stake $XYM.**

Tidak

**48: Karena jumlah kasus penggunaan untuk Nem atau simbol tidak bertambah, itu tidak dibicarakan sama sekali di berita. Tidakkah menurut Anda mungkin ada masalah dengan rencana untuk merilis berita ini?**

Tidak. Kami sangat menentang 'berita demi berita'. Ini telah menjadi masalah historis yang berulang dan lebih banyak merugikan daripada membantu NEM.

Terserah kita semua untuk mendorong adopsi Simbol - bukan hanya tim protokol. Jika Anda ingin melihat lebih banyak aktivitas di berita atau media, terlibatlah! Bicara tentang Simbol di pertemuan lokal Anda; berbicara tentang algoritma konsensus di konferensi; membangun usecases inovatif pada rantai dan menjadi salah satu pelopor awal. Jika menurut Anda kurangnya berita adalah masalah, kami mendorong Anda untuk menjadi bagian dari solusi.

**49: Saya ingin Anda membuat Simbol populer lebih cepat!**

Kami juga melakukannya! Tapi, hal-hal baik membutuhkan waktu. Bagaimana Anda ingin mewujudkannya?

**50: Apakah ada halangan untuk mempekerjakan seseorang yang berpengaruh (misalnya youtuber) yang berbicara bahasa selain bahasa Inggris untuk memperkuat komunikasi perusahaan?**

Tidak. Kami tidak membayar influencer, selebritas, atau media untuk memberikan kredibilitas palsu kepada Symbol. Ini tidak sesuai dengan etika kita. Kami ingin menumbuhkan komunitas kami secara organik dan menarik perhatian global karena utilitas dan inovasi kami.

**51: Bagaimana Anda berniat untuk meningkatkan dan memperkuat komunikasi perusahaan NEM dengan negara-negara dengan teknologi baru?**

Baik Bitcoin dan Ethereum telah membuktikan bahwa mantra “jika Anda membangunnya, mereka akan datang” adalah benar. Cara terbaik untuk meningkatkan dan memperkuat kemampuan Symbol untuk membangun dengan rantai.

**52: Apa itu perusahaan NEM?**

Kami tidak yakin, tapi itu terdengar seperti perusahaan yang menggunakan NIS1 atau Symbol.









