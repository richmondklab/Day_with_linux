🐧 Guide Ultime : Day with Linux (Cybersécurité de A à Z)

Bienvenue dans ce dépôt complet dédié à l'apprentissage de Linux pour la cybersécurité. Que vous débutiez sur TryHackMe, RootMe ou que vous prépariez des certifications, la maîtrise de Linux est votre arme la plus puissante.
📋 Sommaire

    Introduction : Pourquoi Linux ?

    Premiers pas : Qui êtes-vous sur la machine ?

    Navigation et gestion des fichiers sans souris

    Recherche de fichiers et de texte

    Opérateurs, flux et redirection

    Gestion des permissions et des droits (Crucial en Cyber)

    Gestion des processus et des services

    Réseau et investigation de base

    Gestion des paquets et installations

1. Introduction : Pourquoi Linux ?

Il est juste de dire que Linux est beaucoup plus intimidant à l'approche que les systèmes d'exploitation (OS) tels que Windows. Les deux variantes ont leurs propres avantages et inconvénients. Par exemple, Linux est beaucoup plus léger et vous seriez surpris de savoir qu'il y a de fortes chances que vous utilisiez Linux sous une forme ou une autre tous les jours ! Linux alimente des choses telles que :

    Les sites web que vous visitez chaque jour.

    Les panneaux de divertissement et de contrôle de voitures modernes.

    Les systèmes de point de vente (PoS) tels que les caisses et registres dans les magasins.

    Les infrastructures critiques telles que les contrôleurs de feux de circulation ou les capteurs industriels.

    Les téléphones (Android est basé sur un noyau Linux) et appareils informatiques similaires.

Dans la cybersécurité, Linux est le roi incontesté des serveurs, des environnements cloud et des machines que vous allez auditer ou attaquer. Cette interaction commence avec le terminal, et non avec une souris.
2. Premiers pas : Qui êtes-vous sur la machine ?

Être familier avec le terminal (interface de ligne de commande) sur Linux est une compétence critique. Vous y passerez 90% de votre temps, de l'exécution d'outils de piratage (Nmap, Metasploit) à la chasse aux attaquants (Blue Teaming).

Une commande est une instruction donnée à l'ordinateur pour effectuer une tâche.

    whoami : Indique quel utilisateur vous êtes sur le système. C'est fondamental en cybersécurité car vos actions dépendent entièrement de vos privilèges (utilisateur standard vs administrateur root).

    echo [texte] : Permet d'afficher un texte spécifique dans le terminal.

        Exemple : echo "TryHackMe" ou echo "hello world".

    Astuce pro : Dans le terminal, utilisez les touches flèche haut et flèche bas de votre clavier pour faire défiler rapidement l'historique des commandes déjà entrées.

3. Navigation et gestion des fichiers sans souris

Apprenons à naviguer dans les fichiers du système uniquement via le terminal. Quatre commandes font presque toute la navigation de base :

    pwd (Print Working Directory) : Imprime le répertoire de travail actuel — "Où suis-je ?".

    ls (List) : Liste ce qu'il y a dans le dossier courant.

        Astuce : ls -l (affiche les détails) ou ls -a (affiche les fichiers cachés commençant par un point). Sous Linux, les dossiers apparaissent généralement en bleu.

    cd (Change Directory) : Permet de changer de répertoire et de se déplacer (ex: cd /etc ou cd .. pour reculer d'un dossier).

    cat (Concatenate) : Permet d'afficher directement le contenu textuel d'un fichier dans le terminal.

Commandes pour manipuler les fichiers :

    touch nom_de_fichier.txt : Crée un fichier vide.

    mkdir nom_de_dossier : Crée un nouveau dossier.

    cp source destination : Copie un fichier ou un dossier.

    mv source destination : Déplace ou renomme un fichier.

    rm nom_de_fichier : Supprime un fichier.

4. Recherche de fichiers et de texte

Ne cherchez plus jamais les choses à la main. Plutôt que de faire défiler des centaines de lignes à l'œil, utilisez ces moteurs de recherche intégrés :

    find : Recherche des fichiers par leur nom ou leurs critères.

        Exemple : find / -name passwords.txt (cherche le fichier passwords.txt à partir de la racine du disque).

    grep : Recherche à l'intérieur d'un fichier pour trouver un texte ou un motif précis.

        Exemple : grep "password123" access.log (recherche le mot de passe dans un fichier journal de serveur).

5. Opérateurs, flux et redirection

Sous Linux, les opérateurs permettent de combiner des commandes entre elles et de rediriger les flux de données (entrées/sorties).

    & : Exécute la commande en arrière-plan (background) sans bloquer votre terminal.

    && : Exécute la deuxième commande uniquement si la première s'est terminée avec succès (comme un jeu de dominos).

    > : Redirige la sortie d'une commande vers un fichier. Attention : cet opérateur écrase tout le contenu préexistant dans le fichier cible.

    >> : Redirige la sortie mais l'ajoute (append) simplement à la fin du fichier sans rien écraser.

        Exemple : echo "hey" > welcome crée (ou écrase) le fichier welcome avec le texte "hey". On vérifie avec cat welcome.

6. Gestion des permissions et des droits (Crucial en Cyber)

En cybersécurité, comprendre les permissions est vital pour l'escalade de privilèges. Tapez ls -l pour voir les droits d'un fichier (ex: -rwxr-xr--).

    Les trois types d'utilisateurs :

        u (User) : Le propriétaire du fichier.

        g (Group) : Le groupe associé au fichier.

        o (Others) : Tout le monde le reste.

    Les trois permissions :

        r (Read = 4) : Lire le fichier.

        w (Write = 2) : Modifier ou supprimer le fichier.

        x (eXecute = 1) : Exécuter le fichier (script ou programme).

    Modifier les permissions (chmod) :

        Exemple : chmod +x script.sh rend un script exécutable.

        Exemple numérique : chmod 755 fichier (Propriétaire: rwx=7, Groupe: r-x=5, Autres: r-x=5).

    Modifier le propriétaire (chown) :

        sudo chown utilisateur:groupe fichier change le propriétaire d'un fichier.

7. Gestion des services et processus

Pour savoir ce qui tourne sur la machine (et repérer d'éventuels malwares ou services vulnérables) :

    ps aux : Liste tous les processus en cours d'exécution sur le système.

    top ou htop : Affiche en temps réel l'utilisation des ressources CPU/RAM et les processus actifs.

    kill [PID] : Tue un processus bloqué ou suspect à l'aide de son identifiant (PID).

    systemctl : Gère les services du système.

        Exemple : sudo systemctl status apache2 (vérifie si le serveur web tourne).

        Exemple : sudo systemctl start ssh (démarre le service SSH).

8. Réseau et investigation de base

Pour analyser la connectivité et identifier des portes dérobées ou des ports ouverts :

    ip a ou ifconfig : Affiche les interfaces réseau et les adresses IP de la machine.

    ping [adresse_ip] : Teste la connectivité réseau avec une autre machine.

    netstat -tulnp ou ss -tulnp : Liste tous les ports en écoute sur la machine (très utile pour auditer les services actifs).

    curl ou wget : Permet de télécharger des fichiers ou d'interagir avec des serveurs web directement depuis le terminal.

9. Gestion des paquets et installations

Selon la distribution Linux que vous utilisez (Ubuntu/Debian ou Kali Linux), vous gérerez vos logiciels via des gestionnaires de paquets :

    sudo apt update : Met à jour la liste des paquets disponibles.

    sudo apt upgrade : Met à jour tous les logiciels installés.

    sudo apt install [nom_du_paquet] : Installe un nouvel outil (ex: sudo apt install nmap).

    sudo apt remove [nom_du_paquet] : Désinstalle un outil.
