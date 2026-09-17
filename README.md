# Day_with_linux

Où est Linux utilisé ?

Il est juste de dire que Linux est beaucoup plus intimidant à l'approche que les systèmes d'exploitation (OS) tels que Windows. Les deux variantes ont leurs propres avantages et inconvénients. Par exemple, Linux est beaucoup plus léger et vous seriez surpris de savoir qu'il y a de fortes chances que vous utilisiez Linux sous une forme ou une autre tous les jours! Linux alimente des choses telles que:

    Sites que vous visitez
    Panneaux de divertissement/contrôle de voiture
    Systèmes de point de vente (PoS) tels que les caisses et les registres dans les magasins
    Infrastructures critiques telles que les contrôleurs de feux de circulation ou les capteurs industriels
    Téléphones et appareils informatiques similaires
    Et bien plus encore !


    Qui êtes-vous sur cette machine ?

Linux est un choix populaire pour les serveurs et les machines que vous allez interagir dans la cybersécurité. Cette interaction commence avec le terminal, pas avec une souris. Dans cette pièce, vous interagirez avec votre tout premier terminal Linux - un endroit où nous pouvons exécuter des commandes sur le système.

Être familier avec le terminal (interface de ligne de commande) sur Linux est une compétence critique car vous passerez probablement la plupart de votre temps ici dans la cybersécurité. De l'exécution d'outils de piratage à la chasse aux attaquants.

Une commande est une instruction que nous pouvons donner à l'ordinateur pour effectuer une tâche donnée. L'une des premières commandes que nous pouvons faire est whoami. Ceci est important dans la cybersécurité, car vous changerez souvent d’utilisateur sur la machine, ce qui détermine ce que vous pouvez et ne pouvez pas faire.
whoami 	vous dit qui vous êtes sur le système

Lorsque vous exécutez votre première commande, vous verrez du texte. Nous appelons cela la production. Interagir avec Linux ressemble à une conversation. Vous lui donnez une instruction, et il vous donne la sortie. Nous pouvons demander à Linux de produire du texte spécifique pour nous.
echo 	produire un texte spécifique qui est fourni

Pour faire écho au texte "TryHackMe", nous pouvons utiliser echo TryHackMe. Pour plusieurs mots, nous devrons les envelopper dans des citations. Par exemple, echo "hello world". Utilisation echon'est que le début d'une compétence très importante dans la cybersécurité: être capable de créer de la production et de l'envoyer quelque part. Vous verrez comment cette compétence est davantage utilisée dans les tâches à venir.
Caractère
 
 
 
 
Vous devrez...
1. Utilisez le whoamicommander de voir qui vous êtes sur le système.
2. Appuyez sur la touche Entrée pour exécuter la commande.
3. Maintenant, utilisez echopour sortir le texte TryHackMe.

Astuce pro: Lorsque vous utilisez le terminal, vous pouvez appuyer sur les touches fléchées vers le haut et vers le bas de votre clavier pour faire défiler les commandes que vous avez déjà entrées.


Déplacez-vous sans jamais toucher une souris

Apprenons à naviguer dans les fichiers du système via le terminal. Quatre commandes font presque toute la navigation
ls 	Liste ce qu'il y a dans le dossier courant
cd 	modifier le répertoire — se déplacer dans un dossier
cat 	montrer le contenu d'un fichier
pwd 	Imprimer le répertoire de travail — "où suis-je?"

Sous Linux, vous remarquerez peut-être que les fichiers et les dossiers apparaissent sous différentes couleurs. Cela permet d'identifier facilement ce qu'il est. Sur ce système Linux, les dossiers sont bleus.
