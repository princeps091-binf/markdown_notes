# Rencontre avec et Frederic sur la Blockchain

## Introduction a la blockchain par une petite histoire (inspire de la video 3Brown1Blue)

Imaginons un groupe de personnes echangeant biens et services de maniere reguliere. Pour rendre leurs echanges plus efficaces et transparents ils decident de garder un livre de comptes commun, consultable par tous. Cette exercice presente une serie de challenges pour garantir une retranscription fidele des transactions effectuees sans pour autant dependre seulement sur l'honnetete et la bonne volonte des membres.

Evidement n'importe quel membre est authorise a effectuer une transaction, mais la premiere difficulte est comment garantir qu'une transaction a bien ete effectuee par un membre et n'a pas ete frauduleuse? Pour ce premier eceuil, on solicitera une signature digitale qui attachera a chaque transaction un identifiant unique produit par un code secret (connu seulement du membre effectuant le paiemement et appelee clef privee) et un "descriptif" de la transaction. Pour valider cette transaction, le receveur de ce paiement peut utiliser cette identifiant unique avec un code publique attache au payeur (consultable par tous les membres et appelee clef publique) pour valider l'authenticite de cette transaction (identifiant de la transaction produit par la clef privee connu du seul payeur). Une autre composante importante de cette procedure, est qu'a aucun moment le payeur n'a eu besoin de partager son code prive. Sans etre anonyme, cette procedure offre un pseudonymat en mesure de masquer l'identite reelle du payeur.

Outre la capacite de garantir l'authenticite de la transaction sans avoir a partager son identite reelle (paiement bien effectue par les membres concernes), comment s'assurer que ces paiements sont legitimes? Comment s'assurer que les membres ne depensent pas plus qu'ils ne possedent sur leurs comptes respectifs? Traditionellement, cette validation est effectuee par une tierce partie, a savoir nos banques qui vont s'assurer que la balance de nos comtpes est compatible avec les paiements que l'on desire faire et bloquer la transaction si cela n'est pas le cas. Neanmoins l'introduction d'une tierce partie impose une forme de foi en cette entite exterieure, et les evenements recents ont plus que mis a mal le peu de croyance que l'on pouvait avoir en nos banques. 

Donc pour couper cette dependance au banques pour cet aspect precis de nos transactions il serait ideal d'avoir un systeme qui ne dependrait que des membres de cette communaute d'echange et qui minimiserait le risque de fraude. Comment donc maintenir un historique de nos transactions afin de s'assurer d'avoir une balance des comptes de chacun des membres sans pour autant dependre d'une banque? La reponse est de faire que chacun des membres ait son propre historique de toutes les transactions effectuees au sein de la communaute.

Cette strategie requiert que chacun des membres desirant effectuer une transaction, la declare afin que tous les membres puissent mettre a jour leur historiques respectif et valider la legitimite de cette transaction a lumiere de la balance des comptes au moment de la transaction. Cette etape requiert que tous les membres de cette communaute d'echange aient simultanement la meme version de l'historique des transactions, qu'il y ait un consensus sur l'etat actuel de la balance des comptes. L'innovation majeure de la blockchain est d'avoir proposer une methode pour permettre un tel consensus permetant une mise a jour coordonnee de l'historique des transactions et de la balance des comptes qui en decoule.

Sans rentrer dans le detail de cette methode, la blockchain originellement decrite par Satoshi Nakamoto utilise un critere appele "preuve de travail" pour valider une mise a jour de l'historique parmis plusieures versions possibles. La characteristique majeure de ce critere est qu'il rend la fraude trop couteuse (en terme de puissance de calcul requise) pour en valoir la peine.

Ces validations se faisant a intervales regulier et dans un ordre precis, ils forment une chaine de bloques de transactions validees par tous les membres du reseau, d'ou le terme blockchain (bloque-chaine).
        
Plus concretement, la blockchain est la combinaison de trois technologies qui ensemble permettent de realiser le systeme decrit ci-dessus:
- Le reseau Peer-to-Peer (P2P) est la technologie rendant chaque membre du reseau tributaire des donnees partagees par tous les membres (ici il sagit de l'historique des transactions)
- La signature digitale (combinaison d'une clef prive avec une clef publique) est ce qui permet d'authentifier des transaction sans que les parties prenantes n'aient a reveler leure identite reelle (pseudonymat)
- Le mechanisme de consensus est une serie de regles predefinies qui par l'effet dissuasif qu'elles produisent en cas de fraude permettent une mise a jour coordonnee et fiable de l'historique des transactions effectuees par la communaute d'echange consideree.

## Les enjeux politiques souleve par cette technologie (Notes tirees du Chapitre 1 et 2 du livre Blockchain and the Law, the rule of code)
Aujourd'hui on peut identifier 3 types d'applications majeures de la blockchain:
- Systeme de transfert de valeur trans-national
- Systeme autonome
- Registre resilient, transparent, immuable, et resitant aux manoeuvres d'alterations frauduleuses.

Ces applications viennent avec leurs lots d'opportunites et de contrarietes.

- Ils permettent l'emergence de systemes autonomes operant de maniere globalises avec un cout moindre et une efficacite inimaginable dans les domaines de la finance, des medias, du droit et de l'administration au sens large.
- Ils rendent le flux d'information produit sur internet encore plus difficile a contenir/gerer, offrant ainsi une parade aux efforts de regimes authoritaires visant un controle par la censure
- Ils rendent la capacite de surveillance des echanges plus facilement tracable et offrent une arme supplementaire pour tout regime abusant de ses prerogatives a des fins de controle et de surveillance.

### Reseau trans-national, loi nationale
Par principe la blockchain est un logiciel implementant un protocole operant sur un reseau d'ordinateurs dans le but d'effectuer des operations coordonees. Ce reseau est en principe ouvert a n'importe-quel individu muni d'un appareil capable de se connecter a un reseau internet. Ceci implique que ces reseaux n'ont que tres peu de consideration pour les frontieres nationales et les jurisdictions qui s'y imposent. Une telle fluiditite rend ces objet particulierement difficile a cerner d'un point de vue legal. 

### Resilience aux aleats et a la fraude
Les donnees contenues dasn la blockchain sont partagees par tous les membres du reseau (P2P) avec un mechanisme de consensus qui en garanti l'integrite. La nature distribuee de cette maniere de stocker les donnees offre une serie d'avantages decisifs. En particuliers il est impossible d'unilateralement modifier ou reviser l'information stockee dans la blockchain. Rendant la faillite d'un des membres du reseau moins prejudiciable que si cette information etait centralisee. De meme il est impossible pour un seul membre du reseau d'arreter l'execution de la blockchain dans sa globalite par sa malveillance ou sa faillite.

### Donnees transparente et permanente
La combinaison du reseau P2P avec la signature digitale rendent les donnees stockees dans la blockchain verifiable par tout membres du reseau avec des garantis d'integrite qui rende tout mensonges/denies de transactions difficilement tenable a la lumiere d'une audit effectuee sur cette blockchain. Cette propriete rend aussi la notion de droit a l'oubli pratiquement impossible.

### Pseudonymat
Le pseudonymat rendu possible par la signature digitale protege l'identite reelle des usagers de la blockchain. Les derniers developpements de cette technologie (zero-­knowledge proofs et ring signatures) offrent encore plus de garanties sur cet aspect. Neanmoins une telle garantie nourrie un interet evident pour toute activite illegale qui gagnerait a ne pas pouvoir etre attachee a l'identite reelle de ces instigateurs.

### Consensus et coordination de l'activite des membres
Les mechanismes de consensus gouvernent comment l'information contenue dans la blockchain est mise a jour pour tous les membres simultanement. Une telle capacite permet de coordonner l'activite d'un collectif a grande echelle de maniere autonome. De plus l'integrite du contenue de la blockchain garantie par ce mechanisme de consensus permet une adhesion au reseau sur la base de son contenu/activite sans avoir besoin de faire confiance a quiconque dans ce meme reseau.
### Autonomie
Les reseau P2P couple au mechanisme de consensus facilite le deploiement de logiciels autonomes aptent a fonctioner sans l'intervention d'une tierce partie. Une telle propriete rend les procesus informatiques bases sur la blockchain tres difficiles a modifier ou meme arreter. Neanmoins de tels procesus s'affranchissent de la supervision humaine, fonctionnent plus rapidement avec un plus haut degre de fiabilite et evacuent l'origine principale des defaillances dans de tels systemes (l'erreur humaine)

### La Lex cryptographica
La blockchain et toutes ses applications ont la capacite de produire des systemes autonomes regis par leurs propres lois. Initialement internet etait percut comme un tel systeme. Mais concretement des acteurs comme les fournisseurs internet (telecoms), les moteurs de recherches (Google) ou les plateformes (Facebook) representent de facto des points de controle largement integre dans la strategie de controle des Etats.

La Blockchain a l'heure actuelle surmonte certaines de ces contraintes realisant la notion du "code fait loi", ou l'activite d'une blockchain et determinee par les regles qui l'animent avec une resilience a toutes formes d'attaques internes ou externes. Neanmoins les lois du code sont elles-memes sujettent aux biais ideologiques et politiques des concepteurs et autres ingenieurs les mettant au jour.

### Challenges
Les critiques recurentes et pas totalement evacuees a l'heure actuelle:
- La realite d'un deploiement a grande echelle possible (empreinte environementale, )
- Encore a la merci des gouvernements et de leurs regulations pouvant promouvoir ou entraver l'adoption de cette technologie.

## Notes de l'echange pour identifier les questions d'actualites touchant a la blockchain
La discussion avec Zove et Frederic bouffetier a fair ressortir une serie d'evenements dans l'actualite pour lesquels la comprehension de la blockchain et ses enjeux permettent de mieux les saisir. En voici une liste non-exhaustive:
- L'interet montant de la classe dirigeante pour cette technologie indique un risque d'instrumentalisation de cette technologie initialement pensee comme outil d'emancipation
    - Projet de crypto-monnaie par Facebook ou la BCE dont la vise de surveillance generalisee est a peine cachee.
- Deploiement "progressistes" de ces technologie encore possible
    - Platerforme de partage de video de-centralisee Odysee
- Enjeux geo-politiques avec l'avance prise par des acteurs comme la Chine qui changerait le rapport de force sur l'echiquier mondial de telle sorte que l'Europe se verrait encore plus vulnerabilisee.

