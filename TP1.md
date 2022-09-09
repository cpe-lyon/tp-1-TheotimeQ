
 ![](../master/Images/IMG_1.jpg)

**Quere Theotime 3ICS**

# Table des matières

[Exercice 1. Installation du serveur](#_Toc113528394)

[Exercice 2. Prise en main de l'interpréteur de commandes](#_Toc113528395)

[Manuel](#_Toc113528396)

[Navigation dans l'arborescence des fichiers](#_Toc113528397)

[Commandes importantes](#_Toc113528398)

[Exercice 3. Découverte de l'éditeur de texte nano](#_Toc113528399)

[Exercice 4. Personnalisation du shel](#_Toc113528400)

# Exercice 1. Installation du serveur

Uniquement pour IRC et ETI

# Exercice 2. Prise en main de l'interpréteur de commandes

## Manuel :

1 : La commande which renvoi le chemin complet du fichier associé a la commande passés en paramettre

2 : on peut rechercher un terme en tapant / suivis de ce qu'on cherche , puis faire entré

Si on veut cherche option , on tape /option + entré

3 : q permet de quitter le man

4 : la commande pour voir la première page qui présente le contenu d'une section (l'intro) est : man 6 intro. La section 6 du manuel parle des jeux « amusant » et des petits programmes disponibles sur le system

## Navigation dans l'arborescence des fichiers :

1 : cd /vag/log

2 : cd ..

3 : cd ~

4 : cd –

5 :

 ![](../master/Images/IMG_2.jpg)

6 :  ![](../master/Images/IMG_3.jpg)

Explication

7 :

 ![](../master/Images/IMG_4.jpg)

Pour créer l'arborescence suivante, je tape :

- cd ~
- mdkir Dossier1
- mkdir Dossier2
- touch Dossier1/Fichier1
- mkdir Dossier2/Dossier2.1
- mkdir Dossier2/Dossier2.2
- touch Dossier2/Dossier2.2/Fichier2
- touch Dossier2/Dossier2.2/Fichier3

8 : Si on tape rm Fichier1 , ca fonctinne

Si on tape rm Dossier1 , ca ne marche pas , car Dossier1 est un dossier.

9 : La commande rmdir Dossier1 permet de suprimer le dossier

10 : rmdir Dossier2 ne fonctione pas , car le dossier n'est pas vide.

11 : On peut faire rm –rf Dossier2 pour supprimer le dossier et tout son contenu

## Commandes importantes :

1 : La commande date permet d'afficher la date

Time permet de calculter le temps d'execution d'une commande

2 : ls la permet d'affichier les fichier caché . Les fichier avec un point sont des fichier caché

3 : pour trouver ou ce situe le programme ls , on tape which ls

On trouve : /usr/bin/ls

La commande ls est donc dans /usr/bin

4 : ll est equivalent a ls –l , il n'y a pas de manuel pour ll car c'est un alias de la commande ls -l

5 : ls /usr/bin permet d'affichier le contenus du dossier bin

6 : ls liste le contenus d'un dossier

7 : pwd donne le chemin du dossier courant

8 : echo 'bib' \> plop ecrit bib dans un fichier ( qu'il créer si necessaire ) nomé plop , il ecrase au passage le contenu presnet dans le fichier plop avant d'ecrire dedans.

9 : echo bib \>\> plop , permet d'ajouter bib dans le fichier plop. Si le fichier n'existe pas il le créer

10 : sleep 10 | echo 'toto ecrit toto dans le termial et suspens l'execution des autre commande pendant 10 sec

11 : la commande file permet d'avoir des information sur le type de fichier que l'on test ( txt , pdf… )

12 :

Créez un fichier original qui contient la chaîne Hello Toto ! ;

Touch original

Echo « Hello toto » \> original

créer ensuite un lien lien\_phy vers ce fichier avec la commande ln original lien\_phy.

ln original lien\_phy

Modifiez à présent le contenu de original et affichez le contenu de lien\_phy : qu'observe-t-on ?

Echo « Coucou maman » \> original

Cat lien\_phy

On observe que le contenu de lien\_phy est modifier aussi .

Supprimez le fichier original ; quelle conséquence cela a-t-il sur lien\_phy ?

En suppriman le fichier original , on oberseve que lien\_phy existe toujours et n'est pas modifiée.

13 : on fait la commande : ln -s lien\_phy lien\_sym

On modifie lien\_phy : le contenu de lien sym est modifier aussi

On modifie lien\_sym : le contenu de lien phy est modifier aussi

On suprpime lien\_phy : cela ne supprime pas lien\_sym , mais le liens est cassé et l'on ne peut plus lire / ecrire sur lien le fichier

14 : ctrl + s stop le defilemennt

Ctrlk + q reprend le defilement

15 : head /var/log/syslog 5 permet d'afficher les premier ligne d'un fichier

Tail /var/log/syslog 15 permet d'affichier les 15 dernier ligne

Sed –n'10,11p' /var/log/syslog'

16 : la commande dmesg | less affiche les message stocker sur une seule page

17 : on affiche le contenu de /etc/passwd avec cat /etc/passwd .

Ce fichier contient une base dde donnée avec tout les compte utilisateur trouvé dans le system.

Man /etc/passwd permet d'afficher la page de manuel de ce fichier

18 : pour afficher seulement la premiere collone afficher par ordre alphabetique invers on fait :

Cat /etc/passwd | sed 's/ :.\*$/ /g ' | sort –r

19 : Il faut compte le nombre d'user enregistré dans la base de donnée stocké dans /etc/passwd.

Pour cela on peut faire un wc –l /etc/passwd pour compte le nombre de ligne de cette base de donnée . On trouve 34

20 : Il faut cherche le nom de page qui contienne conversion dans leur description , pour cela on tape : man –k conversion | wc -l

21 : find / -type f –name 'passwd'

22 : pour rediriger la sortie standar dans le fichier ~/list\_passwd\_files.txt et le serreurs dans /dev/null on fait :

: find / -type f –name 'passwd' \> ~/list\_passwd\_files.txt 2\> /dev/null

23 : cat ./.bashrc | grep ll

24 : Plocate n'est pas installé , on ne peut pas utiliser la comande

25 :

ALT + FX pour multiple terminal

# Exercice 3. Découverte de l'éditeur de texte nano

On copie le fichier syslog avec :

Cp /var/log/syslog log.txt

On l'ouvre avec nano :

Nano log.txt

Pour voir le contenu , il nous faut les permissions , on fait sudo chmod 777 log.txt

On refait nano :

On remplac kernel par noyau avec :

Alt + R , puis on tape kernel , puis noyau, puis A pour tout remplacer

Pour deplacer les lignes on fait shit + up / down pour les selectionner

Pui sCrlk + k pour couper

Puis CTRLK + u pour coller

On annule avec alt + u

Ctrl + x pour quitte ret enregirster

# Exercice 4. Personnalisation du shell

1 : On fait une copie du .bashrc :

On vas dans le repertoire personall avec cd ~

On copie le .bashrc avec cp .bashrc .bashrc\_bak

On verifie avec ls –la

2 : on cherche la ligne avec ctrl + W , puis on la decommmante

3. on recharche le .bash avec source .bashrc\_bak

4

 ![](../master/Images/IMG_5.jpg)
