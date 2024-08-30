# Documentation du mini-language de Programmation AlgoX

## Table des matières
1. [Introduction](#introduction)
2. [Structure de base](#structure-de-base)
3. [Types de données](#types-de-données)
4. [Variables](#variables)
5. [Constantes](#constantes)
6. [Opérateurs](#opérateurs)
7. [Structures de contrôle](#structures-de-contrôle)
8. [Fonctions et Procédures](#fonctions-et-procédures)
9. [Entrée et Sortie](#entrée-et-sortie)
10. [Tableaux](#tableaux)
11. [Enregistrements (Structures)](#enregistrements-structures)

## 1. Introduction

AlgoX est un langage de programmation procédural conçu à des fins éducatives. Il combine des éléments de pseudocode avec des constructions de programmation plus formelles, ce qui le rend adapté à l'apprentissage de la pensée algorithmique et des concepts de base de la programmation.

## 2. Structure de base

Un programme AlgoX a la structure générale suivante :

```
Algorithme nomAlgo

  [Déclaration des constantes]
  [Déclaration des variables]
  [Déclaration des fonctions et procédures]

debut
  [Code du programme principal]
fin
```

## 3. Types de données

AlgoX prend en charge les types de données de base suivants :

- `ENTIER`
- `REEL`
- `CHAINE`
- `BOOLEEN` (déduit de l'utilisation)

## 4. Variables

Les variables sont déclarées dans le format suivant :

```
Variable
var nomVariable: type [<- valeurInitiale];
```

Exemple :
```
var nomUser: chaîne <- "Alice";
var ageUser: entier <- 30;
```

Plusieurs variables du même type peuvent être déclarées sur une seule ligne :

```
var aa, bb, cc, dd: entier;
```

## 5. Constantes

Les constantes sont déclarées en utilisant le mot-clé `Constante` :

```
Constante
const NOM_CONSTANTE : Type <- valeur;
```

Exemple :
```
const PI : Entier <- 3.14;
const MAX_FACTORIELLE : Entier <- 20;
```

## 6. Opérateurs

AlgoX prend en charge les opérateurs suivants :

- Arithmétiques : `+`, `-`, `*`, `/`, `%` (modulo), `^` (exponentiation)
- Comparaison : `>`, `<`, `>=`, `<=`, `=`, `<>` (différent)
- Logiques : `et`, `ou`
- Affectation : `<-`

## 7. Structures de contrôle

### Instructions conditionnelles

#### Si-Sinon

```
si (condition) alors
  [instructions]
sinon si (condition) alors
  [instructions]
sinon
  [instructions]
fin si
```

#### Switch (Selon)

```
selon(variable)
  cas valeur1: [instructions]
  cas valeur2: [instructions]
  defaut: [instructions]
fin selon
```

### Boucles

#### Boucle Pour

```
pour variable de debut à fin faire
  [instructions]
fin pour
```

#### Boucle Tant que

```
tant que condition faire
  [instructions]
fin tant que
```

#### Boucle Faire-Tant que

```
faire
  [instructions]
tant que(condition)
```

## 8. Fonctions et Procédures

### Fonctions

Les fonctions sont déclarées comme suit :

```
fonction nomFonction(parametre1: Type, parametre2: Type): TypeRetour
  [Variables locales]
Début
  [instructions]
  retourner valeur;
fin fonction
```

Exemple :
```
fonction factorielle(n: Entier) : Entier
  Var resultatLocal : Entier;
Début
  si n <= 1 alors
    retourner 1;
  sinon
    resultatLocal <- n * factorielle(n - 1);
    retourner resultatLocal;
  fin si
fin fonction
```

### Procédures

Les procédures sont similaires aux fonctions mais ne retournent pas de valeur :

```
PROCEDURE nomProcedure(parametre: Type)
DEBUT
  [instructions]
FIN PROCEDURE
```

Exemple :
```
PROCEDURE afficherMessage(message: CHAINE)
DEBUT
  AFFICHER(message)
FIN PROCEDURE
```

## 9. Entrée et Sortie

### Sortie

- `écrire(...)` ou `afficher(...)` : Affiche la sortie sur la console
- Plusieurs éléments peuvent être affichés dans une seule instruction, séparés par des virgules

### Entrée

- `lire(variable)` ou `saisir(variable)` : Lit l'entrée de l'utilisateur

## 10. Tableaux

Les tableaux sont déclarés et utilisés comme suit :

```
Tableau nomTableau : Tableau[taille] de Type
```

Exemple :
```
Tableau list : Tableau[5] de Entier <- [1, 4, 3, 20, 15];
```

Accès aux éléments du tableau :
```
list[index]
```

## 11. Enregistrements (Structures)

Les enregistrements sont définis en utilisant le mot-clé `ENREGISTREMENT` :

```
ENREGISTREMENT NomEnregistrement
  champ1 : Type;
  champ2 : Type;
  ...
FIN ENREGISTREMENT
```

Exemple :
```
ENREGISTREMENT Etudiant
  nom : CHAINE;
  age : ENTIER;
  moyenne : REEL;
FIN ENREGISTREMENT
```

Déclaration et utilisation des enregistrements :
```
VAR etudiant1 : Etudiant;
etudiant1.nom <- "Alice";
etudiant1.age <- 20;
etudiant1.moyenne <- 15.5;
```

Les tableaux d'enregistrements sont également pris en charge :
```
Tableau classe : Tableau[3] de Etudiant;
```

Cette documentation fournit un aperçu des principales caractéristiques et de la syntaxe du langage de programmation AlgoX. Elle peut servir de guide de référence rapide pour les utilisateurs qui apprennent ou travaillent avec AlgoX.


# Exemples d'Algorithmes en AlgoX


## 1. Calcul de la somme des nombres de 1 à n

```
Algorithme SommeDesNombres

Variable
  var n : entier;
  var somme : entier <- 0;

debut
  écrire("Entrez un nombre entier positif : ");
  lire(n);
  
  pour i de 1 à n faire
    somme <- somme + i;
  fin pour
  
  écrire("La somme des nombres de 1 à ", n, " est : ", somme);
fin
```

## 2. Vérification de nombre pair ou impair

```
Algorithme PairOuImpair

Variable
  var nombre : entier;

debut
  écrire("Entrez un nombre entier : ");
  lire(nombre);
  
  si nombre % 2 = 0 alors
    écrire(nombre, " est pair.");
  sinon
    écrire(nombre, " est impair.");
  fin si
fin
```

## 3. Calcul de la factorielle

```
Algorithme Factorielle

Variable
  var n : entier;
  var resultat : entier <- 1;

debut
  écrire("Entrez un nombre entier positif : ");
  lire(n);
  
  pour i de 1 à n faire
    resultat <- resultat * i;
  fin pour
  
  écrire("La factorielle de ", n, " est : ", resultat);
fin
```

## 4. Recherche du maximum dans un tableau

```
Algorithme MaximumTableau

Variable
  Tableau nombres : Tableau[5] de Entier;
  var max : entier;

debut
  pour i de 0 à 4 faire
    écrire("Entrez le nombre ", i + 1, " : ");
    lire(nombres[i]);
  fin pour
  
  max <- nombres[0];
  
  pour i de 1 à 4 faire
    si nombres[i] > max alors
      max <- nombres[i];
    fin si
  fin pour
  
  écrire("Le plus grand nombre est : ", max);
fin
```

## 5. Calcul de la moyenne d'une série de nombres

```
Algorithme MoyenneSerie

Variable
  var n : entier;
  var somme : reel <- 0;
  var nombre : reel;

debut
  écrire("Combien de nombres voulez-vous entrer ? ");
  lire(n);
  
  pour i de 1 à n faire
    écrire("Entrez le nombre ", i, " : ");
    lire(nombre);
    somme <- somme + nombre;
  fin pour
  
  écrire("La moyenne est : ", somme / n);
fin
```

## 6. Vérification de nombre premier

```
Algorithme NombrePremier

Variable
  var n : entier;
  var estPremier : booleen <- vrai;

debut
  écrire("Entrez un nombre entier positif : ");
  lire(n);
  
  si n <= 1 alors
    estPremier <- faux;
  sinon
    pour i de 2 à n - 1 faire
      si n % i = 0 alors
        estPremier <- faux;
      fin si
    fin pour
  fin si
  
  si estPremier alors
    écrire(n, " est un nombre premier.");
  sinon
    écrire(n, " n'est pas un nombre premier.");
  fin si
fin
```

## 7. Conversion de température Celsius en Fahrenheit

```
Algorithme ConversionTemperature

Variable
  var celsius : reel;
  var fahrenheit : reel;

debut
  écrire("Entrez la température en Celsius : ");
  lire(celsius);
  
  fahrenheit <- (celsius * 9/5) + 32;
  
  écrire(celsius, "°C équivaut à ", fahrenheit, "°F");
fin
```

## 8. Calcul du PGCD de deux nombres

```
Algorithme PGCD

Variable
  var a : entier;
  var b : entier;
  var temp : entier;

debut
  écrire("Entrez le premier nombre : ");
  lire(a);
  écrire("Entrez le deuxième nombre : ");
  lire(b);
  
  tant que b <> 0 faire
    temp <- b;
    b <- a % b;
    a <- temp;
  fin tant que
  
  écrire("Le PGCD est : ", a);
fin
```

## 9. Génération de la suite de Fibonacci

```
Algorithme Fibonacci

Variable
  var n : entier;
  var a : entier <- 0;
  var b : entier <- 1;
  var c : entier;

debut
  écrire("Combien de termes de la suite de Fibonacci voulez-vous ? ");
  lire(n);
  
  écrire("Suite de Fibonacci : ");
  
  pour i de 1 à n faire
    écrire(a, " ");
    c <- a + b;
    a <- b;
    b <- c;
  fin pour
fin
```

## 10. Tri à bulles d'un tableau

```
Algorithme TriBulles

Variable
  Tableau nombres : Tableau[5] de Entier;
  var temp : entier;

debut
  pour i de 0 à 4 faire
    écrire("Entrez le nombre ", i + 1, " : ");
    lire(nombres[i]);
  fin pour
  
  pour i de 0 à 3 faire
    pour j de 0 à 3 - i faire
      si nombres[j] > nombres[j + 1] alors
        temp <- nombres[j];
        nombres[j] <- nombres[j + 1];
        nombres[j + 1] <- temp;
      fin si
    fin pour
  fin pour
  
  écrire("Tableau trié : ");
  pour i de 0 à 4 faire
    écrire(nombres[i], " ");
  fin pour
fin
```

## 11. Calcul du n-ième nombre de Fibonacci (avec fonction récursive)

```
Algorithme FibonacciRecursif

fonction fib(n: Entier): Entier
Début
    si n <= 1 alors
        retourner n;
    sinon
        retourner fib(n - 1) + fib(n - 2);
    fin si
fin fonction

Variable
    var n : entier;

debut
    écrire("Entrez la position du nombre de Fibonacci que vous voulez calculer : ");
    lire(n);
    écrire("Le ", n, "-ième nombre de Fibonacci est : ", fib(n));
fin
```

## 12. Calcul de l'aire et du périmètre d'un cercle (avec procédures)

```
Algorithme AirePerimetreCercle

Constante
    const PI : Reel <- 3.14159;

PROCEDURE calculerAire(rayon: Reel)
DEBUT
    var aire : Reel;
    aire <- PI * rayon * rayon;
    AFFICHER("L'aire du cercle est : ", aire);
FIN PROCEDURE

PROCEDURE calculerPerimetre(rayon: Reel)
DEBUT
    var perimetre : Reel;
    perimetre <- 2 * PI * rayon;
    AFFICHER("Le périmètre du cercle est : ", perimetre);
FIN PROCEDURE

Variable
    var rayon : Reel;

debut
    écrire("Entrez le rayon du cercle : ");
    lire(rayon);
    calculerAire(rayon);
    calculerPerimetre(rayon);
fin
```

## 13. Gestion d'une bibliothèque (avec enregistrements)

```
Algorithme GestionBibliotheque

ENREGISTREMENT Livre
    titre : CHAINE;
    auteur : CHAINE;
    anneePublication : ENTIER;
    estEmprunte : BOOLEEN;
FIN ENREGISTREMENT

PROCEDURE afficherLivre(livre: Livre)
DEBUT
    AFFICHER("Titre : ", livre.titre);
    AFFICHER("Auteur : ", livre.auteur);
    AFFICHER("Année de publication : ", livre.anneePublication);
    si livre.estEmprunte alors
        AFFICHER("Statut : Emprunté");
    sinon
        AFFICHER("Statut : Disponible");
    fin si
    AFFICHER("-------------------------");
FIN PROCEDURE

Variable
    Tableau bibliotheque : Tableau[3] de Livre;

debut
    // Initialisation des livres
    bibliotheque[0].titre <- "1984";
    bibliotheque[0].auteur <- "George Orwell";
    bibliotheque[0].anneePublication <- 1949;
    bibliotheque[0].estEmprunte <- faux;

    bibliotheque[1].titre <- "Le Petit Prince";
    bibliotheque[1].auteur <- "Antoine de Saint-Exupéry";
    bibliotheque[1].anneePublication <- 1943;
    bibliotheque[1].estEmprunte <- vrai;

    bibliotheque[2].titre <- "Cent ans de solitude";
    bibliotheque[2].auteur <- "Gabriel García Márquez";
    bibliotheque[2].anneePublication <- 1967;
    bibliotheque[2].estEmprunte <- faux;

    // Affichage des livres
    AFFICHER("Catalogue de la bibliothèque :");
    pour i de 0 à 2 faire
        afficherLivre(bibliotheque[i]);
    fin pour
fin
```

## 14. Calcul de statistiques sur un ensemble de notes (avec fonctions et enregistrements)

```
Algorithme StatistiquesNotes

ENREGISTREMENT Statistiques
    moyenne : REEL;
    minimum : REEL;
    maximum : REEL;
FIN ENREGISTREMENT

fonction calculerMoyenne(notes: Tableau de REEL, taille: ENTIER): REEL
Début
    var somme : REEL <- 0;
    pour i de 0 à taille - 1 faire
        somme <- somme + notes[i];
    fin pour
    retourner somme / taille;
fin fonction

fonction trouverMinimum(notes: Tableau de REEL, taille: ENTIER): REEL
Début
    var min : REEL <- notes[0];
    pour i de 1 à taille - 1 faire
        si notes[i] < min alors
            min <- notes[i];
        fin si
    fin pour
    retourner min;
fin fonction

fonction trouverMaximum(notes: Tableau de REEL, taille: ENTIER): REEL
Début
    var max : REEL <- notes[0];
    pour i de 1 à taille - 1 faire
        si notes[i] > max alors
            max <- notes[i];
        fin si
    fin pour
    retourner max;
fin fonction

Variable
    Tableau notes : Tableau[5] de REEL;
    var stats : Statistiques;

debut
    // Saisie des notes
    pour i de 0 à 4 faire
        écrire("Entrez la note ", i + 1, " : ");
        lire(notes[i]);
    fin pour

    // Calcul des statistiques
    stats.moyenne <- calculerMoyenne(notes, 5);
    stats.minimum <- trouverMinimum(notes, 5);
    stats.maximum <- trouverMaximum(notes, 5);

    // Affichage des résultats
    écrire("Statistiques des notes :");
    écrire("Moyenne : ", stats.moyenne);
    écrire("Note minimale : ", stats.minimum);
    écrire("Note maximale : ", stats.maximum);
fin
```
