````md
# 🔗 HC1T1 — Composition de fonctions en Haskell

---

## 📝 Présentation

Dans cet exercice, je découvre comment composer plusieurs fonctions simples en Haskell. L’idée est d’enchaîner deux transformations :
- une fonction `double` qui multiplie un entier par 2
- une fonction `increment` qui ajoute 1

Je vais créer une fonction `doubleThenIncrement` qui combine les deux grâce à l’opérateur de composition `(.)`. L’objectif est de rendre le code plus clair et plus fonctionnel, en évitant les appels imbriqués.

---

## 🎯 Ce que j’ai cherché à comprendre

- Comment fonctionne la composition de fonctions en Haskell
- En quoi elle permet d’écrire du code plus lisible et modulable
- Comment structurer des fonctions simples pour les réutiliser

---

## 🔧 Code que j’ai écrit

```haskell
-- Multiplie un entier par 2
double :: Int -> Int
double x = x * 2

-- Ajoute 1 à un entier
increment :: Int -> Int
increment x = x + 1

-- Compose les deux opérations : double, puis increment
doubleThenIncrement :: Int -> Int
doubleThenIncrement = increment . double
```

Avec l’opérateur `(.)`, on peut écrire `increment . double` au lieu de `increment (double x)`. C’est plus concis et ça reflète bien la logique fonctionnelle.

---

## ✅ Quelques tests

J’ai testé la fonction sur plusieurs valeurs pour vérifier que tout fonctionne comme prévu :

| Entrée | Étapes                    | Résultat |
|--------|---------------------------|----------|
| 3      | `double(3) = 6`, `increment(6) = 7`   | 7        |
| 0      | `double(0) = 0`, `increment(0) = 1`   | 1        |
| -4     | `double(-4) = -8`, `increment(-8) = -7` | -7       |
| 100    | `double(100) = 200`, `increment(200) = 201` | 201   |

Tout fonctionne correctement, et je peux facilement réutiliser cette fonction dans d'autres programmes.

---

## 📚 Ce que j’ai retenu

| Concept            | Ce que j’en comprends                                                  |
|--------------------|------------------------------------------------------------------------|
| Composition `(.)`  | Permet d’enchaîner deux fonctions sans passer par une variable intermédiaire. |
| Fonctions pures    | Chaque fonction dépend uniquement de son entrée, sans effet secondaire.       |
| Typage explicite   | La signature `Int -> Int` aide à comprendre ce que la fonction attend et renvoie. |
| Clarté du code     | On obtient une définition plus lisible, proche d’une formule mathématique. |

---

## 🗒️ Mon avis personnel

Même si l’exercice est simple, il m’a permis de bien comprendre comment enchaîner des fonctions et à quel point Haskell encourage un style clair et modulaire. C’est une première étape vers des concepts plus avancés comme les fonctions d’ordre supérieur ou l’usage de `map`.

Ce fichier me servira de référence pour les prochaines tâches. Je documente ici chaque concept que je comprends au fur et à mesure, et je trouve ça motivant — ça me permet de voir ma progression et de produire un dépôt cohérent et structuré.

---

## 📂 Fichiers associés

- `HC1T1.hs` → Code source Haskell
- `HC1T1.md` → Documentation (ce fichier)

---
