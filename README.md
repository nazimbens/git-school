# git-school


## Partie 1: Configuration initiale
### 1. Créer un repo en local ou sur GitHub et le cloner
```
#Créer un nouveau repo sur GitHub (si nécessaire)
# ou cloner un repo existant
git clone <URL_du_repo>
```
### 2. Introduire des fichiers et des dossiers
```
# Créer des fichiers et des dossiers
touch hello.py
```
Ajouter le code Python suivant : 
```
#hello.py
print('Hello World!")
```

### 3. Ajouter et valider les modifications
```
git add . ou #git add hello.py car on a un seul fichier
git commit -m "Add hello.py"
```
### 4. Pousser les fichiers et dossiers dans le branch main
```
git push origin main
```

## Partie 2: Développement de fonctionnalités
### 1. Créer une branche dev et une feature
Création d'une branche dev
```
git checkout -b dev
```
Intégration du code python
```
# hello.py
def greet(name):
    print("Hello, " + name + "!")
greet("Alice")
```
Ajouter ces changements dans le staging
```
git add .
git commit -m "Add greet function"
```

### 2. Fusionner la branche dev dans main

```
git checkout main
git merge dev
```

## Partie 3: Test des fonctionnalités
### 1. Créer une branche dev-test et tester plusieurs fonctionnalités

```
git checkout -b dev-test
```

Création d'une nouvelle fonction
```
# hello.py
def greet(name):
    print("Hello, " + name + "!")

greet("Bob")

def farewell(name):
    print("Goodbye, " + name + "!")

farewell("Alice")
```
Ajout de la fonction 
```
git add .
git commit -m "Add farewell function for Alice"
```
Création d'une nouvelle fonction
```
# hello.py
def greet(name):
    print("Hello, " + name + "!")

greet("Bob")

def farewell(name):
    print("Goodbye, " + name + "!")

farewell("Alice")

def ask():
    print("How are you?")

ask()
```
Ajout de la fonction
```
git add .
git commit -m "Add ask function"
```
Création d'une nouvelle fonction
```
# hello.py
def greet(name):
    print("Hello, " + name + "!")

greet("Bob")

def farewell(name):
    print("Goodbye, " + name + "!")

farewell("Alice")

def ask():
    print("How are you?")

ask()

def thanks():
    print("Thank you for your time!")

thanks()
```
Ajout de la fonction
```
git add .
git commit -m "Add thanks function"
```
## Partie 3: Test des fonctionnalités
### 1. Revenir en arrière de deux commits avec git reset

```
git reset --hard HEAD~2
```

Cela ajoute plusieurs fonctionnalités à notre script hello.py dans la branche dev-test, puis revient en arrière de deux commits pour annuler les deux derniers commits réalisés dans cette branche.

### 2. Revenir en arrière de deux commits avec git rebase
```
git rebase -i HEAD~4
```
Cela ouvrira une interface interactive où vous pourrez choisir les commits que vous souhaitez conserver, modifier ou supprimer. Supprimez les deux commits que vous souhaitez annuler, puis sauvegardez et fermez l'éditeur.

### 3. Revenir en arrière de deux commits avec git revert

```
git log
```
Notez les identifiants des deux commits que vous souhaitez annuler.

```
git revert <ID_commit1> <ID_commit2>
```
Git créera deux nouveaux commits qui annuleront les modifications apportées par les commits spécifiés.

Ces méthodes vous permettent de revenir en arrière sur les commits précédents de différentes manières, en gardant à l'esprit que `git rebase` réécrit l'historique des commits, tandis que `git revert` crée de nouveaux commits pour annuler les modifications des commits spécifiés.

## Partie 4: Finaliser le projet
### 1. Résoudre les éventuelles confilts de fusion 
```
git add .
git commit -m "Résolution des conflits de fusion"
git push origin dev-test
```
### 2. Pousser dans la branche main 
```
git checkout main
git merge dev-test
```

## Partie 5 : Ignorer un fichier avec un .gitignore
### 1. Créer le fichier 
```
touch file.txt
vim .gititngore
```

### 2. Ajouter la ligne suivante
```
file.txt
```

### 3. Ajouter et valider les modificatinons 
```
git add .gitignore
git commit -m "Add file.txt to .gitignore"
```

### 4. Vérifier que le fichier est ignoré
```
git status
```

### 5. Pousser les modifications dans la branche main
```
git push origin main
```
