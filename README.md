# Battle Ice Breaker

Ce site est hébergé sur GitHub Pages et disponible à l'adresse suivante : https://agileanddevopstoolkit.github.io/battle-ice-breaker/

## Description

Battle Ice Breaker est une mini application web qui permet d'organiser une battle de préférences.

Le principe est simple :
- Vous chargez une liste au format `.txt`.
- L'application affiche deux propositions.
- Vous choisissez votre proposition préférée à chaque duel.
- Le gagnant reste en place jusqu'à ce qu'il ne reste plus qu'un champion.

## Fonctionnalités

- Chargement d'un fichier `.txt` par glisser-déposer ou via le bouton Parcourir.
- Détection d'erreurs de format avec message explicite.
- Suppression automatique des doublons (insensible à la casse).
- Bouton Recharger pour rouvrir la zone de chargement.
- Bouton Reset pour redémarrer la battle avec la même liste.
- Affichage du gagnant final.

## Format du fichier d'entrée

Le fichier doit respecter la structure suivante :
- Ligne 1 : le thème (voir règles ci-dessous)
- Lignes suivantes : une entrée par ligne

Règles pour la ligne 1 :
- Si la ligne commence par `Ton` ou `Ta` (insensible à la casse), ce mot est retiré du type de liste et sert à définir le genre.
- Le type de liste est ensuite :
	- le 2e mot si la ligne commence par `Ton` ou `Ta`
	- sinon le 1er mot

Exemples valides de ligne 1 :
- `Superhéro` -> type = `Superhéro`, genre = `ton`
- `Ton superhéro` -> type = `superhéro`, genre = `ton`
- `Ta musique` -> type = `musique`, genre = `ta`

Le genre est utilisé dans la phrase finale :
- `Ton ...` -> `ton superhéro préféré`
- `Ta ...` -> `ta musique préférée`

Exemple complet de fichier :

```txt
Ta musique
Bohemian Rhapsody
Billie Jean
Smells Like Teen Spirit
Imagine
```

Dans cet exemple :
- type = `musique`
- genre = `ta`
- phrase finale attendue : `TA MUSIQUE PRÉFÉRÉE EST :`

### Commentaires

Il est possible d'annoter le fichier à l'aide de commentaires avec `//` :

- Une ligne commençant par `//` est entièrement ignorée.
- Sur une ligne d'item, tout ce qui suit `//` est ignoré (commentaire de fin de ligne).

Exemple :

```txt
Superhéro
// Héros Marvel
Spider-Man
Iron Man // mon super héro préféré
Captain America
// Héros DC (ignorés ici)
// Batman
Thor
Hulk
```

Un exemple prêt à l'emploi est disponible dans `listes-exemples/Superhéro.txt`.

## Utilisation

### En ligne

Ouvrez directement le site ici :
https://agileanddevopstoolkit.github.io/battle-ice-breaker/

### En local

Ce projet est un simple fichier HTML, vous n'avez donc pas besoin de lancer un serveur local.

Il suffit d'ouvrir le fichier `index.html` dans votre navigateur pour utiliser l'application.

## Structure du projet

- `index.html` : interface, styles et logique JavaScript.
- `listes-exemples/` : exemples de listes.
- `README.md` : documentation du projet.

## Technologies

- HTML5
- CSS3
- JavaScript (vanilla)