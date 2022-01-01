# Rapport

Vous trouverez le rapport, selon cette table des matieres : 

Table des matières :

Rapport Projet UML	1
I / Explication du jeu	2
Liste des accessoires présents dans le jeu :	2
Liste des caractéristiques présents dans le jeu :	2
II / Conditions de jeu	3
III / Explication des phases	4
IV / Conception du Jeu	5
V / Cas d’utilisations	6
V.I. Cas d’utilisation “en jeu” :	6
V.II. Cas d’utilisation “Paramètres”	7
V.III. Cas d’utilisations "Menu Principal"	7
VI / Diagrammes d’activités	8
VI.I. Diagramme d’activité “Capture de l’alien”	8
VI.II. Diagramme d’activité “Se déplacer”	9
VI.III. Diagramme d’activité “Se Soigner”	10
VI.IV. Diagramme d’activité “Soigner”	11
VI.V. Diagramme d’activité charger une partie (Solo uniquement)	11
VII / Diagrammes de séquences	13
VII.I. Attaque Alien avec QTE réussi et raté	13
VII.II. Test QTE pour réparer un élément	13
VII.III. Utilisation lampe torche sur l'Alien	14
VII.IV. Génération des dégâts sur le vaisseau pour la phase 2	15
VII.V. Scénario de créer une partie, avec 4 joueurs	16
VII.VI. Scénario de créer une partie solo	18
VII.VII. Détruire le vaisseau si trop de dégâts	18
VII.VIII. Scénario de répartir les rôles lors de la création d’une partie	19
VII.IX. Ramassage d'un accessoire	20
VII.X. Attaquer l'alien (calcul des dégâts avec ou sans arme)	20
VIII / Diagramme de classe	22
IX / Diagramme d’états-transitions	22
IX.I. Joueur	22
IX.II. Vaisseau	23
IX.III. Alien (IA)	23
IX.IV. Partie	23
X / Glossaire	25


I / Explication du jeu
Notre jeu consiste à faire décoller, voyager et atterrir un vaisseau spatial mais un alien à bord complique la tâche. Vous devrez, suivant trois phases (décollage, voyage et atterrissage) survivre et réussir votre mission en minimisant les pertes. Tout au long de votre partie, l’alien provoquera des dégâts à votre vaisseau et vous poursuivra. Il vous faudra trouver des moyens de l’éviter, le tuer ou l’emprisonner tout en réparant les dégâts provoqués pour continuer la mission. 

Enfin, pour mener à bien votre mission, vous trouverez des objets spécifiques aux pièces de votre vaisseau, à vous de savoir les utiliser avec ruse.
Liste des accessoires présents dans le jeu :
Arme (différence de porté) :	
Couteau
Hache
Pistolet 
Cage (divisée en 3 parties séparées dans le vaisseau)
Kit de soin
rendre une vie à un joueur
Radar
prévenir le joueur si la bête est proche
Lampe torche éblouissante
Immobilisation de l’alien pendant 3 secondes 
Liste des caractéristiques présents dans le jeu :
Ingénieur
répare plus rapidement les dégâts en réduisant la quantité de QTE nécessaire de 2 au lieu de 1 en cas de réussite
Loup solitaire
plus de temps pour réaliser tous les qte quand il est seul dans une pièce
Casse cou
fait 1 dégât de plus à l’alien
Bon samaritain 
soigne une vie en plus les autres personnages mais ne peut pas se soigner soi même 


II / Conditions de jeu 
Nombre de joueurs maximum (Multi) → 4. On ne peut lancer une partie (multi) que si le nombre de joueurs présent dans le salon est atteint.
L’alien du vaisseau est une IA.
Rejoindre une partie nécessite un code. Ce code est généré par le créateur du salon. 
Le vaisseau est réparti en différentes pièces contenant un ou plusieurs objets uniques, permettant de réparer le vaisseau ou résister face à l’alien. Au lancement de la partie, les joueurs obtiendront aléatoirement un passif / caractéristiques. 

Lors de la phase de décollage, le joueur doit réussir des QTE de discrétion afin de ne pas se faire repérer par la bête.
Lors du voyage, le joueur peut commencer à effectuer les réparations des différentes parties du vaisseau. Chaque réparation nécessite une quantité de QTE à réussir.
Le joueur peut aussi se déplacer dans le vaisseau afin de retrouver les accessoires facilitant sa survie. Si ce dernier se retrouve proche de l’alien, il devra réussir un QTE de fuite.
Lors de l’atterrissage, le joueur pourra effectuer des attaques afin de tuer l’alien. Chaque attaque demandera un QTE. Le joueur va soit tuer la bête soit la piéger en réunissant les 3 pièces d’une cage sur un même joueur pour pouvoir finir la partie.

III / Explication des phases 
La première phase, la phase décollage consiste en une séquence de furtivité où les joueurs devront effectuer des QTE (tests de rapidité avec contrôles de la manette) pour ne pas se faire repérer par l’alien, le joueur sera figé sur place, ne pourrait pas se déplacer et n’aurait pour but juste de rester inactif.

La deuxième phase, la phase voyage, aurait pour but de pouvoir se déplacer, attaquer l’alien et réparer des parties du vaisseau (détruites par l’alien). Les joueurs auront pour but de résister à l’alien sans mourir, tout en gardant le vaisseau en bon état pour éviter de le perdre.

La troisième et dernière phase atterrissage, a pour but de mettre hors d’état de nuire l’alien, soit en l’emprisonnant, soit en le tuant par tous les moyens disponibles. Le but ici n’est plus de prendre soin du vaisseau mais d’à tout prix se débarrasser de l’alien.

IV / Conception du Jeu 
Afin de fournir une vision d’ensemble du projet tout en expliquant ses fonctionnalités, son fonctionnement et les différents scénarios d’utilisations du jeu, il est nécessaire de fournir des diagrammes UML qui permettront de synthétiser l’ensemble du jeu. Ils permettent de fournir un socle conceptuel facilitant la création et le développement du projet.

Dans un premier temps nous présenterons les cas d’utilisations résumant la liste des fonctionnalités, puis les diagrammes d’activités des cas d’utilisations les plus complexes, par la suite des diagrammes de séquence pour expliquer les différents scénarios et actions possibles. Par la suite, des diagrammes d’états transitions et enfin un diagramme de classe permettront de synthétiser la structure du projet et de faciliter son implémentation en logiciel / programme réel.

V / Cas d’utilisations
Pour tous nos cas d’utilisations, quatres acteurs en total seront pris en compte : 
Le joueur
L’alien (IA / bot)
Les autres joueurs de la partie
Le système

Pour des raisons d’esthétique et de compréhension, nous avons divisé l’ensemble des cas d’utilisations en plusieurs diagrammes afin que son contenu soit plus compréhensible et agréable à lire.
V.I. Cas d’utilisation “en jeu” :
Le diagramme de cas d’utilisation pour la phase “en Jeu”, elle répertorie toutes les actions directes que peut faire le joueur dans une partie. Tout au long de la partie, le joueur peut effectuer différentes intéractions (soigner, tuer, se déplacer, qte…) mais peut aussi la mettre la en pause ou la quitter.



V.II. Cas d’utilisation “Paramètres”
Le diagramme de cas d’utilisation qui présente les différentes fonctionnalités auxquelles le joueur peut accéder, lorsqu’il se rend dans le menu des paramètres. Ainsi, il peut configurer l’assignation des actions de son clavier ou de sa manette. Le paramétrage du son et des graphismes est disponible. Pour appliquer les changements effectués, le joueur doit cliquer sur sauvegarder ou dans le cas contraire sur annuler.


V.III. Cas d’utilisations "Menu Principal"
Le diagramme de cas d’utilisation pour les fonctionnalités auxquelles le joueur a accès quand il se trouve dans le menu principal du jeu, il répertorie toutes les actions qu’il peut effectuer sur une partie (nouvelle partie, charger partie, rejoindre partie), consulter les crédits, changer ses paramètres ou quitter le jeu.


VI / Diagrammes d’activités
Les diagrammes d’activité permettent de dérouler une fonctionnalité en fonction des choix et des conditions liées à la fonctionnalité elle-même.

VI.I. Diagramme d’activité “Capture de l’alien”
Ce diagramme représente la fonctionnalité de capture de l’alien, qui se situe lors de la phase 3. Cette fonctionnalité est uniquement disponible lorsqu’un joueur réunit les 3 parties qui composent la cage. Si le joueur se trouve à portée de l’alien, ce dernier est emprisonné et la partie se termine sur la victoire des joueurs. 





VI.II. Diagramme d’activité “Se déplacer”
Ce diagramme d’activité représente la fonctionnalité de “se déplacer” pour le joueur. Cette fonctionnalité est possible que si le joueur n’est pas dans l’état “Mort”. 





















VI.III. Diagramme d’activité “Se Soigner”
Ce diagramme d’activité représente la fonctionnalité “se soigner” pour un joueur. A ne pas confondre avec “Soigner” qui permet de soigner un autre joueur. Le joueur ne peut se soigner que si son nombre de vie est inférieur à 3. Ainsi, s’il possède au moins un kit de soin, le joueur peut le consommer pour se soigner. L’utilisateur sera averti des aboutissements de ses actions.
















VI.IV. Diagramme d’activité “Soigner”
Ce diagramme d’activité représente la fonctionnalité “Soigner” pour un joueur. Elle correspond à la fonctionnalité de soigner un autre joueur. Cette fonctionnalité est uniquement possible si le joueur qu’on souhaite soigner à perdu au moins un point de vie. On prend le cas où le joueur qui effectue l’action possède un kit de soin.
Si l’action est effectuée correctement, les 2 joueurs sont avertis du succès de l’action.
VI.V. Diagramme d’activité charger une partie (Solo uniquement)
Ce diagramme d’activité représente la fonctionnalité “Charger une partie” pour un joueur. Après sélection par le joueur de la partie à charger, le jeu lance la partie.


VII / Diagrammes de séquences
VII.I. Attaque Alien avec QTE réussi et raté
Ce diagramme de séquence représente le scénario d’une confrontation avec l’alien suite à une attaque de l’alien. 

VII.II. Test QTE pour réparer un élément
Le diagramme de séquence représente le scénario lorsque le joueur souhaite effectuer une réparation. On vérifie tout d’abord si l’élément est endommagé. Si c’est le cas, le joueur doit effectuer un QTE aléatoire. 
En cas de succès, le nombre de réparation nécessaire de l’élément diminue de 1 et 2 si le joueur possède la caractéristique “Ingénieur”.

VII.III. Utilisation lampe torche sur l'Alien
Le diagramme de séquence ‘Utilisation d’une lampe torche sur alien’ représente le scénario lorsque le joueur souhaite utiliser l'objet Lampe torche éblouissante, ce dernier va devoir effectuer un QTE aléatoire.
En cas de succès, l’alien va passer dans l’état "Éblouit" pendant 3 secondes.

VII.IV. Génération des dégâts sur le vaisseau pour la phase 2
Ce diagramme de séquence représente la génération des dégâts sur le vaisseau pendant la deuxième phase. Le système établit un nombre de dégâts à réaliser. Tant que ce nombre de dégâts est supérieur à 0, le système trouvera au hasard, une pièce du vaisseau à faire subir des dégâts.

VII.V. Scénario de créer une partie, avec 4 joueurs
Le diagramme de séquence “créer une partie avec 4 joueurs” représente le scénario lorsque le joueur souhaite créer une partie multijoueur. Un serveur est alloué à la partie et un code d’invitation est généré afin que les autres joueurs puissent rejoindre la partie.
Du côté des autres joueurs, ils vont devoir aller dans la fonctionnalité “Rejoindre une partie” et insérez le code d’invitation. Une vérification est ensuite effectuée pour s’assurer de la validité du code.
Pour finir, si le créateur de la partie souhaite démarrer le jeu, le jeu est alors démarré pour tous les joueurs de la partie.

VII.VI. Scénario de créer une partie solo
Ce diagramme de séquence représente la création d’une partie en solo. Tout d’abord, le système retourne un serveur disponible, puis crée le salon et le joueur lance immédiatement la partie.

VII.VII. Détruire le vaisseau si trop de dégâts
Ce diagramme de séquence représente le scénario où, si le vaisseau à subit trop de dégâts, il se détruit. Si la vérification de l’état du vaisseau,  révèle qu’il est trop endommagé, alors le système le détruit, notifie les joueurs de la partie et termine la partie.

VII.VIII. Scénario de répartir les rôles lors de la création d’une partie
Ce diagramme de séquence représente la répartition des rôles lors de la création de la partie. Chaque joueur se verra attribuer un rôle aléatoirement par le système.

VII.IX. Ramassage d'un accessoire
Ce diagramme de séquence représente le ramassage d’un accessoire. Si le joueur est déjà en possession d’un accessoire, ce dernier sera déposé et remplacé par le nouvel accessoire.

VII.X. Attaquer l'alien (calcul des dégâts avec ou sans arme)
Ce diagramme de séquence représente le calcul des dégâts infligés à l’alien par un joueur. Après calcul de la distance entre l’alien et le joueur par le système, en fonction de sa proximité avec sa cible et son arme, le système calcule les dégâts à infliger.

VIII / Diagramme de classe


IX / Diagramme d’états-transitions
IX.I. Joueur

Le diagramme d’états-transitions pour le joueur lors de la partie. Le joueur peut avoir 3 états différents : 
L’état "Santé Pleine" lorsque le joueur possède ces 3 points de vie.
L’état “Blessé” lorsqu'il a perdu au moins un point de vie.
L’état “Mort” lorsque le joueur ne possède plus aucun point de vie. 



IX.II. Vaisseau

Le diagramme d’états-transitions pour le vaisseau lors de la partie. Le vaisseau peut avoir 3 états différents : 
L’état "Décollage" lorsque le vaisseau est dans la première phase du jeu.
L’état “En Voyage” lorsque le vaisseau est dans la deuxième phase du jeu.
L’état “Atterrissage” lorsque le vaisseau est dans la troisième phase du jeu. 


IX.III. Alien (IA)

Le diagramme d’états-transitions pour l’alien lors de la partie. L’alien peut avoir 5 états différents : 
L’état "Santé Pleine" lorsque l’alien possède ses 10 points de vie.
L’état "Blessé" lorsque l’alien perd au moins un point de vie.
L’état “Mort” lorsque l’alien n’a plus aucun point de vie. 
L’état “Eblouit” lorsque le joueur utilise la lampe torche éblouissante sur l’alien.
L’état “Emprisonné” lorsque le joueur utilise la cage complétée sur l’alien. 


IX.IV. Partie

Le diagramme d’états-transitions pour la partie. La partie peut avoir 4 états différents : 
L’état "En Attente" lorsque le joueur crée sa partie et génère le code, en attente d’autres joueurs pour pouvoir commencer.
L’état "En Cours" lorsque la partie se déroule correctement.
L’état “En Pause” lorsque le joueur qui a créé la partie met en pause le jeu uniquement s’il joue tout seul. 
L’état “Terminé” lorsque la partie est arrivée à son terme avec soit l’alien qui est mort soit plus aucun joueur en vie.



X / Glossaire 

Terme
Définition
QTE
QTE, ou « Quick Time Event », pour événements en temps limités, sont des séquences de jeu vidéo filmées sous des angles cinématographiques et qui ne demandent au joueur d’appuyer sur le bouton qui apparaît à l'écran pour permettre à la scène de se poursuivre.















