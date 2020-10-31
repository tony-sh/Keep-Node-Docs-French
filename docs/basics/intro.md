# Introduction à tBTC & Keep Network


## DeFi
La finance décentralisée (DeFi) est un système de services et de produits financiers ouverts et interconnectés, construit et exploité sur le réseau Ethereum. D'ici juillet 2020, près de 4 milliards de dollars sont impliqués dans toutes les applications DeFi offrant des prêts, des jetons, des produits dérivés, des échanges via des contrats intelligents décentralisés. Ce volume continue de croître.

Les protocoles DeFi ont une structure modulaire qui leur permet d'interagir les uns avec les autres, créant un système de plus en plus complexe. Étant donné que les produits DeFi sont du code qui réside sur un réseau blockchain comme Ethereum, ils ne peuvent jamais être désactivés ou masqués à quiconque souhaite les utiliser. Ainsi, toute personne ayant accès à Internet peut bénéficier de prêts, de produits financiers complets, d'opportunités d'épargne, d'investissement et de négociation sur DeFi.

## Intentions tBTC
Malgré la croissance exponentielle des projets dans DeFi et Ethereum, le bitcoin représente toujours les deux tiers du volume total de crypto-monnaie dans le monde.

Comme Ilyas Khatsis présente tBTC sur son [blog] (https://medium.com/@iliashatzis/could-bitcoin-on-defi-displace-banks-yes-4c0ad99f0da4):
> «Bitcoin DeFi est le rêve d'un bitcoiner. Nous pouvons rêver devenu réalité et le nouveau projet tBTC amènera Bitcoin dans le monde DeFi.
> Bitcoin a le potentiel de transformer DeFi de manière spectaculaire, et l'équipe Keep le comprend. »

L'équipe Keep a lancé tBTC, un système de stockage décentralisé, sécurisé et assuré pour les bitcoins dans les jetons TBTC Ethereum ERC-20, avec un taux de 1: 1 pour BTC. Les détenteurs de Bitcoin qui souhaitent dépenser leur BTC sur Ethereum et DeFi ne doivent pas faire confiance aux dépositaires (signataires) car les signataires doivent déposer une garantie supérieure à la valeur du BTC qu'ils détiennent.

?> Excellente [vidéo] (https://www.youtube.com/watch?v=cfmQiArg3B8) à ce sujet de Artem # 4718 sur Discord.

Les signataires sont choisis au hasard dans le plus grand réseau de signataires et travaillent par groupes de trois. La garantie garantit que le comportement des signataires dans le système reste équitable, avec le risque de perdre leur garantie en cas de fraude ou de garantie insuffisante. Si les signataires déplacent des fonds sans autorisation, laissant plus de TBTC en stock que de BTC, le système confisquera leur garantie afin d'acheter et de détruire l'équivalent TBTC du marché, équilibrant ainsi le TBTC et le BTC stockés.

<p align = "center">
  <img width = "619" alt = "Beacon" src = "https://user-images.githubusercontent.com/68087535/88100735-57075f80-cb73-11ea-996f-ec2d9590b073.png">
</p>


## Keep Network

tBTC est une application chez [Keep Network] (https://keep.network) que Ben Longstaff a donné une excellente [description] (https://medium.com/@ben_longstaff/secure-multi-party-computation -smpc-expliqué-visuellement-ecde155fc7c0):

> "Keep Network a l'intention de devenir une solution de confidentialité pour stocker en toute sécurité les données hors du réseau, tout en développant considérablement les fonctionnalités des contrats intelligents et l'adoption massive de la technologie blockchain."

Keep Network est une solution de confidentialité qui stocke de petites quantités de données distribuées, telles qu'une clé privée, et maintient la communication inter-chaîne. Les Keeps sont des contrats intelligents qui permettent à d'autres contrats intelligents d'interagir en toute sécurité avec les données personnelles. Ils sont construits sur l'algorithme ECDSA, pris en charge par de nombreuses chaînes de blocs de premier plan, et facilitent la signature de groupes décentralisés à l'aide de signatures à seuil multipartite.

Keep Network at [Messari] (https://messari.io/article/announcement-messari-adds-11-new-disclosures-registry-participants-surpassing-50-members) est un membre enregistré ouvert. En rejoignant ce registre, ces projets se sont engagés à accroître le niveau de transparence des crypto-actifs grâce à la divulgation continue.

[Keeps Grants Explorer] (https://explorer.keep-grants.info/) par MutedTommy # 3155 (dans Discord) garde une trace des subventions allouées à KEEP en jetons.

### noeud t-ECDSA

T-ECDSA Keep assure la sécurité des transactions avec plusieurs clés privées détenues par plusieurs signataires. La signature décentralisée est effectuée à l'aide de sMPC (Secure Multiparty Computing) pour calculer sur des clés partagées sans les exposer. La responsabilité des signatures est partagée et nécessite un certain nombre de participants pour créer une signature.

En général, cela fonctionne comme ceci: le contrat intelligent Ethereum demande au Keep Network d'ouvrir un nouveau t-ECDSA Keep. Ce magasin est géré par un groupe de signataires sélectionnés au hasard dans le cluster sMPC, un plus grand réseau de signataires. Ces signataires utilisent t-ECDSA pour générer une clé et fournir une signature. Les signataires peuvent tout signer, y compris les transactions blockchain. Un contrat intelligent Ethereum peut demander à Keep de signer une transaction sur n'importe quelle blockchain basée sur ECDSA, Bitcoin n'est que l'un d'entre eux.

Ce mécanisme est fiable car les signataires sont indépendants; ce sont des personnes et des organisations qui ont lancé un nœud avec un cluster sMPC.

<p align = "center">
  <img width = "319" alt = "Beacon" src = "https://user-images.githubusercontent.com/68167410/88845610-05ca2200-d1aa-11ea-9d8b-400516fed25c.png">
</p>

### Nœud de balise aléatoire

Random Beacon est une autre partie du réseau: un outil décentralisé pour sélectionner au hasard les signataires d'une certaine manière. Cette balise est BLSThreshold Relay et ne peut être ni contrôlée ni manipulée. C'est une source fiable d'aléa pour la sélection de groupe. Personne ne sait qui seront les signataires, y compris les signataires eux-mêmes, jusqu'à ce qu'ils soient choisis par une balise aléatoire. Cela garantit que les signataires ne peuvent pas s'entendre pour voler des fonds ou attaquer le réseau, c'est pourquoi le véritable caractère aléatoire fourni par la balise est si important.

** Random Beacon et t-ECDSA Keeps core sur le réseau Keep. **



***

** Sources et informations utiles: **
- [Bitcoin sur DeFi pourrait-il déplacer les banques? Oui] (https://medium.com/@iliashatzis/could-bitcoin-on-defi-displace-banks-yes-4c0ad99f0da4) par Ilias Hatzis
- [Bridging Bitcoin and Ethereum] (https://blog.keep.network/bridging-bitcoin-and-ethereum-b2f9923630a7) sur le blog Keep Network
- [Secure Multiparty Computation] (https://medium.com/@ben_longstaff/secure-multi-party-computation-smpc-explained-visually-ecde155fc7c0) par Ben Longstaff
- [Construire des ponts entre les blockchains avec tECDSA Keep] (https://blog.keep.network/building-bridges-between-blockchains-with-t-ecdsa-keeps-e58d6debb8fd) par Piotr Dyraga du blog Keep Network
- [Staking Documentation] (https://keep-network.gitbook.io/staking-documentation/) de la documentation Keep Network
- [Présentation technique du tBTC] (https://tbtc.network/developers/tbtc-technical-system-overview/) sur le site Web du tBTC
- [Que contient une balise] (https://blog.keep.network/whats-in-a-beacon-12c34b0bc078) par Antonio Salazar Cardozo du blog Keep Network
- [Pourquoi la confiance aléatoire est-elle si importante?] (Https://blog.keep.network/why-is-trusted-randomness-so-important-c22de1c1c5ee) par Antonio Salazar Cardozo du blog Keep Network
- [Threshold ECDSA - Multi-signatures plus sûres et plus privées] (https://blog.keep.network/threshold-ecdsa-safer-more-private-multi-signatures-51153f3e9ed2) par Antonio Salazar Cardozo du blog Keep Network sur Conservez la présentation du développeur Piotr Dyraga sur le seuil-ECDSA de San Francisco Blockchain Week 2018.
- [Defi expliqué] (https://decrypt.co/resources/defi-decentralized-finance-explained-guide-learn) par Decrypt.co
- [Qu'est-ce que Defi] (https://defipulse.com/blog/what-is-defi/) par Defipulse
- [Keep promo video] (https://www.youtube.com/watch?v=h2IErqf-VrQ) par Lelka Bo dans Discord Design Channel
- [TBTC: A New Sidechain Design for Bitcoin] (https://insights.deribit.com/market-research/a-new-sidechain-design-for-bitcoin/) par Su Zhu dans Deribit Insights
- Les images proviennent de SpaceWalker (Discord Design Channel), [Ilias Hatzis] (https://medium.com/@iliashatzis) (de son histoire), Keep Team (Discord Design Channel).

---
`Source de la documentation officielle de Keep Team, éditée et ajoutée par la communauté. '[Source] (https://keep-network.gitbook.io/staking-documentation/) `

ʻAuteurs: Ramaruro, EstebanK`
`Traduction: Evelyn`
