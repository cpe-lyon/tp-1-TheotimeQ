
 ![](/Images/IMG_1.png)

**Quere Theotime 3ICS**

# Table des matières

[Exercice 1. Installation du serveur](#_Toc113528394)

[Exercice 2. Prise en main de l'interpréteur de commandes](#_Toc113528395)

 * [Manuel](#_Toc113528396)

 * [Navigation dans l'arborescence des fichiers](#_Toc113528397)

 * [Commandes importantes](#_Toc113528398)

[Exercice 3. Découverte de l'éditeur de texte nano](#_Toc113528399)

[Exercice 4. Personnalisation du shel](#_Toc113528400)

# Exercice 1. Installation du serveur

Uniquement pour IRC et ETI

# Exercice 2. Prise en main de l'interpréteur de commandes

## Manuel :

1 : La commande which renvoi le chemin complet du fichier associé à la commande passés en paramettre

2 : on peut rechercher un terme en tapant / suivis de ce qu'on cherche , puis entrée

Si on veut cherche option , on tape /option + entrée

3 : q permet de quitter le man

4 : la commande pour voir la première page qui présente le contenu d'une section (l'intro) est : man 6 intro. La section 6 du manuel parle des jeux « amusant » et des petits programmes disponibles sur le systeme

## Navigation dans l'arborescence des fichiers :

1 : cd /vag/log

2 : cd ..

3 : cd ~

4 : cd –

5 : Voici ce qu'il se passe , nous n'avons pas la permission d'acceder à root

 ![](/Images/IMG_2.png)

6 : Voici ce qu'il se passe lorqu'on essay de forcer avec sudo 

![](/Images/IMG_3.png)

Sudo ne fonctionne qu'avec des executables. La commande cd étant une commande shell build in , cela ne fonctionne pas .

7 :

 ![](/Images/IMG_4.png)

Pour créer l'arborescence suivante, je tape :

- cd ~
- mdkir Dossier1
- mkdir Dossier2
- touch Dossier1/Fichier1
- mkdir Dossier2/Dossier2.1
- mkdir Dossier2/Dossier2.2
- touch Dossier2/Dossier2.2/Fichier2
- touch Dossier2/Dossier2.2/Fichier3

8 : Si on tape rm Fichier1 , ca fonctionne

Si on tape rm Dossier1 , ca ne fonctionne pas , car Dossier1 est un dossier.

9 : La commande rmdir Dossier1 permet de suprimer le dossier

10 : rmdir Dossier2 ne fonctionnee pas , car le dossier n'est pas vide.

11 : On peut faire rm –rf Dossier2 pour supprimer le dossier et tout son contenu

## Commandes importantes :

1 : La commande date permet d'afficher la date

Time permet de calculer le temps d'éxecution d'une commande

2 : ls la permet d'afficher les fichier caché . Les fichier avec un point sont des fichiers cachés;

3 : Pour trouver ou se situe le programme ls , on tape which ls

On trouve : /usr/bin/ls

La commande ls est donc dans /usr/bin

4 : ll est équivalent a ls –l , il n'y a pas de manuel pour ll car c'est un alias de la commande ls -l

5 : ls /usr/bin permet d'afficher le contenus du dossier bin

6 : ls liste le contenu d'un dossier

7 : pwd donne le chemin du dossier courant

8 : echo 'bib' \> plop ecrit bib dans un fichier ( qu'il créer si necessaire ) nomé plop , il écrase au passage le contenu présent dans le fichier plop avant d'écrire dedans.

9 : echo bib \>\> plop , permet d'ajouter bib dans le fichier plop. Si le fichier n'existe pas il le créer

10 : sleep 10 | echo 'toto ecrit toto dans le termial et suspens l'éxecution des autre commande pendant 10 sec

11 : La commande file permet d'avoir des informations sur le type de fichier que l'on test ( txt , sh... )

12 :

Créez un fichier original qui contient la chaîne Hello Toto ! ;

Touch original

Echo « Hello toto » \> original

Créer ensuite un lien lien\_phy vers ce fichier avec la commande ln original lien\_phy.

ln original lien\_phy

Modifiez à présent le contenu de original et affichez le contenu de lien\_phy

Echo « Coucou maman » \> original

Cat lien\_phy

On observe que le contenu de lien\_phy est modifier aussi .

Supprimez le fichier original ; quelle conséquence cela a-t-il sur lien\_phy ?

En supprimant le fichier original , on observe que lien\_phy existe toujours et qu'il n'est pas modifié.

13 : on fait la commande : ln -s lien\_phy lien\_sym

On modifie lien\_phy : le contenu de lien sym est modifié aussi

On modifie lien\_sym : le contenu de lien phy est modifié aussi

On suprpime lien\_phy : cela ne supprime pas lien\_sym , mais le liens est cassé et l'on ne peut plus lire / écrire sur le fichier

14 : ctrl + s stop le défilemennt

Ctrlk + q reprend le défilement

15 : head /var/log/syslog 5 permet d'afficher les premieres lignes d'un fichier

Tail /var/log/syslog 15 permet d'afficher les 15 dernieres ligne

Sed –n'10,11p' /var/log/syslog'

16 : la commande dmesg | less affiche les messages stockés dans le noyaux sur une seule page à la fois

17 : on affiche le contenu de /etc/passwd avec cat /etc/passwd .

Ce fichier contient une base de donnée avec tous les comptes utilisateurs trouvés dans le systems.

Man /etc/passwd permet d'afficher la page de manuel de ce fichier

18 : pour afficher seulement la première collone affichée par ordre alphabetique inverse on fait :

Cat /etc/passwd | sed 's/ :.\*$/ /g ' | sort –r

19 : Il faut compter le nombre d'user enregistrés dans la base de donnée stockée dans /etc/passwd.

Pour cela on peut faire un wc –l /etc/passwd pour compter le nombre de ligne de cette base de donnée . On trouve 34.

20 : Il faut chercher le nombre de page qui contienne conversion dans leur description , pour cela on tape : man –k conversion | wc -l

21 : find / -type f –name 'passwd'

22 : pour rediriger la sortie standard dans le fichier ~/list\_passwd\_files.txt et led erreurs dans /dev/null on fait :

: find / -type f –name 'passwd' \> ~/list\_passwd\_files.txt 2\> /dev/null

23 : cat ./.bashrc | grep ll

24 : Plocate n'est pas installé , on ne peut pas utiliser la comande

25 : De même

ALT + FX pour multiple terminal

# Exercice 3. Découverte de l'éditeur de texte nano

On copie le fichier syslog avec :

Cp /var/log/syslog log.txt

On l'ouvre avec nano :

Nano log.txt

Pour voir le contenu , il nous faut les permissions , on fait sudo chmod 777 log.txt

On refait nano :

On remplace kernel par noyau avec :

Alt + R , puis on tape kernel , puis noyau, puis A pour tout remplacer

Pour deplacer les lignes on fait shift + up / down pour les selectionner

Puis CTRL + k pour couper

Puis CTRL + u pour coller

On annule avec alt + u

Ctrl + x pour quitter et enregistrer

# Exercice 4. Personnalisation du shell

1 : On fait une copie du .bashrc :

On vas dans le repertoire personel avec cd ~

On copie le .bashrc avec cp .bashrc .bashrc\_bak

On verifie avec ls –la

2 : on cherche la ligne avec ctrl + W , puis on la decommmante

3 : on recharge le .bash avec source .bashrc\_bak

4 : on fait les changement de couleur necessaire et on ajoute l'heure .

 ![](/Images/IMG_5.png)
 
 Aprés rechargement , cela fonctionne!
