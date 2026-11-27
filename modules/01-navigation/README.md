# Module 1 — Navigation et recherche de fichiers sous Linux

## 1. Présentation

Ce module présente les commandes fondamentales permettant de se déplacer dans l'arborescence Linux, d'afficher le contenu des répertoires et de rechercher des fichiers.

La maîtrise de ces commandes constitue une base essentielle pour l'administration des systèmes Linux.

## 2. Objectifs

À la fin de ce module, vous serez capable de :

- Identifier mon répertoire courant.
- Afficher les fichiers et dossiers.
- Naviguer entre les répertoires.
- Comprendre l'organisation de l'arborescence Linux.
- Rechercher des fichiers et des commandes.

## 3. Comprendre l'arborescence Linux

Linux organise les fichiers et les répertoires sous la forme d'une arborescence.

Le répertoire principal est appelé la racine et est représenté par `/`.

Exemple :

```text
/
├── home
│   └── utilisateur
│       ├── Documents
│       ├── Téléchargements
│       └── Projets
├── etc
├── var
├── usr
└── tmp
```

Quelques répertoires importants :

| Répertoire | Rôle                                                |
| ---------- | --------------------------------------------------- |
| `/`        | Racine du système                                   |
| `/home`    | Répertoires personnels des utilisateurs             |
| `/etc`     | Fichiers de configuration                           |
| `/var`     | Données variables, journaux et fichiers de services |
| `/usr`     | Applications et ressources système                  |
| `/tmp`     | Fichiers temporaires                                |

## 4. La commande `pwd`

### Rôle

La commande `pwd` signifie *Print Working Directory*.

Elle permet d'afficher le chemin absolu du répertoire dans lequel je me trouve.

### Syntaxe

```bash
pwd
```

### Exemple

```bash
pwd
```

Résultat possible :

```text
/home/utilisateur
```

Cela signifie que mon répertoire courant est `/home/utilisateur`.

## 5. La commande `ls`

### Rôle

La commande `ls` permet d'afficher le contenu d'un répertoire.

### Syntaxe

```bash
ls
```

### Options importantes

| Commande | Rôle                                       |
| -------- | ------------------------------------------ |
| `ls`     | Afficher le contenu                        |
| `ls -l`  | Affichage détaillé                         |
| `ls -a`  | Afficher aussi les fichiers cachés         |
| `ls -lh` | Affichage détaillé avec tailles lisibles   |
| `ls -la` | Affichage détaillé, fichiers cachés inclus |

### Exemple

```bash
ls -la
```

Cette commande affiche les fichiers et dossiers, y compris ceux dont le nom commence par un point.

## 6. La commande `cd`

### Rôle

La commande `cd` signifie *Change Directory*.

Elle permet de changer de répertoire.

### Syntaxe

```bash
cd chemin
```

### Exemples

Aller dans Documents :

```bash
cd Documents
```

Revenir au répertoire personnel :

```bash
cd ~
```

Remonter d'un niveau :

```bash
cd ..
```

Revenir au répertoire précédent :

```bash
cd -
```

## 7. Chemins absolus et relatifs

### Chemin absolu

Un chemin absolu commence toujours par `/`.

Exemple :

```bash
cd /home/utilisateur/Documents
```

### Chemin relatif

Un chemin relatif dépend du répertoire courant.

Exemple :

```bash
cd Documents
```

Si je me trouve dans `/home/utilisateur`, cette commande me conduit dans `/home/utilisateur/Documents`.

## 8. Conclusion

Les commandes `pwd`, `ls` et `cd` permettent de connaître ma position dans le système, d'afficher le contenu des répertoires et de naviguer dans l'arborescence Linux.

Elles sont indispensables pour travailler efficacement dans le terminal.

## 9. La commande `mkdir`

### Rôle

La commande `mkdir` signifie *Make Directory*.

Elle permet de créer un répertoire.

### Syntaxe

```bash
mkdir nom_du_repertoire
```

### Exemple

```bash
mkdir test
```

Cette commande crée un répertoire nommé `test`.

Pour créer plusieurs répertoires :

```bash
mkdir dossier1 dossier2 dossier3
```

Pour créer une arborescence complète :

```bash
mkdir -p projets/linux/module1
```

L'option `-p` permet de créer les répertoires parents nécessaires.

## 10. La commande `touch`

### Rôle

La commande `touch` permet de créer un fichier vide s'il n'existe pas.

Elle permet également de mettre à jour les dates d'accès et de modification d'un fichier existant.

### Syntaxe

```bash
touch nom_du_fichier
```

### Exemple

```bash
touch notes.txt
```

Cette commande crée le fichier `notes.txt` s'il n'existe pas.

## 11. La commande `cp`

### Rôle

La commande `cp` signifie *Copy*.

Elle permet de copier un fichier ou un répertoire.

### Syntaxe

```bash
cp source destination
```

### Exemple

```bash
cp notes.txt sauvegarde.txt
```

Cette commande crée une copie de `notes.txt` nommée `sauvegarde.txt`.

Pour copier un répertoire et son contenu :

```bash
cp -r dossier1 dossier2
```

L'option `-r` permet de copier récursivement le contenu d'un répertoire.

## 12. La commande `mv`

### Rôle

La commande `mv` signifie *Move*.

Elle permet de déplacer ou de renommer un fichier ou un répertoire.

### Exemple : renommer un fichier

```bash
mv notes.txt cours.txt
```

Le fichier `notes.txt` est renommé `cours.txt`.

### Exemple : déplacer un fichier

```bash
mv cours.txt Documents/
```

Cette commande déplace le fichier dans le répertoire `Documents`.

## 13. La commande `rm`

### Rôle

La commande `rm` signifie *Remove*.

Elle permet de supprimer des fichiers.

### Exemple

```bash
rm notes.txt
```

Cette commande supprime le fichier `notes.txt`.

Pour supprimer un répertoire vide :

```bash
rmdir test
```

Pour supprimer un répertoire et son contenu :

```bash
rm -r dossier1
```

**Attention :** la suppression avec `rm` ne passe généralement pas par la corbeille. Il faut vérifier soigneusement le chemin avant d'exécuter la commande.

## 14. Rechercher des fichiers avec `find`

La commande `find` permet de rechercher des fichiers et des dossiers dans un répertoire donné.

### Syntaxe

```bash
find chemin -name "nom"
```

### Exemples

Rechercher un fichier nommé `rapport.txt` dans le répertoire personnel :

```bash
find ~ -name "rapport.txt"
```

Rechercher tous les fichiers PDF dans le répertoire personnel :

```bash
find ~ -type f -name "*.pdf"
```

Rechercher les dossiers nommés `Documents` :

```bash
find ~ -type d -name "Documents"
```

- `-name` : recherche selon le nom.
- `-type f` : recherche uniquement les fichiers.
- `-type d` : recherche uniquement les dossiers.

## 15. Localiser une commande avec `which`

La commande `which` permet de connaître le chemin d'une commande disponible dans le système.

### Exemple

```bash
which ls
```

Résultat possible :

```text
/usr/bin/ls
```

Cela signifie que la commande `ls` se trouve dans `/usr/bin/`.

## 16. Utiliser `command -v`

La commande `command -v` permet également de vérifier si une commande est disponible et d'afficher son emplacement ou sa définition.

### Exemple

```bash
command -v nano
```

Résultat possible :

```text
/usr/bin/nano
```

## 17. Consulter le manuel avec `man`

La commande `man` permet de consulter le manuel détaillé d'une commande.

### Exemple

```bash
man ls
```

Dans le manuel :

- `↑` et `↓` : faire défiler le contenu.
- `/mot` : rechercher un mot.
- `n` : passer au résultat suivant.
- `q` : quitter le manuel.

## 18. Utiliser l'aide avec `--help`

De nombreuses commandes proposent une option `--help` pour afficher rapidement leur syntaxe et leurs principales options.

### Exemple

```bash
ls --help
```

Cette option est pratique lorsqu'on souhaite obtenir une aide rapide sans ouvrir le manuel complet.

## 19. Exercices pratiques

Les exercices suivants permettent de mettre en pratique les commandes étudiées dans ce module.

Pour éviter de modifier ou de supprimer des fichiers personnels, les exercices sont réalisés dans un répertoire de test.

### Préparation

Créer un répertoire de travail :

```bash
mkdir -p ~/linux-navigation-lab
```

Entrer dans ce répertoire :

```bash
cd ~/linux-navigation-lab
```

Vérifier le répertoire courant :

```bash
pwd
```

### Exercice 1 : créer une arborescence

Créer les dossiers suivants :

```text
linux-navigation-lab/
├── documents/
│   └── rapports/
├── images/
└── sauvegardes/
```

Commandes utilisées :

```bash
mkdir -p documents/rapports images sauvegardes
```

Vérifier le résultat :

```bash
ls -R
```

### Exercice 2 : créer des fichiers

Créer trois fichiers :

```bash
touch documents/notes.txt
touch documents/rapports/rapport.txt
touch images/photo.txt
```

Afficher les fichiers créés :

```bash
ls -R
```

### Exercice 3 : copier un fichier

Copier `notes.txt` dans le dossier `sauvegardes` :

```bash
cp documents/notes.txt sauvegardes/
```

Vérifier :

```bash
ls sauvegardes
```

### Exercice 4 : déplacer et renommer un fichier

Déplacer `photo.txt` dans le dossier `documents` :

```bash
mv images/photo.txt documents/
```

Renommer le fichier en `image-test.txt` :

```bash
mv documents/photo.txt documents/image-test.txt
```

Vérifier :

```bash
ls documents
```

### Exercice 5 : rechercher un fichier

Rechercher `rapport.txt` dans le répertoire de travail :

```bash
find ~/linux-navigation-lab -name "rapport.txt"
```

### Exercice 6 : afficher les fichiers cachés

Créer un fichier caché :

```bash
touch .fichier-cache
```

Afficher tous les fichiers, y compris les fichiers cachés :

```bash
ls -la
```

### Exercice 7 : nettoyer le répertoire de test

Après avoir terminé les exercices, quitter le répertoire :

```bash
cd ~
```

Supprimer le répertoire de test et son contenu :

```bash
rm -r ~/linux-navigation-lab
```

**Attention :** la commande `rm -r` supprime les fichiers et dossiers sans les envoyer dans la corbeille. Vérifier soigneusement le chemin avant de l'utiliser.

## 20. Conclusion du module

Dans ce module, vous avez appris à :

- Identifier votre répertoire courant avec `pwd`.
- Lister les fichiers et dossiers avec `ls`.
- Naviguer dans l'arborescence avec `cd`.
- Créer des dossiers et des fichiers avec `mkdir` et `touch`.
- Copier, déplacer et renommer des fichiers avec `cp` et `mv`.
- Supprimer des fichiers et des dossiers avec `rm` et `rmdir`.
- Rechercher des fichiers avec `find`.
- Localiser une commande et consulter son aide.

Ces connaissances constituent une base importante pour l'administration d'un système Linux.
