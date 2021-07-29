# [Italian] COMMUNITY LOG 0x1

Questa è la prima parte di una sessione di domande e risposte divisa in due parti con [Gimre](https://twitter.com/NCOSIGIMCITYNRE), [Hatchet](https://twitter.com/0x6861746366574) & [Jaguar](https://twitter.com/Jaguar0625).
#

# Il Programma SuperNode
**01: Cosa sta succedendo con il programma SuperNode? Perché c’è ritardo? Perché le ricompense per il sistema di voto sono state ritardate?**
Durante il lavoro iniziale sulla tokenomics, c'erano alcune ipotesi circa il prezzo e sull'attività della rete che (finora) non sono state il comportamento che abbiamo osservato sulla rete attuale. Alla luce di ciò, così come nella nuova direzione presa per le subChains, stiamo rivisitando il meccanismo di incentivi per vedere se sono necessari aggiustamenti per bilanciare meglio i premi e le commissioni rispetto alla sicurezza economica fornita dalla rete. Anche i premi per il voto e il programma SuperNode verranno rivisitati come parte di questo compito.
Forniremo un rapporto completo al termine della nostra analisi, ma non aspettarti nuovi pagamenti o programmi finché non l'avremo completata.

**02: Alcuni utenti della rete vengono trattati in modo diverso dal resto della community? Se è così, perché?**
Sì. C'è un canale privato NGL :: SN che ha circa 30-40 "whales". Originariamente doveva essere un canale di breve durata per comunicare i ritardi del progetto con le grandi parti interessate, ma da allora ha perso il suo scopo. Dopo il lancio di Symbol è diventato superfluo e due di noi lo hanno già lasciato. Va contro i nostri principi fondamentali di trasparenza. Ora stiamo spendendo tutto il nostro tempo in [Discord](https://www.disc+ord.gg/xymcity).
# Tecnologia

**03: Ultimamente, Hatchet ha parlato molto della cross-chaining di chain pubbliche e private. Quali sono esattamente le tue prospettive e mi piacerebbe sentire i tuoi pensieri sull'utilità del cross-chaining XEM/XYM.**
Vedi [qui](https://docs.symbolplatform.com/handbook/) per maggiori informazioni; pensiamo che le SubChains forniscano un modo più pulito di gestire le reti autorizzate.

**04: Perché Symbol non richiede Smart Contracts per avere successo?**
Symbol ha una versione del concetto di [Smart Contracts](https://www.fon.hum.uva.nl/rob/Courses/InformationInSpeech/CDROM/Literature/LOTwinterschool2006/szabo.best.vwh.net/smart_contracts_2.html), proprio come Bitcoin. Nello specifico, ciò che Symbol non ha è la “turing-completeness “ - la funzionalità principale è rappresentata dai loop. Il vantaggio di questo è che evita loop infiniti durante la verifica delle transazioni (es. spam). La soluzione di Ethereum a questo è stata quella di introdurre commissioni aggiuntive per ogni operazione (chiamata gas): più richieste sono eseguite, maggiore è la "commissione".
Ci sono vantaggi per una blockchain non-turing complete: come ad esempio un utilizzo prevedibile delle risorse; un’ analisi migliorata; utilizzo mirato del dominio. Detto questo, stiamo attivamente ricercando modi per estendere la programmabilità di Symbol, ma non abbiamo ancora un percorso deinito da portare avanti. Forse potrebbe emergere una soluzione [da qualche parte nel mezzo](https://www.gwern.net/Turing-complete).

**05: In che modo pensi che l'obiettivo del Layer2 di Symbol sarà diverso rispetto a Ethereum 2.0?**
Ci possono essere somiglianze nell'approccio (ad esempio, [zk-Rollups](https://docs.ethhub.io/ethereum-roadmap/layer-2-scaling/zk-rollups/) e STARK), ma è troppo presto per identificare le differenze nell'architettura e nell'implementazione.

**06: Stai pianificando di introdurre “l'impegno polinomiale” (polynomial commitment) per rendere più compatta la verifica dello stato basata su Merkle? / Kate (KZG).**
[Verkle Trees](https://math.mit.edu/research/highschool/primes/materials/2018/Kuszmaul.pdf) (e successivamente, Kate Commitments) sono una delle cose che abbiamo ricercato insieme a zero-knowledge proofs, zk-STARK e zk-Rollup. Anche se non abbiamo ancora preso una decisione concreta, sembra esser una progressione naturale per l'architettura quando pensiamo al ridimensionamento della mainChain. 
È possibile trovare un buon primer su Kate Commitments [qui](https://hackmd.io/@tompocock/Hk2A7BD6U), di Tom Walton-Pocock di [Aztec](https://aztec.network/).

**07: Cosa ne pensi della compatibilità EVM?**
Resta da vedere quale sarebbe il vantaggio della compatibilità EVM: dopo tutto, non useresti Ethereum solo per le attività relative a EVM? Un approccio più pulito potrebbe essere una subChain dedicata che faciliti le transazioni tra Ethereum e Symbol, al fine di fornire agli LP più pairs (coppie). 
È importante capire che i concetti di Ethereum non si traducono naturalmente in Symbol: L’[EVM](https://ethereum.org/en/developers/docs/evm/) è una macchina virtuale turing completa. Esistono altre macchine virtuali per reti crittografiche, come [Rusk](https://dusk.network/news/rusk-abi-rc) o [NeoVM](https://docs.neo.org/docs/en-us/basic/technology/neovm.html). Abbiamo anche discusso di altre possibilità, come [eBPF](https://www.infoq.com/articles/gentle-linux-ebpf-introduction/). Non abbiamo ancora una chiara idea per l’introduzione di una macchina virtuale in Symbol, ma siamo continuamente in ricerca su questo argomento.

**08: NEM 3.0 verrà rilasciato?**
No.

**09: Creerete un DEX per scambiare XEM/XYM?**
Scambiare XEM in XYM sarebbe compito di un fornitore di liquidità (LP). Sì, c'è un piano per portare questa funzionalità a Symbol con l'introduzione di NIS1 come subChain. Le soluzioni a breve termine potrebbero vedere l'utilizzo di altre reti di liquidità, come [Thorchain](https://thorchain.org/) o [Sushiswap](https://sushi.com/).

**10: Perché le altre catene non sono collegate con cross-chains a Symbol e NEM?**
Raramente è responsabilità degli sviluppatori di protocolli implementare funzionalità cross-chain con altre criptovalute. Se desideri esplorare gli scambi tra chains, la documentazione [qui](https://docs.symbolplatform.com/guides/secretlock/atomic-cross-chain-swap-between-NEM-public-and-private-chain.html) è un buon punto di partenza. Uno scambio potrebbe essere fattibile con SHA256d per Ethereum, Bitcoin e i relativi fork.

**11: L'apostille è una caratteristica molto importante. Quando implementerai la funzione di apostille nel portafoglio Symbol?**
Eventuali richieste dovrebbero essere aggiunte [qui](https://github.com/symbol/symbol-desktop-wallet/issues). Anche se siamo fan dell'Apostille, non sembra essere così importante in quanto nessuno ha presentato un problema.

**12: Perché non rendere le discussioni sullo sviluppo più trasparenti?**
Dirigiti verso [Discord](https://discord.gg/xymcity)- tutto il nostro lavoro e la chat quotidiana sono pubblicamente visibili; se sei uno sviluppatore o un ricercatore, puoi essere coinvolto nel nostro canale Progetti o Ricerca.

**13: È possibile aggiungere funzioni deterministiche gerarchiche nei futuri portafogli?**
Certamente. Si prega di aggiungere una richiesta di aggiunta di nuove funzionalità [qui](https://github.com/symbol/symbol-desktop-wallet/issues).

**14: Ragazzi avete già un modo standard per creare e gestire NFT su Symbol, avete intenzione di farlo, quanto presto, o in breve per ora per gli sviluppatori che lavorano con Symbol dobbiamo creare le nostre implementazioni di NFT su Symbol secondo la nostra logica?**
Abbiamo osservato che la community ha per lo più adottato uno standard di creazione di mosaici con una fornitura di 1 ed un hash IPFS nei metadati. Oltre a ciò, ci sono ulteriori piani per estendere la funzionalità del mosaico per supportare metadati univoci per singola unità di una determinata fornitura, ma non c’è nessuna timeline definita in merito.

**15: Cosa ne pensi della catena privata (mijin)?**
Le nostre strade con TechBureau si sono divise e, poiché non abbiamo mai agito come utenti di una catena distribuita privatamente, non possiamo rispondere a questa domanda.

**16: È possibile lanciare un token sulla blockchain di Symbol?**
Sì, i token Symbol (come nel caso di NIS1) sono chiamati mosaici. Questa denominazione potrebbe cambiare in futuro.

**17: Possiamo avere un approccio più strutturato ai rilasci dei nodi? Magari con una chiara distinzione tra rilasci mainnet/testnet. È troppo confuso al momento, specialmente se è annunciato come un aggiornamento al server 1.0.1.0 e il bootstrap è a 1.0.6, è difficile capire se sto eseguendo la versione corretta.**
No. Lo strumento bootstrap esegue un'iterazione più veloce di Catapult e segue lo schema del controllo della [versione semantica](https://semver.org/). Catapult segue il controllo della versione più comune per il software, con una chiara distinzione tra le versioni mainnet e testnet.
Il controllo della versione del server per testnet/mainnet è stato definito con la versione 1.0.0.0:


| Descrizione | Versioni |
| -------- | -------- |
| esempio numeri di build mainnet     | 1.0.0.0, 1.2.xx, 1.4.xx, 2.2.xx, 3.4.xx     |
| esempio di numeri di build di testnet     | 1.1.0.0, 1.3.xx, 1.5.xx, 2.3.xx, 3.5.xx     | 


*Nota che testnet non ha sempre una build separata. Nel caso in cui non ci siano nuove funzionalità da testare, eseguirà la stessa build di mainnet.*

**18: Quando creerai uno strumento che renda l'utilizzo dei token più applicabile alla persona media?**
Questo strumento è comunemente noto come wallet. Puoi inviare richieste di aggiuntà di nuove funzionalità [qui](https://github.com/symbol/symbol-desktop-wallet/issues), oppure puoi seguire lo sviluppo del wallet partecipando alla discussione su [Discord](https://discord.gg/xymcity).

**19: Vorrei sapere se saremo in grado di vedere nft dall'app Xym.**
Puoi fare una richiesta di aggiunta di nuove funzionalità [qui](https://github.com/symbol/symbol-desktop-wallet/issues).

**20 Ero in NXT prima di NEM: entrambi sono pionieri a modo loro. Qual è lo sforzo fatto dai team NEM (dev, ngl, ecc.) per assicurarsi che NEM non finisca come NXT (abbandonato e dimenticato)?**
Non abbiamo intenzione di abbandonare Symbol o NIS1, ma è responsabilità di tutti contribuire alla blockchain e guidarla verso un successo collettivo. C'è un chiaro contratto sociale tra gli sviluppatori di un protocollo e la sua community - e non saremmo passati attraverso lo sforzo di un'altra riorganizzazione se non avessimo intenzione di sostenere quel contratto sociale.
# Tokenomics e prezzo

**21: Possiamo discutere ulteriori miglioramenti alla tokenomics e al modello di staking? Ad esempio, DOT è molto più redditizio per lo staking regolare (non per il master node) rispetto a XYM. Supponendo un investimento di 60k, DOT genera il 12% di APY, mentre Symbol è difficile anche da calcolare in quanto non è coerente. Presumo che questo faccia parte della tokenomics, quindi perché qualcuno dovrebbe scegliere XYM invece di DOT?**
Non puoi confrontare la tokenomics di due monete che hanno obiettivi diversi. La tua tokenomics è un framework per incoraggiare determinati comportamenti nella rete (ad esempio, la partecipazione al minting di nuovi blocchi o nodi in esecuzione). Man mano che la rete cresce, cresce anche la redditività della partecipazione alla rete. È progettato per curare un ciclo di feedback, non qualcosa che "venga aggiustato" perché un'altra moneta è più redditizia (in effetti, spesso vuoi riadattarti per assicurarti di non pagare troppo [sicurezza economica](https://drive.google.com/file/d/1pwt-EdnjhDLc_Mi2ydHus0_Cm14rs1Aq/view)).
Detto questo, stiamo attualmente rivedendo il nostro modello di tokenomics ora che abbiamo avuto il tempo di lanciare la chain e iniziare a lavorare insieme come una squadra.
Per quanto riguarda la difficoltà di calcolo, la tabella seguente presenta una stima approssimativa per un account di 100K XYM che ha iniziato a raccogliere poco dopo il lancio di Symbol:


| Mesi di raccolta | Raccolta nativa (fattore 0,95) ottimista | Raccolta delegata (fattore 0,7) Ottimista | Raccolta nativa (fattore 0,95) pessimista | Raccolta delegata (fattore 0,7) pessimista |
| ---------------- | ---------------------------------------- | ----------------------------------------- | ----------------------------------------- | ------------------------------------------ |
| 1                | 1094                                     | 806                                       | 182                                       | 134                                        |
| 2                | 2553                                     | 1881                                      | 547                                       | 403                                        |
| 3|	3775	|2782	|721	|531
4|	4997	|3682	|1070	|789
6|	7563	|5573	|1587	|1169
12|	14507	|10689	|3208	|2363

•	Fattore 0,95 = Raccolta - (95% delle commissioni | 5% Commissione di rete)
•	Fattore 0,7 = Raccolta delegata (70% delle commissioni | 25% Harvester | 5% Commissione di rete)
________________________________________
Per l’harvester nativo, l'APY per il primo anno è compreso tra il 3,2% (pessimista) e il 14,5% (ottimista); per la mietitrice delegata, l'APY è compreso tra il 2,3% (pessimista) e il 10% (ottimista). Nelle nostre attuali condizioni di rete, osserviamo risultati ottimistici.

**22: Hai consigliato di utilizzare la blockchain pubblica di Symbol, ma c'è un dev giapponese che ha escogitato un modo per archiviare i dati sulla chain. Se questo è ampiamente utilizzato, qual è il tuo sistema di supporto nel caso in cui il carico della blockchain pubblica aumenti e il sistema si fermi? Se puoi dire che non andrà down, perché?**
È sempre stato possibile memorizzare i dati "on-chain" (dopotutto, è a questo che serve il campo dei metadati nei mosaici). È una questione se sia economicamente fattibile e pratico dal punto di vista dell'utilità. Detto questo, non vediamo l'ora di scoprire cosa creerà la community giapponese con Symbol. In caso di problemi, collaboreremo con la community per valutare rapidamente e rilasciare una patch per i nodi (unisciti al nostro [Discord](https://www.discord.gg/xymcity) e segui il nostro [Account Twitter](https://www.twitter.com/NEMOfficial) per eventuali aggiornamenti).

**23: Gimre una volta ha detto: "Non sono interessato al prezzo". Cosa ne pensano gli altri sviluppatori principali di questo? Penso che il prezzo sia uno dei fattori più importanti nel sostenere l'ecosistema, compresi gli stipendi NGL e le donazioni per i devs.**
Il prezzo è una funzione dell'utilità della rete. Come abbiamo scritto [qui](https://docs.symbolplatform.com/handbook/), è responsabilità dei vari gruppi nell'ecosistema lavorare insieme per far crescere la rete (non una parte specifica). È nostro compito aggiungere nuove funzionalità alla chain ed è compito degli utenti trovare modi nuovi e creativi per utilizzare questa funzionalità attraverso applicazioni su chain. Se ritieni che il prezzo sia uno dei fattori più importanti per il successo della rete, vieni coinvolto e contribuisci ad aumentare l'utilità (o a promuovere la visibilità di Symbol).

**24: Hai in programma di aumentare il prezzo? Puoi farlo attraverso l'offerta e la domanda del token, che controlli. Il team può trovare una terza parte per la gestione del valore di mercato. I team possono anche controllare l'offerta, creando deflazione o inflazione. Perché non assumi una terza parte per valutare questo per te e aiutarti? Le questioni di regolamentazione sono l'ostacolo?**
Poiché ci sono più domande qui, le suddivideremo per comodità.
> Hai intenzione di aumentare il prezzo?
> 
Vedi sopra - il prezzo è una funzione dell'utilità della rete.
> Puoi farlo attraverso l'offerta e la domanda di token, che controlli.
> 
Il mercato controlla la domanda e l'offerta, non noi.
I team possono anche controllare l'offerta, creando deflazione o inflazione.
Le modifiche alla deflazione o all'inflazione non sono cose che si fanno "per capriccio" in risposta alle richieste di mercato. La nostra inflazione è piuttosto piccola e diventerà trascurabile al blocco 31410299. Come abbiamo affermato, stiamo effettuando una revisione della nostra tokenomics.
> Il team può trovare una terza parte per la gestione del valore di mercato. (…) Perché non assumi una terza parte per valutare questo per te e aiutarti?
> 
Questa non è responsabilità del team del protocollo, né è una cosa etica per l'ecosistema. Il tuo mercato è una risposta diretta alla salute e alla funzionalità della rete ed interferire con ciò vanifica lo scopo del meccanismo di '[exit and voice](https://en.wikipedia.org/wiki/Exit,_Voice,_and_Loyalty)' nelle reti crittografiche.
Se stai parlando di attività di market making (che aiuta a ridurre la diffusione tra le transazioni), puoi impegnarti in queste attività come utente utilizzando programmi come [Hummingbot](https://docs.hummingbot.io/miner/liquidity-mining/current-rewards&terms/).

# Formazione
**25: Sarebbe bello fornire alcune guide di base e semplici esercizi di programmazione per iniziare con Symbol. C'è molta documentazione disponibile ma non molta per i principianti. Forse qualcuno nel team sarebbe in grado di lavorare su questo?**
Ti invitiamo a fare una richiesta di richiesta di aggiunta di materiale [qui](https://github.com/symbol/symbol-docs/issues). Incoraggiamo anche la community a partecipare alla creazione di guide: ci sono già alcune fantastiche risorse [qui](https://symbolblog.com/) e la documentazione tecnica ha alcune [guide](https://docs.symbolplatform.com/guides/index.html) per iniziare.

**26: Vorrei chiederti se hai intenzione di creare una sorta di tutorial che ci permetta di vedere come depositare nel portafoglio Xym, dico questo perché ho cercato in diversi posti informazioni a riguardo e non l'ho trovato.**
[Questa guida](https://docs.symbolplatform.com/guides/transfer/sending-a-transfer-transaction.html) spiega come farlo attraverso la CLI, l'SDK e attraverso il wallet.
# Trasparenza

**27: Dov'è l'AMA che è stato promesso?**
È qui. Lo stai leggendo.

**28: Qual è lo stato dell'elenco Binance XYM?**
In genere, i team del progetto non hanno alcun controllo sul tempo necessario per quotare una moneta in uno scambio. Siamo sicuri che Binance elencherà XYM quando sarà pronto.

**29: Perché gli sviluppatori principali non mostrano la loro faccia? Alcuni dicono che questo è un male per la fiducia.**
Per favore chiedi a Satoshi cosa ne pensa. Inoltre, l'anonimato è un tratto comune tra i responsabili del progetto -[Nicolas van Saberhagen di CryptoNote](https://en.wikipedia.org/wiki/CryptoNote); [Chef Nomi](https://coinmarketcap.com/alexandria/people/chef-nomi) e [0xMaki](https://twitter.com/0xMaki) di sushi; [Tom Elvis Jedusor di MimbleWimble](https://scalingbitcoin.org/papers/mimblewimble.txt). Oggi ci sono imprese di capitale di rischio costituite [esclusivamente di partner anonimi](https://www.egirlcapital.com/); e società di venture capital che sostengono fondatori anonimi. Ci sono lezioni sul potere dell’[economia pseudonima](https://www.youtube.com/watch?v=urtXRg9Nl3k), e alcuni addirittura credono l'anonimato porta più [credibilità alle azioni](https://twitter.com/MikeAbundo/status/1342258232610312192?s=20).
In sintesi, si misura la fiducia in base all'output, in base al lavoro svolto, non all'identità. Riteniamo che questo non abbia alcun effetto negativo sul progetto.
# Governance
**30: Abbiamo bisogno di un token di governance per votare in merito ad i problemi.**
Siamo d'accordo che i [token di governance aiutano ad aumentare la liquidità](https://insights.deribit.com/market-research/why-i-have-changed-my-mind-on-tokens/) ed è un importante meccanismo di voto per consentire agli utenti di esprimere la propria voce, ma hai già un token per la governance: si chiama XYM. Se stai leggendo questo, è probabile che tu lo abbia.

Stiamo ora cercando modi per dare a XYM uno scopo nella governance: uno di questi è attraverso l'introduzione di una piattaforma di finanziamento quadratico che consentirà alla community di finanziare beni pubblici che ritengono più vantaggiosi per la rete.

È anche importante capire cosa significa governance rispetto a Symbol (ogni cripto-rete ha le sue regole). Anche se non abbiamo regole fisse e veloci e questo è qualcosa che costruiremo con la community, ci sono alcune cose che non dovrebbero essere lasciate a “ciò a cui la folla crede sia giusto”: un ottimo esempio sono le decisioni altamente tecniche, come quale curva BLS usare.

Siamo d'accordo che la trasparenza non è stata la migliore nella storia del progetto e stiamo facendo passi da gigante per alleviare questo problema. Ad esempio, [pubblicheremo rapporti di trasparenza simili a ETC](https://etccooperative.org/ETC-Coop-Board-Package-January-February-2021.pdf). Un altro passo avanti che abbiamo fatto è l'apertura di tutta la nostra comunicazione interna in Discord, oltre a rendere il nostro manuale accessibile al pubblico e open source.

**31: In che modo il concetto di gerarchia si adatta al concetto di decentramento?**
Avevamo bisogno di una gerarchia di “comando e controllo” più tradizionale per farci attraversare l'ultimo miglio per il lancio. Ma una gerarchia tradizionale non si adatta al concetto di decentralizzazione, motivo per cui stiamo cercando di far evolvere la nostra organizzazione in qualcosa che sia più coerente con il [Flatland model](https://www.researchgate.net/publication/282395703_Valve's_Way). 

**32: Quanti fondi sono disponibili per lo sviluppo di Symbol e NIS1 e in quale periodo di tempo?**
Tutte queste informazioni possono essere trovate nella blockchain. Nel 2020, tutti i "fondi fondamentali" (ossia il premine iniziale) sono stati trasferiti in un Trust. In totale, il Trust contiene circa 1,6 miliardi di XYM e 2,8 miliardi di XEM (circa ~ 630 milioni di dollari ai prezzi di oggi). Ci sono 1,2 miliardi di XYM in meno rispetto a XEM perché sono stati convertiti in ricompense di blocco per il Symbol.

**33: Non credi che gli sviluppatori di NEM abbiano troppi fondi? Alcuni giapponesi ritengono che sia uno dei rischi che la squadra abbia un fondo troppo grande.**
Rispetto a qualcosa come EOS o Ethereum Foundation, il pool di fondi è relativamente piccolo. Tutti i fondi sono attualmente detenuti in Trust protetti tramite conti multisig; il loro ruolo e la loro missione è utilizzare questi fondi "per supportare e sviluppare l'ecosistema NEM, le blockchain associate, le valute e le tecnologie native". Attualmente, questo significa lo sviluppo di Symbol e NIS1.
# Marketing/Branding/Partnership
34: Voglio conoscere i piani di marketing futuri.
[Come abbiamo è stato illustrato qui](https://docs.symbolplatform.com/handbook/), è responsabilità della community e dei suoi Ambassador dare visibilità al progetto e far crescere l'ecosistema. Man mano che la community costruisce progetti degni di nota, i media offriranno naturalmente loro visibilità e si metteranno in contatto per parlare del progetto. Inoltre, alcuni membri del nostro team sono molto attivi sui social media e appaiono su podcast, talkshow e persino in televisione.

**35: Perché non si parla di NEM o Symbol al di fuori del Giappone?**
私 た ち に は 手 掛 か り が あ り ま せ ん.

**36: Perché questi problemi di branding non sono stati risolti mesi fa? Qual è stato il processo che ha portato a non creare account sui social media Symbol come proposto?**
Non siamo in grado di parlare a nome di NEM Group e dei suoi predecessori, tuttavia la community sta attualmente esprimendo la propria opinione tramite Twitter e Discord. Ti invitiamo a partecipare a tali discussioni. Siamo d'accordo che c'è una certa confusione su "NEM", internamente ed esternamente, sia nella nostra community che con gli exchange ed i partner. Ascoltiamo la discussione e pensiamo al modo migliore per andare avanti.

**37: Perché non seguiamo l'esempio di Cardano e twittiamo gli aggiornamenti tecnici?** Esempio: https://twitter.com/cardano_updates
Quel bot di Twitter pubblica statistiche GitHub per lo più prive di significato. Preferiremmo che tu guardassi direttamente il nostro GitHub.

**38: Possiamo produrre un riepilogo settimanale di tutti gli aggiornamenti tecnici in inglese? I nostri mod NEM HUB possono tradurli nelle loro lingue native (le 8 lingue più parlate al mondo, oltre al giapponese e molte altre). NEMHUB può fornire una chat room istantanea (Messenger), può anche partecipare e live e trasmettere regolarmente programmi NEM online. Cosa ne pensi?**
La nostra community ha già iniziato a tradurre tweet, blog e post popolari tramite sia i [loro account Twitter](https://docs.google.com/document/d/1rNUdM4z0pI_BldoWoT8jkTjP9PFXBdPRyapHbLcXWEQ/edit?usp=drivesdk) e tramite i [blog gestiti dalla community](https://symbolblog.com/). Poiché tutto il nostro lavoro è in Discord e GitHub, la community è in grado di collaborare per eseguire aggiornamenti in merito allo sviluppo.

**39: Ci sono ancora molte persone che pensano che XEM sia il principale e XYM sia solo un bonus, perché non cambiamo il logo NEM con il logo Symbol?**
Vedi la nostra risposta alla domanda #36.

**40: Penso che dovremmo paragonare attivamente le differenze tra NEM (NIS1) e Symbol e le loro prospettive future.**
Come dettagliato nel nostro [manuale](https://docs.symbolplatform.com/handbook/), NIS1 sarà una subChain di Symbol.

**41: Vorrei conoscere più prospettive di marketing future.**
Purtroppo non abbiamo una sfera di cristallo funzionante.

**42: In Giappone, le criptovalute sono ancora viste come un investimento, ma se lanciamo spot televisivi e pubblicità online che fanno appello alla blockchain, che è la forza di Symbol, e instilliamo l'immagine della blockchain = Symbol in Giappone d'ora in poi, possiamo sicuramente battere Ethereum. Non vediamo l'ora di vedere una forte strategia di marketing.**
Anche se non è una domanda, apprezziamo l'entusiasmo e il suggerimento.

**43: Parla di più sulla DeFi.**
Lo faremo. Puoi seguire i nostri account Twitter [[1]](https://twitter.com/Jaguar0625)[[2]](https://twitter.com/0x6861746366574)[[3]](https://twitter.com/NCOSIGIMCITYNRE) o unirti a [Discord](https://discord.gg/xymcity) per ulteriori pensieri, opinioni e ricerche sul tema della DeFi.

**44: Interagisci con altre community blockchain? Si interessano all’ecosistema NEM?**
Sì. Di noi tre, [Hatchet](https://twitter.com/0x6861746366574) ha la maggiore esposizione; generalmente, l'interesse di altri progetti blockchain in NEM è basso. Riteniamo che questo aumenterà nel tempo quando inizieremo a partecipare alla ricerca e allo sviluppo di tecnologie utilizzate nel mondo delle criptovalute (come zk-SNARK e zk-Rollups) e inizieremo a parlare di più del modello e dell'architettura di Symbol.

**45: Cosa pensi ci sia di buono nell'approccio del Giappone a NEM? Inoltre, cosa pensi si dovrebbe fare per diffonderlo oltre il Giappone?**
Amiamo l'entusiasmo e la sperimentazione della community giapponese. Ci piacerebbe vedere più di questo in tutto il mondo. Oltre a ciò, articoli ben scritti, ricerca innovativa e prodotti che utilizzano Symbol possano dare una migliore visibilità al progetto.

**46: Sono passati più di tre mesi dal lancio di Symbol. Tuttavia, non è stato listato su tutti gli exchange come avevo sperato. Perché?**
Non ne siamo sicuri. Gli exchanges hanno un processo interno che consente loro di dare la priorità alle monete in base alla domanda del mercato. Nonostante Binance fornisce alcune [linee guida per la quotazione](https://www.binance.com/en/blog/421499824684902218/Binance-Listing-Tips-from-CZ) per aiutare il processo, non ci sono garanzie che la mineta in questione venga efettivamente listata. Pensiamo che Binance listerà XYM quando saranno pronti.

**47: Vorrei sapere se NEM sta pensando di entrare nel mondo degli NFT all'interno di lq Blockchain e se possono essere implementati come requisito per Stakin Specials for Unstake e Stake of $XYM.**
No.

**48: Dal momento che il numero di casi d'uso per Nem o Symbol non è aumentato, (non se ne parla affatto nelle notizie). Non pensi che ci possano esser problemi sotto il punto di vista delle pubblicazioni delle informazioni?**
No. Siamo fermamente contrari alle "notizie per far notizia". Questo è stato un problema storico e ricorrente e ha fatto più male che aiuto a NEM.
Sta a tutti noi guidare l'adozione di Symbol, non solo il team del protocollo. Se desideri vedere più attività nelle notizie o nei media, partecipa! Parla di Symbol ad i tuo meetups locali; parla dell'algoritmo di consenso alle conferenze; costruisci casi d'uso (uses case) innovativi sulla chain e sii uno dei primi pionieri. Se pensi che la mancanza di notizie sia un problema, ti invitiamo a far parte della soluzione.

**49: Voglio che Symbol diventi più popolare il prima possibile!**
Anche noi! Ma le cose buone richiedono tempo. Come vuoi che ciò accada?

**50: C'è qualche impedimento ad assumere influencers (uno youtuber per esempio) che parli lingue diverse dall'inglese per amplificare la comunicazione aziendale?**
No. Non paghiamo influencers, celebrità o media per dare falsa credibilità a Symbol. Questo non è in linea con la nostra etica. Vogliamo far crescere la nostra community in modo organico e attirare l'attenzione globale grazie alla nostra utilità e innovazione.

**51: Come intendi migliorare e amplificare la comunicazione di NEM con i paesi tecnologicamente emergenti?**
Sia Bitcoin che Ethereum hanno dimostrato quanto sia vero il mantra di "se lo costruisci, arriveranno". Il modo migliore per migliorare e amplificare le capacità di Symbol è lo sviluppo della chain e costruire use cases su essa.

**52: Che cos'è NEM?**
Non ne siamo sicuri, ma sembra sia un'azienda che utilizzi NIS1 o Symbol.





