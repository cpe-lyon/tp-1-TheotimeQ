**Quere Theotime 3ICS**

# Table des matières

[Exercice 1.Variables d'environnement]

[Exercice 2.Contrôle de mot de passe]

[Exercice 3.Expression rationelles]

[Exercice 4.Controle d'utilisateur]

[Exercice 5.Factorielle]

[Exercice 6.Le juste prix]

[Exercice 7.Statistique]

# Exercice 1. Variables d'environnement

## 1 : Dans quels dossiers bash trouve-t-il les commandes tapées par l’utilisateur ?

## 2 : Quelle variable d’environnement permet à la commande cd tapée sans argument de vous ramener dans votre répertoire personnel ?

## 3 : Explicitez le rôle des variables LANG, PWD, OLDPWD, SHELL

## 4 : Créez une variable locale MY_VAR (le contenu n’a pas d’importance). Vérifiez que la variable existe

## 5 : Tapez ensuite la commande bash. Que fait-elle ? La variable MY_VAR existe-t-elle ? Expliquez. A la fin de cette question, tapez la commande exit pour revenir dans votre session initiale.

## 6 : Transformez MY_VAR en une variable d’environnement et recommencez la question précédente. Expliquez.

## 7 : Créer la variable d’environnement NOM ayant pour contenu vos prénom et nom séparés par un espace.Afficher la valeur de NOM pour vérifier que l’affectation est correcte.

## 8 : Ecrivez une commande qui affiche ”Bonjour à vous, prenom nom !” en utilisant la variable NOM

## 9 Quelle différence y a-t-il entre donner une valeur vide à une variable d’environnement et l’utilisation de la commande unset ?

## 10 : Utilisez la commande echo pour écrire exactement la phrase : $HOME = chemin (où chemin est votre dossier personnel d’après bash)

# -- Programmation Bash --

# Exercice 2. Contrôle de mot de passe

## Écrivez un script testpwd.sh qui demande de saisir un mot de passe et vérifie s’il correspond ou non au contenu d’une variable PASSWORD dont le contenu est codé en dur dans le script. Le mot de passe saisi par l’utilisateur ne doit pas s’afficher.

# Exercice 3. Expression rationelles

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
Il affichera un message d’erreur dans le cas contraire.

# Exercice 4. Controle d'utilisateur

# Exercice 5. Factorielle

# Exercice 6. Le juste prix

# Exercice 7. Statistiques
