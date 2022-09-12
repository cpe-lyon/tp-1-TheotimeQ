**Quere Theotime 3ICS**

# Table des matières

[Exercice 1.Variables d'environnement](#Anch1)

[Exercice 2.Contrôle de mot de passe](#Anch2)

[Exercice 3.Expression rationelles](#Anch3)

[Exercice 4.Controle d'utilisateur](#Anch4)

[Exercice 5.Factorielle](#Anch5)

[Exercice 6.Le juste prix](#Anch6)

[Exercice 7.Statistique](#Anch7)

# Exercice 1. Variables d'environnement [Anch1]

## 1 : Dans quels dossiers bash trouve-t-il les commandes tapées par l’utilisateur ?

Toutes les commandes ce trouvent dans les fichiers specifié dans la variable d'environnement PATH .
```console 
User@localhost:~$ printenv PATH
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
```

## 2 : Quelle variable d’environnement permet à la commande cd tapée sans argument de vous ramener dans votre répertoire personnel ?

La variable d'environnement `$HOME` permet au cd de trouver le repertoire personnel quand il n'y a pas d'argument.
```console 
User@localhost:~$ printenv HOME
/home/User
```
Dans notre cas , HOME contient `/home/User`

## 3 : Explicitez le rôle des variables LANG, PWD, OLDPWD, SHELL

`LANG` : contient la langue des messages à afficher

`PWD` : contient le chemin absolu vers le répertoire courant

`OLDPWD` : contient le chemin absolu vers le répertoire courant précédent 

`SHELL` : l'interpreteur shell utilisé par défaut. La valeur habituelle sous linux est /bin/bash

## 4 : Créez une variable locale MY_VAR (le contenu n’a pas d’importance). Vérifiez que la variable existe

Pour creer une variable , on tape : 
```console 
User@localhost:~$MY_VAR="coucou maman"
```
Pour verifier son existance : 
```console 
User@localhost:~$ echo $MY_VAR
coucou maman
```

## 5 : Tapez ensuite la commande bash. Que fait-elle ? La variable MY_VAR existe-t-elle ? Expliquez. A la fin de cette question, tapez la commande exit pour revenir dans votre session initiale.

Apres avoir lancé bash , la variable MY_VAR n'existe plus . En effet MY_VAR à été crée seulement dans le shell car c'est une variable local. Elle n'existe donc pas dans bash

Une fois exit , on peut retrouver notre variable.

## 6 : Transformez MY_VAR en une variable d’environnement et recommencez la question précédente. Expliquez.

On transforme MY_VAR en variable d'environnement 
```console 
User@localhost:~$ export MY_VAR="coucou maman"
```
Cette fois ci apres avoir lancé bash on peut retrouver notre variable : 
```console 
User@localhost:~$ printenv $MY_VAR
coucou maman
```

## 7 : Créer la variable d’environnement NOM ayant pour contenu vos prénom et nom séparés par un espace.Afficher la valeur de NOM pour vérifier que l’affectation est correcte.

On creer la variable d'envirennement NOM : 
```console 
User@localhost:~$ export NOM="Theotime Quere"
```
On affiche sa valeur : 
```console 
User@localhost:~$ printenv NOM
Theotime Quere
```

## 8 : Ecrivez une commande qui affiche ”Bonjour à vous, prenom nom !” en utilisant la variable NOM

```console 
User@localhost:~$ echo "Bonjour à vous, $NOM !"
Bonjour à vous, Theotime Quere !
```

## 9 Quelle différence y a-t-il entre donner une valeur vide à une variable d’environnement et l’utilisation de la commande unset ?

Quand on donne une valeur vide , la variable existe mais n'a pas de valeur . Avec Unset , la variable n'existe plus , elle est effacée.

## 10 : Utilisez la commande echo pour écrire exactement la phrase : $HOME = chemin (où chemin est votre dossier personnel d’après bash)

```console 
User@localhost:~$ echo "$\HOME = $HOME"
$HOME = /home/User
```

# -- Programmation Bash --

# Exercice 2. Contrôle de mot de passe [Anch2]

## Écrivez un script testpwd.sh qui demande de saisir un mot de passe et vérifie s’il correspond ou non au contenu d’une variable PASSWORD dont le contenu est codé en dur dans le script. Le mot de passe saisi par l’utilisateur ne doit pas s’afficher.

```bash
#!/bin/bash

PASSWORD='test'

read -p 'Mot de passe :' -s mdp 

if [[ $mdp == $password ]]
then 
  echo 'Bon mot de passe'
else 
  echo 'Mauvais mot de passe'
fi
```

 ![](/TP2_IMG/TP2_1.png)

# Exercice 3. Expression rationelles [Anch3]

## Ecrivez un script qui prend un paramètre et utilise la fonction suivante pour vérifier que ce paramètre est un nombre réel :

```bash 
function is_number()
{
  re='^[+-]?[0-9]+([.][0-9]+)?$'
  if ! [[ $1 =~ $re ]] ; then
    return 1
  else
    return 0
  fi
}
```
* Il affichera un message d’erreur dans le cas contraire. *

# Exercice 4. Controle d'utilisateur [Anch4]

## Écrivez un script qui vérifie l’existence d’un utilisateur dont le nom est donné en paramètre du script. Si le script est appelé sans nom d’utilisateur, il affiche le message : ”Utilisation : nom_du_script nom_utilisateur”, où nom_du_script est le nom de votre script récupéré automatiquement (si vous changez le nom de votre script, le message doit changer automatiquement)

# Exercice 5. Factorielle [Anch5]

## Écrivez un programme qui calcule la factorielle d’un entier naturel passé en paramètre (on supposera que l’utilisateur saisit toujours un entier naturel).

# Exercice 6. Le juste prix [Anch6]

## Écrivez un script qui génère un nombre aléatoire entre 1 et 1000 et demande à l’utilisateur de le deviner. Le programme écrira ”C’est plus !”, ”C’est moins !” ou ”Gagné !” selon les cas (vous utiliserez $RANDOM).

# Exercice 7. Statistiques [Anch7]

## 1. Écrivez un script qui prend en paramètres trois entiers (entre -100 et +100) et affiche le min, le max et la moyenne. Vous pouvez réutiliser la fonction de l’exercice 3 pour vous assurer que les paramètres sont bien des entiers.

## 2. Généralisez le programme à un nombre quelconque de paramètres (pensez à SHIFT)
## 3. Modifiez votre programme pour que les notes ne soient plus données en paramètres, mais saisies et stockées au fur et à mesure dans un tableau.

# Exercice 8. Statistiques [Anch8]

## Écrivez un script qui affiche les combinaisons possibles de couleurs (cf. TP 1) :


unzip > opy.zip 2>> /var/log | analyse 2> erreurs analyse/log | correction 2> erreur-correction.log | tee notes.csv | moyenne
