# REGISTRO DE LA COMUNIDAD 0x1

*Esta es la primera parte de una serie de preguntas y respuestas de la comunidad con [Gimre](https://twitter.com/NCOSIGIMCITYNRE), [Hatchet](https://twitter.com/0x6861746366574) & [Jaguar](https://twitter.com/Jaguar0625).*



# El programa SuperNodo

**01: ¿Qué está pasando con el programa SuperNode? ¿Por qué el retraso? ¿Por qué se han retrasado las recompensas de las votaciones?**

Durante el trabajo inicial de tokenomic, hubo algunas suposiciones modeladas sobre el precio y la actividad de la red que (hasta ahora) no han sido el comportamiento que hemos observado en la red actual. A la luz de esto, así como el de la nueva dirección de las subcadenas, estamos revisando nuestro diseño de tokens y mecanismos para ver si se necesitan ajustes para equilibrar mejor las recompensas y las tasas frente a la seguridad económica que proporciona la red. Las recompensas por votación y el programa SuperNode también se están revisando como parte de este esfuerzo.

Proporcionaremos un informe completo cuando hayamos terminado nuestro análisis, pero no esperen ningún nuevo pago o programa hasta que lo hayamos terminado.

**02: ¿Se trata a algunos usuarios de la red de forma diferente al resto de la comunidad? Si es así, ¿por qué?**

Sí. Hay un canal privado NGL :: SN que cuenta con unas 30-40 "ballenas". En un principio estaba pensado como un canal de corta duración para comunicar los retrasos de los proyectos con los grandes interesados, pero desde entonces ha perdido su finalidad. Tras el lanzamiento de Symbol se hizo innecesario, y dos de nosotros ya lo hemos abandonado. Va en contra de nuestros principios básicos de transparencia. Ahora pasamos todo nuestro tiempo en Discord.

# Tecnología

**03: Últimamente, Hatchet ha hablado mucho de cadenas privadas y públicas cruzadas. Cuáles son exactamente sus perspectivas, y me encantaría escuchar su opinión sobre la utilidad de la cadena cruzada XEM/XYM**.

Ver [aquí](https://docs.symbolplatform.com/handbook/) para más información; creemos que las subcadenas proporcionan una forma más limpia de manejar las redes con permisos.

**04: ¿Por qué Symbol no requiere contratos inteligentes para tener éxito?**

Symbol tiene una versión del concepto de [contratos inteligentes](https://www.fon.hum.uva.nl/rob/Courses/InformationInSpeech/CDROM/Literature/LOTwinterschool2006/szabo.best.vwh.net/smart_contracts_2.html),, al igual que Bitcoin. Específicamente, lo que Symbol no tiene es lo completo de Turing. La funcionalidad principal son los bucles. La ventaja de esto es que evita los bucles infinitos durante la verificación de las transacciones (es decir, spam). La solución de Ethereum a esto fue introducir tarifas adicionales para cada operación (llamadas gas). Cuantas más sentencias se ejecuten, mayor será el "fee".

Hay beneficios en un blockchain que no sea turing: uso predecible de los recursos; mejor análisis; uso enfocado del dominio. Dicho esto, estamos investigando activamente formas de ampliar la programabilidad de Symbol, pero aún no tenemos un camino definido. Tal vez surja una solución en algún punto intermedio.

**05: ¿En qué crees que se diferenciará el objetivo de Symbol de Layer2 en comparación con Ethereum 2.0?**

Puede haber similitudes en el enfoque (por ejemplo, los circuitos zk-Rollups y STARK), pero es demasiado pronto en la etapa de investigación para identificar las diferencias en la arquitectura y la implementación.

**06: ¿Están planeando introducir el compromiso polinómico para hacer más compacta la prueba de estado basada en el árbol de Merkle? / Kate (KZG) Compromiso**

Los árboles de Verkle (y posteriormente, los compromisos de Kate) son una de las cosas que hemos estado investigando junto con las pruebas de conocimiento cero, los zk-STARKs y los zk-Rollups. Aunque todavía no hemos tomado una decisión concreta, es una progresión natural para la “arquitectura trie” cuando pensamos en escalar la mainChain.

Se puede encontrar un buen manual sobre Kate Commitments [aquí](https://hackmd.io/@tompocock/Hk2A7BD6U), por Tom Walton-Pocock de Aztec.

**07: ¿Qué opina de la compatibilidad con EVM?**

Queda por ver cuál sería el beneficio de la compatibilidad con EVM - después de todo, ¿no se usaría Ethereum para la actividad relacionada con EVM? Un enfoque más limpio podría ser una subcadena dedicada que facilite las transacciones entre Ethereum y Symbol, con el fin de proporcionar a los LP más emparejamientos.

Es importante entender que los conceptos de Ethereum no se traducen naturalmente en Symbol: la EVM es una máquina virtual completa de Turing. Hay otras máquinas virtuales para cripto-redes, como Rusk o NeoVM. También hemos discutido otras posibilidades, como eBPF. Todavía no tenemos planes concretos para introducir una máquina virtual en Symbol, pero estamos investigando activamente.

**08: ¿Se lanzará NEM 3.0?**

No.

**09: ¿Crearán un DEX para intercambiar XEM/XYM?**

El cambio de XEM a XYM sería una tarea del proveedor de liquidez. Sí, hay un plan para llevar esta funcionalidad a Symbol con la introducción de NIS1 como subcadena (junto con el mercado correspondiente). Las soluciones a corto plazo podrían ser el uso de otras redes de liquidez, como Thorchain o Sushiswap.

**10: ¿Por qué otras cadenas no están conectadas con cadenas cruzadas a Symbol y NEM?**

Rara vez es responsabilidad de los desarrolladores de protocolos implementar la funcionalidad de las cadenas cruzadas con otras criptomonedas. Si quieres explorar los intercambios entre cadenas, la documentación aquí es un buen lugar para empezar. Un intercambio podría ser factible con SHA256d para Ethereum, Bitcoin y sus bifurcaciones relacionadas.

**11: La función de apostilla es una característica muy importante. ¿Cuándo se implementará la función de apostilla en el monedero de Symbol?**

Cualquier solicitud de característica debe ser añadida [aquí](https://github.com/symbol/symbol-desktop-wallet/issues). Aunque somos fans de la apostilla, no parece ser tan importante ya que nadie ha presentado todavía una incidencia.

**12: ¿Por qué no se abren a más discusiones técnicas?**

Dirígete a Discord: todo nuestro trabajo y las charlas del día a día son visibles públicamente; si eres desarrollador o investigador, puedes participar en nuestro canal de Proyectos o Investigación.

**13: ¿Es posible añadir funciones deterministas jerárquicas en futuros monederos?**

Ciertamente. Por favor, añade una petición de función [aquí](https://github.com/symbol/symbol-desktop-wallet/issues).

**14: ¿Tenéis ya una forma estándar de crear y gestionar NFT en Symbol, tenéis pensado hacerlo, en qué plazo, o en definitiva por ahora para los devs que trabajamos con Symbol debemos crear nuestras propias implementaciones de NFT en Symbol bajo nuestra lógica?**

Hemos observado que la comunidad ha adoptado mayoritariamente el estándar de crear mosaicos con un suministro de 1 y un hash IPFS en los metadatos. Más allá de esto, hay planes para ampliar la funcionalidad de los mosaicos para soportar metadatos únicos por unidad individual de un suministro dado, pero no hay un calendario definido.

**15: ¿Qué piensas de la cadena privada (mijin)? Quiero preguntar al core-dev.**

Nuestros caminos con TechBureau se han separado, y como nunca hemos actuado como usuarios de una cadena privada no podemos responder a esa pregunta.

**16: ¿Es posible lanzar un token en la blockchain de Symbol?**

Sí, los tokens de Symbol (como en el caso de NIS1) se denominan mosaicos. Esta denominación podría cambiar en el futuro.

**17: ¿Podemos tener un enfoque más estructurado de las versiones de los nodos? Una versión de arranque que siga a la versión del servidor en la que la actualización de arranque se publique justo después de la actualización del servidor. Con una clara distinción entre las versiones de mainnet/testnet. Es demasiado confuso en este momento, especialmente si se anuncia como una actualización del servidor 1.0.1.0 y el bootstrap está en 1.0.6, difícil de averiguar si estoy ejecutando la versión correcta.**

No. La herramienta bootstrap itera más rápido que Catapult, y sigue el esquema de versionado semántico. Catapult sigue el versionado más común para el software independiente, con una clara distinción entre las versiones de mainnet y testnet.

El versionado del servidor para testnet/mainnet se ha definido con la versión 1.0.0.0:


Tenga en cuenta que la red de pruebas no siempre tiene una compilación separada. En el caso de que no haya nuevas características que probar, se ejecutará el mismo bulild que mainnet.
**

El versionado del servidor para testnet/mainnet se ha definido con la versión 1.0.0.0:

| Descripción | Versiones |
| --- | --- |
| Ejemplo de mainnet build numbers | 1.0.0.0, 1.2.x.x, 1.4.x.x, 2.2.x.x, 3.4.x.x |
| Ejemplo de testnet build numbers | 1.1.0.0, 1.3.x.x, 1.5.x.x, 2.3.x.x, 3.5.x.x |

-   0.95 Factor = Harvesting - (95% de los Fees | Fee de la red: 5%)
    
-   0.7 Factor = Harvesting Delegado (70% de los Fees | 25% Harvester | 5% Fee de la red)
    

**


**18: ¿Cuándo construirán una herramienta que haga que el uso de los tokens sea más aplicable para la persona promedio?**

Esa herramienta se conoce comúnmente como Wallet. Puedes enviar peticiones de características [aquí](https://github.com/symbol/symbol-desktop-wallet/issues), o puedes involucrarte en el desarrollo del monedero uniéndote a la discusión en Discord.

**19: Me gustaría saber si podremos ver nft desde la aplicación Xym.**

Puedes enviarlo como una solicitud de función [aquí](https://github.com/symbol/symbol-desktop-wallet/issues).

**20: Yo estaba en NXT primero antes de estar en NEM debido a su naturaleza innovadora de la tecnología. Ambos son un pionero en su propia manera. ¿Cuál es el esfuerzo de los equipos de NEM (dev, ngl, etc.) para asegurarse de que NEM no acabe como NXT (abandonado y olvidado)?**

No pensamos abandonar Symbol o NIS1, pero es responsabilidad de todos contribuir a la cadena e impulsarla hacia un éxito colectivo. Existe un contrato social claro entre los desarrolladores de un protocolo y su comunidad, y no nos esforzaríamos por llevar a cabo otra reorganización si no tuviéramos la intención de mantener ese contrato social.

# Tokenomics y precio

**21: ¿Podemos hablar de otras mejoras en el modelo de tokenomics y de apuestas? Por ejemplo, DOT es mucho más rentable para el staker regular (no el nodo maestro) que XYM. Suponiendo una inversión de 60k, DOT genera un 12% de APY, mientras que el de Symbol es difícil incluso de calcular ya que no es consistente. Supongo que esto es parte de la tokenomics, así que ¿por qué alguien elegiría apostar por XYM en lugar de DOT?**
No se puede comparar el tokenomics de dos monedas que tienen objetivos diferentes. Su tokenomic es un marco para incentivar ciertos comportamientos en la red (por ejemplo, la participación en la acuñación de nuevos bloques o la ejecución de nodos). A medida que la red crece, la rentabilidad de participar en ella también crece. Está diseñado para curar un bucle de retroalimentación, no algo que se "ajusta" a capricho porque otra moneda es más rentable (de hecho, a menudo se quiere reajustar para asegurarse de que no se está pagando de más por la seguridad económica.

Dicho esto, actualmente estamos revisando nuestro diseño de tokenomics ahora que hemos tenido tiempo de lanzar la cadena y empezar a trabajar juntos como equipo.

En cuanto a tu punto sobre la dificultad de cálculo, la siguiente tabla presenta una estimación aproximada para una cuenta de 100K XYM que ha comenzado a cosechar poco después del lanzamiento de Symbol:

![](https://i.imgur.com/ZXQCieI.png)

*-   0.95 Factor = Harvesting - (95% de los Fees | Fee de la red: 5%)
-   0.7 Factor = Harvesting Delegado (70% de los Fees | 25% Harvester | 5% Fee de la red)*


Para el cosechador nativo, el APY para el primer año se sitúa entre el 3,2% (pesimista) y el 14,5% (optimista); para el cosechador delegado, el APY se sitúa entre el 2,3% (pesimista) y el 10% (optimista). En las condiciones actuales de nuestra red estamos observando resultados optimistas.


**22: Usted recomendó el uso de la blockchain pública de Symbol, pero hay un ingeniero japonés que ha ideado una forma de almacenar los datos en la cadena. Si esto se utiliza ampliamente, ¿cuál es su sistema de apoyo en caso de que la carga de la blockchain pública aumente y el sistema se detenga? Si puede decir que no se va a caer, por favor, explique por qué.**

Siempre ha sido posible almacenar datos "en la cadena" (después de todo, para eso está el campo de metadatos en los mosaicos). Es una cuestión de si es económicamente viable o no, y práctico desde el punto de vista de la utilidad. Dicho esto, estamos deseando ver lo que la comunidad japonesa crea con Symbol. Si se produce algún problema, trabajaremos con la comunidad para resolverlo rápidamente y publicar un parche para los nodos (por favor, únete a nuestro Discord y sigue nuestra cuenta de Twitter para cualquier actualización).

**23: Gimre dijo una vez: "No me interesa el precio". ¿Qué piensan los otros core devs sobre esto? Creo que el precio es uno de los factores más importantes a la hora de apoyar el ecosistema, incluidos los sueldos de NGL y las donaciones a los ingenieros.**

El precio es una función de la utilidad de la red. Como escribimos aquí, es responsabilidad de los distintos grupos del ecosistema trabajar juntos para hacer crecer la red (no de una parte específica). Es nuestro trabajo añadir nuevas funcionalidades a la cadena - y es el trabajo de los usuarios encontrar nuevas y creativas formas de utilizar esta funcionalidad a través de aplicaciones en la cadena. Si crees que el precio es uno de los factores más importantes para el éxito de la cadena, ven a participar y ayuda a aumentar la utilidad (o, a promover la visibilidad de Symbol).

**24: ¿Tienen algún plan para aumentar el precio? Puede hacerlo a través de la oferta y la demanda de tokens, que usted controla. El equipo puede encontrar un tercero que haga la gestión del valor de mercado. Los equipos también pueden controlar la oferta, creando deflación o inflación. ¿Por qué no contrata a un tercero para que evalúe esto por usted y le ayude? ¿Son los problemas de regulación/conformidad el obstáculo?**

Como hay varias preguntas aquí, las dividiremos por comodidad.

**¿Tienen previsto aumentar el precio?**

El precio se da en función de la utilidad de la red.

Puede hacerlo a través de la oferta y la demanda de fichas, que usted controla.

El mercado controla la oferta y la demanda, no nosotros.

Los equipos también pueden controlar la oferta, creando deflación o inflación.

Los cambios en la deflación o la inflación no son cosas que se hagan "a capricho" en respuesta a las fuerzas del mercado. Nuestra inflación es bastante pequeña, y será insignificante en el bloque 31410299. Como hemos dicho, estamos revisando nuestro tokenomics.

El equipo puede encontrar un tercero para hacer la gestión del valor de mercado. (...) ¿Por qué no contratan a un tercero para que evalúe esto por ustedes y les ayude?

Eso no es responsabilidad del equipo de protocolo, ni es algo ético para el ecosistema. Tu mercado es una respuesta directa a la salud y funcionalidad de la red, e interferir en eso anula el propósito de los mecanismos de ['exit and voice](https://en.wikipedia.org/wiki/Exit,_Voice,_and_Loyalty)" en las criptomonedas.

Si te refieres a las actividades de creación de mercado (que ayudan a reducir la dispersión entre las transacciones), puedes participar en estas actividades tú mismo como usuario utilizando programas como Hummingbot.

# Educación

**25: Sería estupendo proporcionar algunas guías básicas y ejercicios sencillos de programación para empezar con Symbol. Hay mucha documentación disponible pero no mucha para los novatos. ¿Tal vez alguien del equipo podría trabajar en esto?**

Te animamos a que hagas una petición de características específicas [aquí](https://github.com/symbol/symbol-docs/issues). También animamos a la comunidad a participar en la creación de guías - ya hay algunos recursos fantásticos [aquí](https://symbolblog.com/) y la documentación técnica tiene algunas [guías](https://docs.symbolplatform.com/guides/index.html) para empezar.

**26: Me gustaría preguntaros si tenéis pensado crear algún tipo de tutorial que nos permita ver cómo depositar en el monedero Xym, lo digo porque he buscado en varios sitios información al respecto y no la he encontrado.
**
[Ésta guía](https://docs.symbolplatform.com/guides/transfer/sending-a-transfer-transaction.html) explica cómo hacerlo a través del CLI, el SDK y el monedero.

  

# Transparencia

**27: ¿Dónde está la AMA que se prometió?**

Está aquí. Lo estás leyendo.

**28: ¿Cuál es el estado de la lista de Binance para XYM?**

Por lo general, los equipos de proyecto no tienen control sobre el tiempo que se tarda en listar una moneda en un Exchange. Estamos seguros de que Binance incluirá a XYM en la lista cuando esté preparado para ello.

**29: ¿Por qué los desarrolladores del núcleo no dan la cara? Algunos dicen que esto es malo para la confianza.**

Por favor, pregúntale a Satoshi lo que piensa. Además, el anonimato es un rasgo común entre los líderes de los proyectos: Nicolas van Saberhagen de CryptoNote; Chef Nomi y 0xMaki de Sushi; Tom Elvis Jedusor de MimbleWimble. Hoy en día, hay empresas de capital riesgo formadas exclusivamente por socios anónimos; y empresas de capital riesgo que respaldan a fundadores anónimos. Hay conferencias sobre el poder de la economía pseudónima, y algunos incluso creen que el anonimato aporta más credibilidad a tus acciones.

En resumen: la legitimidad se mide por la producción, no por la identidad. Creemos que esto no tiene ningún efecto negativo en el proyecto.

# Gobernanza

**30: Necesitamos un token de gobernanza para votar los asuntos.**

Si bien estamos de acuerdo en que los tokens de gobernanza ayudan a la liquidez y es un importante mecanismo de señalización para que los usuarios encuentren su voz, ya tienes un token para la gobernanza - se llama XYM. Si estás leyendo esto, es probable que lo tengas.

Ahora estamos buscando formas de dar a XYM un propósito en la gobernanza - una de ellas es a través de la introducción de una plataforma de financiación cuadrática que permitirá a la comunidad financiar los bienes públicos que consideren más beneficiosos para la red.

También es importante entender lo que significa la gobernanza en relación con Symbol (cada criptomoneda tiene sus propias reglas). Aunque no tenemos reglas firmes y rápidas y esto es algo que construiremos con la comunidad, hay algunas cosas que no deberían dejarse a la sabiduría de las multitudes - un gran ejemplo son las decisiones altamente técnicas, como qué curva BLS utilizar.

Estamos de acuerdo en que la transparencia no ha sido la mejor en la historia del proyecto, y estamos dando pasos para paliarlo. Por ejemplo, vamos a publicar informes de transparencia similares a los del ETC en los que se detallan los gastos. Otro paso que hemos dado es abrir toda nuestra comunicación interna en Discord, así como hacer que nuestro manual de empresa sea de acceso público y de código abierto.

**31: ¿Cómo encaja el concepto de jerarquía con el de descentralización?**

Necesitábamos una jerarquía de mando y control más tradicional para llegar a la última milla del lanzamiento. Pero, una jerarquía tradicional no encaja con el concepto de descentralización, por lo que estamos buscando evolucionar nuestra organización hacia algo que sea más coherente con el modelo de Flatland.

**32: ¿De qué fondos se dispone para el desarrollo de Symbol y NIS1 y durante qué periodo de tiempo?**

Toda esta información se puede encontrar en la cadena de bloques. En 2020, todos los "fondos básicos" (es decir, la prima inicial) se trasladaron a un fideicomiso. En total, el Fideicomiso contiene aproximadamente 1,6B XYM y 2,8B XEM (aproximadamente ~630M USD a los precios de hoy). Hay 1,2B menos de XYM que de XEM porque éstos se convirtieron en recompensas en bloque para Symbol.

  

**33: ¿Qué tipo de grupo es el equipo principal de NEM con un fondo relativamente grande? Algunos japoneses consideran que uno de los riesgos es que el equipo tenga un fondo demasiado grande.**

En comparación con algo como EOS o la Fundación Ethereum, el grupo de fondos es relativamente pequeño. Todos los fondos se mantienen actualmente en fideicomisos protegidos a través de cuentas multisig; su función y misión es utilizar estos fondos "para apoyar y desarrollar el ecosistema NEM, sus blockchains asociadas, monedas nativas y tecnologías". Actualmente, esto significa el desarrollo de Symbol y NIS1.

  

# Marketing/Marca/Asociación

**34: Quiero saber sobre los futuros planes de marketing.**

Como hemos detallado aquí, es responsabilidad de la comunidad y de sus embajadores dar visibilidad al proyecto y hacer crecer el ecosistema. A medida que la comunidad construye proyectos dignos de mención, los medios de comunicación naturalmente les darán visibilidad y se acercarán para hablar del proyecto. Además, algunos miembros de nuestro equipo son muy activos en las redes sociales y aparecen en podcasts, programas de entrevistas e incluso en la televisión.

  

**35: ¿Por qué no se habla de NEM o Symbol fuera de Japón?**

私たちには手掛かりがありません。(No tenemos ni idea)

  

**36: ¿Por qué no se resolvieron estos problemas de marca hace meses? ¿Cuál fue el proceso que llevó a no crear las cuentas de Symbol en las redes sociales como se propuso?**

No podemos hablar en nombre del Grupo NEM y sus predecesores, pero la comunidad está expresando su opinión a través de Twitter y Discord. Te animamos a participar en esos debates. Estamos de acuerdo en que hay cierta confusión sobre "NEM", tanto interna como externamente, tanto en nuestra comunidad como con los Exchanges y socios. Estamos escuchando el debate y pensando en la mejor manera de avanzar.

**37: ¿Por qué no seguimos el ejemplo de Cardano y tuiteamos las actualizaciones tecnológicas? Ejemplo: https://twitter.com/cardano_updates**

Ese bot de Twitter publica estadísticas de GitHub en su mayoría sin sentido. Preferiríamos que miraran nuestro GitHub directamente.

**38: ¿Podemos hacer un resumen semanal de todas las actualizaciones técnicas en inglés? Nuestros mods de NEM HUB pueden traducir a sus idiomas nativos (se cubren los 8 idiomas más hablados, además del japonés y otros más). NEMHUB puede proporcionar una sala de chat instantánea (Messenger), también puede unirse a la transmisión en vivo, transmitir regularmente los programas de NEM en línea. ¿Qué te parece?**

Nuestra comunidad ya ha empezado a traducir tuits, blogs y publicaciones populares a través de sus cuentas de Twitter y de los blogs gestionados por la comunidad. Como todo nuestro trabajo está en Discord y GitHub, la comunidad puede trabajar conjuntamente para hacer actualizaciones técnicas colectivas.

  

**39: Todavía hay mucha gente que piensa que XEM es el principal y XYM es sólo un extra, ¿por qué no cambiamos el logo de NEM por el de Symbol?**

Véase nuestra respuesta a la pregunta nº 36.

  

**40: Creo que deberíamos difundir activamente las diferencias entre NEM (NIS1) y Symbol y sus perspectivas de futuro.**

Como se detalla en el manual, NIS1 será una subcadena de Symbol.

  

**41: Me gustaría conocer más perspectivas de comercialización en el futuro.**

Lamentablemente, no tenemos una bola de cristal que funcione.

  
**42: En Japón, las criptomonedas todavía se ven como una inversión, pero si lanzamos anuncios de televisión y publicidad en línea que apelen a la BlockChain, que es el punto fuerte de Symbol, e inculcamos la imagen de blockchain = Symbol en Japón a partir de ahora, definitivamente podemos superar a Ethereum. Esperamos su audaz estrategia de marketing.**

Aunque no es una pregunta, agradecemos el entusiasmo y la sugerencia.

**43: Hablemos más de DeFi.**

Lo haremos. Puedes seguir nuestras cuentas de Twitter o unirte a Discord para conocer más pensamientos, opiniones e investigaciones sobre el tema de DeFi.

**44: ¿Interactúan con otras comunidades de blockchain? ¿Se interesan por NEM?**

Sí. De los tres, Hatchet tiene la mayor exposición; en general, el interés de otros proyectos de blockchain por NEM es bajo. Creemos que esto aumentará con el tiempo, a medida que empecemos a participar en la investigación y el desarrollo de tecnologías que se utilizan en todas la criptomonedas (como zk-SNARKs y zk-Rollups), así como que empecemos a hablar más sobre el diseño y la arquitectura de los mecanismos de Symbol.

**45: ¿Qué crees que tiene de bueno el enfoque de Japón sobre NEM? Además, ¿qué crees que debería hacerse para que se extienda más allá de Japón?**

Nos encanta el entusiasmo y la experimentación de la comunidad japonesa. Nos gustaría ver más de esto en todo el mundo. Más allá de eso, creemos que un mayor liderazgo de pensamiento, artículos bien escritos, investigaciones innovadoras y productos que utilicen Symbol pueden dar mayor visibilidad al proyecto.

**46: Han pasado más de tres meses desde el lanzamiento de Symbol. Sin embargo, no ha cotizado en tantos exchanges como esperaba. ¿A qué se debe?**

No estamos seguros. Las bolsas tienen un proceso interno que les permite priorizar las monedas en función de la demanda del mercado. Aunque Binance proporciona algunas directrices para ayudar en el proceso, no hay garantías de que su moneda sea listada. Creemos que Binance incluirá a XYM en la lista cuando esté preparado para ello.

  

**47: Me gustaría saber si NEM está pensando en meterse en el mundo de las NFTs dentro de la Blockchain... y que se puedan implementar como requisito para los Stakin Specials de Unstake y Stake de $XYM.**

No.

  

**48: Dado que el número de casos de uso de Nem o Symbol no ha aumentado, no se habla en absoluto de ello en las noticias. ¿No cree que puede haber un problema con el plan de publicación de estas noticias?**

No. Estamos firmemente en contra de "las noticias por las noticias". Este ha sido un problema histórico y recurrente y ha hecho más daño que ayuda a NEM.

Depende de todos nosotros impulsar la adopción de Symbol, no sólo del equipo de protocolo. Si quieres que haya más actividad en las noticias o los medios de comunicación, participa. Habla de Symbol en tu reunión local; habla del algoritmo de consenso en conferencias; crea casos de uso innovadores en la cadena y sé uno de los pioneros. Si crees que la falta de noticias es un problema, te animamos a formar parte de la solución.

**49: ¡Quiero que hagas que Symbol sea popular más rápidamente!**

Nosotros también lo queremos. Pero las cosas buenas llevan su tiempo. ¿Cómo quieres conseguirlo?

**50: ¿Hay algún impedimento para contratar a alguien influencer (un youtuber, por ejemplo) que hable otros idiomas además del inglés para amplificar la comunicación de la empresa?**

No. No pagamos a influencers, famosos o medios de comunicación para dar falsa credibilidad a Symbol. Esto no está en línea con nuestra ética. Queremos hacer crecer nuestra comunidad de forma orgánica y atraer la atención mundial por nuestra utilidad e innovación.

**51: ¿Cómo pretenden mejorar y ampliar la comunicación de la empresa NEM con los países con tecnología emergente?**

Tanto Bitcoin como Ethereum han demostrado que el mantra de "si lo construyes, vendrán" es cierto. La mejor manera de mejorar y amplificar las capacidades de Symbol es construir con la cadena.

**52: ¿Qué es una empresa NEM?**

No estamos seguros, pero eso suena a una empresa que utiliza NIS1 o Symbol.

  

