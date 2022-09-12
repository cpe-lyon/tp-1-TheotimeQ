**Quere Theotime 3ICS**

# Table des matières

[Exercice 1. Installation du serveur](#_Toc113528394)

[Exercice 2. Prise en main de l'interpréteur de commandes](#_Toc113528395)

 * [Manuel](#_Toc113528396)

 * [Navigation dans l'arborescence des fichiers](#_Toc113528397)

 * [Commandes importantes](#_Toc113528398)

[Exercice 3. Découverte de l'éditeur de texte nano](#_Toc113528399)

[Exercice 4. Personnalisation du shell](#_Toc113528400)

# Exercice 1. Installation du serveur

Uniquement pour IRC et ETI

# Exercice 2. Prise en main de l'interpréteur de commandes

## Manuel :

### 1 : A l’aide du manuel, identifiez le rôle de la commande which
```console
User@localhost:~$ man which
```
La commande which renvoi le chemin complet du fichier associé à la commande passés en paramettre.

### 2 : Quand on consulte cette page, comment peut-on rechercher, par exemple, le mot option ?
on peut rechercher un terme en tapant / suivis de ce qu'on cherche , puis entrée

```console
/option
```
Si on veut chercher option , on tape /option + entrée

### 3 : Comment quitte-t-on le manuel ?
q permet de quitter le man.

### 4 : Chaque section du manuel a une première page, qui présente le contenu de la section. Afficher la première page de la section 6 ; de quoi parle cette section ?
La commande pour voir la première page qui présente le contenu d'une section (l'intro) est : man 6 intro. La section 6 du manuel parle des jeux « amusants » et des petits programmes disponibles sur le systeme

```console
User@localhost:~$ man 6 intro
```

## Navigation dans l'arborescence des fichiers :

### 1 : Pour aller dans le dossier /var/log
```console
User@localhost:~$ cd /vag/log
```

### 2 : Pour remonter dans le dossier parent
```console
User@localhost:~$ cd ..
```

### 3 : Pour retourner au dossier personnel 
```console
User@localhost:~$ cd ~
```

### 4 : Pour revenir au dossier précedent
```console
User@localhost:~$ cd –
```

### 5 : essayez d’accéder au dossier /root ; que se passe-t-il ?
Voici ce qu'il se passe , nous n'avons pas la permission d'acceder à root

 ![](/Images/IMG_2.png)

### 6 : essayez la commande sudo cd /root ; que se passe-t-il ? Expliquez
Voici ce qu'il se passe lorqu'on essay de forcer avec sudo 

![](/Images/IMG_3.png)

Sudo ne fonctionne qu'avec des executables. La commande cd étant une commande shell build in , il faut utiliser sudo -s.

### 7 : à partir de votre dossier personnel, créez l’arborescence suivante :

 ![](/Images/IMG_4.png)

Pour créer l'arborescence suivante, je tape :

```console
User@localhost:~$ cd ~
mdkir Dossier1
mkdir Dossier2
touch Dossier1/Fichier1
mkdir Dossier2/Dossier2.1
mkdir Dossier2/Dossier2.2
touch Dossier2/Dossier2.2/Fichier2
touch Dossier2/Dossier2.2/Fichier3
```

### 8 : revenez dans votre dossier personnel ; à l’aide de la commande rm, essayez de supprimer Fichier1, puis Dossier1 ; que se passe-t-il ?
```console 
User@localhost:~$ rm Fichier1
```
Le fichier1 est bien suprimé

```console 
User@localhost:~$ rm Dossier1
``` 
Le dossier1 ne se suprime pas , car Dossier1 est un dossier.

### 9 : Quelle commande permet de supprimer un dossier ? 
```console 
User@localhost:~$ rmdir Dossier1
``` 
La commande rmdir Dossier1 permet de suprimer le dossier

### 10 : Que se passe-t-il quand on applique cette commande à Dossier2 ?
```console 
User@localhost:~$ rmdir Dossier2
``` 
Cela ne fonctione pas , car le Dossier2 n'est pas vide.

### 11 : Comment supprimer en une seule commande Dossier2 et son contenu ?
On peut faire la commande suivante pour supprimer le dossier et tout son contenu.
```console 
User@localhost:~$ rm –rf Dossier2
``` 

## Commandes importantes :

### 1 : Quelle commande permet d’afficher l’heure ? A quoi sert la commande 'time' ?

La commande date permet d'afficher la date
```console 
User@localhost:~$ date
``` 

Time permet de calculer le temps d'éxecution d'une commande
```console 
User@localhost:~$ time
``` 

### 2 : Dans votre dossier personnel, tapez successivement les commandes ___ls___ puis ___la___ ; que peut-on en déduire sur les fichiers commençant par un point ?

```console 
User@localhost:~$ ls la
``` 
La commande permet d'afficher les fichiers cachés . Les fichiers avec un point sont des fichiers cachés;

### 3 : Où se situe le programme ___ls___ ?
Pour trouver ou se situe le programme ls , on tape 
```console 
User@localhost:~$ which ls
``` 

On trouve : /usr/bin/ls

La commande ls est donc dans /usr/bin

### 4 : Que fait la commande ___ll___ ? (indice : la commande alias peut vous aider)
ll est équivalent à 
```console 
User@localhost:~$ ls -l
``` 
Il n'y a pas de manuel pour ll car c'est un alias de la commande `ls -l`

### 5 : Quelle commande permet d’afficher les fichiers contenus dans le dossier /bin ?
```console 
User@localhost:~$ ls /usr/bin
``` 
La commande permet d'afficher le contenus du dossier bin.

### 6 : Que fait la commande ___ls___ .. ?
```console 
User@localhost:~$ ls
``` 
Cette commande liste le contenu d'un dossier.

### 7 : Quelle commande donne le chemin complet du dossier courant ?
```console 
User@localhost:~$ ls
``` 
Cette commmande donne le chemin du dossier courant.

### 8 : Que fait la commande ___echo 'bib' > plop___ exécutée 2 fois ?

```console 
User@localhost:~$ echo 'bib' \> plop
``` 
Cette commande écrit dans un fichier ( qu'elle créer si necessaire ) nomé plop , il écrase au passage le contenu présent dans le fichier plop avant d'écrire dedans.

### 9 : Que fait la commande ___echo 'bib' >> plop___ exécutée 2 fois ?
```console 
User@localhost:~$ echo 'bib' \>\> plop
``` 
Cette commande permet d'ajouter bib dans le fichier plop. Si le fichier n'existe pas il le créer.

### 10 : Interprétez le comportement de la commande sleep 10 | echo 'toto' ?
`Sleep 10 | echo 'toto' ` ecrit toto dans le termial et suspend l'éxecution des autres commandes pendant 10 sec

### 11 : A quoi sert la commande ___file___ ? Essayez la sur des fichiers de types différents.
La commande 'file' permet d'avoir des informations sur le type de fichier que l'on test indépendament de son extenssion.

### 12 : Créez un fichier original qui contient la chaîne Hello Toto ! ; créer ensuite un lien lien_phy vers ce fichier avec la commande ln original lien_phy. Modifiez à présent le contenu de original et affichez le contenu de lien_phy : qu’observe-t-on ? Supprimez le fichier original ; quelle conséquence cela a-t-il sur lien_phy ?

Créez un fichier original qui contient la chaîne Hello Toto ! ;
```console 
User@localhost:~$ touch original
echo 'Hello toto' \> original
``` 

Créer ensuite un lien lien\_phy vers ce fichier avec la commande ln original lien\_phy.
```console 
User@localhost:~$ ln original lien\_phy
``` 

Modifiez à présent le contenu de original et affichez le contenu de lien\_phy
```console 
User@localhost:~$ echo 'Coucou maman' \> original
cat lien\_phy
``` 

On observe que le contenu de lien\_phy est modifier aussi .

Supprimez le fichier original ; quelle conséquence cela a-t-il sur lien\_phy ?

En supprimant le fichier original , on observe que lien\_phy existe toujours et qu'il n'est pas modifié.

### 13 : Créez à présent un lien symbolique lien_sym sur lien_phy avec la commande ln -s lien_phy lien_sym.Modifiez le contenu de lien_phy ; quelle conséquence pour lien_sym ? Et inversement ? Supprimez le fichier lien_phy ; quelle conséquence cela a-t-il sur lien_sym ?
```console 
User@localhost:~$ ln -s lien\_phy lien\_sym
``` 

On modifie lien\_phy : le contenu de lien sym est modifié aussi

On modifie lien\_sym : le contenu de lien phy est modifié aussi

On suprpime lien\_phy : cela ne supprime pas lien\_sym , mais le liens est cassé et l'on ne peut plus lire / écrire sur le fichier

### 14 : Affichez à l’écran le fichier /var/log/syslog. Quels raccourcis clavier permettent d’interrompre et reprendre le défilement à l’écran ?
```console 
User@localhost:~$ cat /var/log/
``` 
ctrl + s stop le défilemennt

ctrl + q reprend le défilement

### 15 : Affichez les 5 premières lignes du fichier /var/log/syslog, puis les 15 dernières, puis seulement les lignes 10 à 20

Pour affichier seulement les 5 premieres lignes : 
```console 
User@localhost:~$ head /var/log/syslog 5
``` 
 
Pour affichier seulement les 15 dernieres lignes : 
```console 
User@localhost:~$ tail /var/log/syslog 15
``` 

Pour affichier seulement les lignes 10 à 20 :
```console 
User@localhost:~$ sed –n'10,20p' /var/log/syslog'
``` 

### 16 : Que fait la commande dmesg | less ?
D'apres le man , la commande dmesg | less affiche les messages stockés dans le noyaux,  une seule page à la fois

### 17 : Affichez à l’écran le fichier /etc/passwd ; que contient-il ? Quelle commande permet d’afficher la page de manuel de ce fichier ?
on affiche le contenu de /etc/passwd avec :
```console 
User@localhost:~$ cat /etc/passwd
``` 

Ce fichier contient une base de donnée avec tous les comptes utilisateurs trouvés dans le systems.

Pour afficher la page du manuel de psswd : 

```console 
User@localhost:~$ man /etc/passwd
``` 

### 18 : Affichez seulement la première colonne triée par ordre alphabétique inverse pour afficher seulement la première collone affichée par ordre alphabetique inverse on fait :

```console 
User@localhost:~$ cat /etc/passwd | sed 's/ :.\*$/ /g ' | sort –r
``` 

### 19 : Quelle commande nous donne le nombre d’utilisateurs ayant un compte sur cette machine (pas seulement les utilisateurs connectés) ?
Il faut compter le nombres d'utilisateurs enregistrés dans la base de donnée stockée dans /etc/passwd.

Pour cela on peut faire `wc –l /etc/passwd` pour compter le nombre de ligne de cette base de donnée . On trouve 34.

### 20 : Combien de pages de manuel comportent le mot-clé conversion dans leur description ?
Il faut chercher le nombre de page qui contienne conversion dans leur description , pour cela on tape : `man –k conversion | wc -l`

### 21 : A l’aide de la commande find, recherchez tous les fichiers se nommant passwd présents sur la machine 
```console 
User@localhost:~$ find / -type f –name 'passwd'
``` 

### 22 : Modifiez la commande précédente pour que la liste des fichiers trouvés soit enregistrée dans le fichier ~/list_passwd_files.txt et que les erreurs soient redirigées vers le fichier spécial /dev/null

Pour rediriger la sortie standard dans le fichier ~/list\_passwd\_files.txt et led erreurs dans /dev/null on fait :

```console 
User@localhost:~$ find / -type f –name 'passwd' \> ~/list\_passwd\_files.txt 2\> /dev/null
``` 

### 23 : Dans votre dossier personnel, utilisez la commande grep pour chercher où est défini l’alias ll vu précédemment

```console 
User@localhost:~$ cat ./.bashrc | grep ll
``` 

### 24 : Utilisez la commande locate pour trouver le fichier history.log.
```console 
User@localhost:~$ locate history.log
/var/log/apt/history.log
``` 

### 25 : Créer un fichier dans votre dossier personnel puis utilisez locate pour le trouver. Apparaît-il ? Pourquoi ? 
Avec `locate` nous ne trouvons pas le fichier. La commande `locate` recherche dans une base de donnée mise à jours une fois par jour . Pour trouver le nouveau fichier il faut donc la mettre à jour avec `sudo updatedb`

#### Tips : 
**ALT + FX pour multiple terminal**

# Exercice 3. Découverte de l'éditeur de texte nano

On copie le fichier syslog avec :

```console 
User@localhost:~$ cp /var/log/syslog log.txt
``` 

On l'ouvre avec nano :

```console 
User@localhost:~$ nano log.txt
``` 

Pour voir le contenu , il nous faut les permissions , on fait 

```console 
User@localhost:~$ sudo chmod 777 log.txt
``` 

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

On vas dans le repertoire personel avec `cd ~`

On copie le .bashrc avec `cp .bashrc .bashrc\_bak`

On verifie avec `ls –la`

2 : on cherche la ligne avec ctrl + W , puis on la décommente

3 : on recharge le .bash avec `source .bashrc\_bak`

4 : on fait les changement de couleur necessaire et on ajoute l'heure .

 ![](/Images/IMG_5.png)
 
 Aprés rechargement , cela fonctionne!
