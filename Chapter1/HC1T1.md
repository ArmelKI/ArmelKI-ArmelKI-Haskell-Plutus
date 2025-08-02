# 🔗 HC1T1 — Composition de fonctions en Haskell

---

## 📝 Présentation

Ce premier exercice m’a permis de découvrir la **composition de fonctions** en Haskell, une idée centrale du paradigme fonctionnel.

L’objectif : construire une fonction `doubleThenIncrement` qui combine deux opérations simples et successives :
- `double` : multiplie un entier par deux
- `increment` : ajoute 1

Plutôt que d’imbriquer les appels (`increment (double x)`), j’utilise l’opérateur `(.)` pour **composer les deux** et écrire `doubleThenIncrement = increment . double`, ce qui me paraît plus lisible, plus élégant et plus fonctionnel.

---

---

## 🔧 Code complet (avec `main`)

```haskell
-- HC1T1.hs

-- Multiplie un entier par 2
double :: Int -> Int
double x = x * 2

-- Ajoute 1 à un entier
increment :: Int -> Int
increment x = x + 1

-- Compose les deux opérations : double, puis increment
doubleThenIncrement :: Int -> Int
doubleThenIncrement = increment . double

-- Fonction principale avec quelques tests
main :: IO ()
main = do
  print (doubleThenIncrement 3)     -- 7
  print (doubleThenIncrement 0)     -- 1
  print (doubleThenIncrement (-4))  -- -7
  print (doubleThenIncrement 100)   -- 201
```

---

## 🗂️ Décryptage détaillé

### 🔸 `double :: Int -> Int`

Cette fonction prend un entier `x` et renvoie `x * 2`. C’est une fonction **pure**, sans effet secondaire :
- Elle agit uniquement sur sa donnée d’entrée.
- Elle est réutilisable dans plein de contextes : par exemple `map double` pour doubler chaque élément d’une liste.

---

### 🔸 `increment :: Int -> Int`

Même logique que `double`, mais ici on ajoute 1 :
- Ça pourrait représenter une opération sur des indices, des compteurs…
- L’idée c’est d’avoir des **fonctions simples, indépendantes**, qu’on peut combiner.

---

### 🔸 `doubleThenIncrement = increment . double`

Ici, j’utilise **l’opérateur `(.)`** pour composer deux fonctions :
- `f . g` signifie “appliquer `g` puis appliquer `f`”, donc ici on fait `double`, puis `increment`.
- Avantage : pas besoin d’écrire `x`, on laisse Haskell inférer le lien entre les fonctions.
- Ça **clarifie la logique** et ça me force à penser en termes de transformations successives.

---

### 🔸 `main :: IO ()`

La fonction `main` me permet de **vérifier les résultats** en affichant quelques cas test :
- J’apprends ici à intégrer mes fonctions dans un petit programme exécutable.
- C’est aussi une manière de valider mon raisonnement avec des entrées variées.

---

## ✅ Cas de test

| Entrée | Étapes                         | Résultat |
|--------|--------------------------------|----------|
| 3      | `double(3) = 6` → `increment(6)` | 7        |
| 0      | `double(0) = 0` → `increment(0)` | 1        |
| -4     | `double(-4) = -8` → `increment(-8)` | -7     |
| 100    | `double(100) = 200` → `increment(200)` | 201   |

---

## 🧠 Zoom sur le concept : composition `(.)`

| Concept              | Pourquoi c’est utile                                             |
|----------------------|------------------------------------------------------------------|
| Composition `(.)`    | Permet d’enchaîner les fonctions sans intermédiaire explicite.   |
| Style fonctionnel    | Favorise un code clair, typé, sans variable temporaire.          |
| Réutilisation        | `double` et `increment` restent utilisables séparément.          |
| Intuition mathématique | Similaire à `f(g(x))`, donc assez naturel à raisonner.         |

---

## 🗒️ Mon avis personnel

Je commence à ressentir ce que ça fait de penser en **fonctions pures**. Au lieu d’imaginer “les étapes d’un programme”, je commence à raisonner en “transformations successives” sur mes données. C’est agréable à écrire, et surtout très lisible une fois documenté. Je trouve que ça donne un code qui parle tout seul, et j’espère garder ce style dans tous les prochains exercices.

---

## 📂 Fichiers associés

- `HC1T1.hs` → Code source Haskell
- `HC1T1.md` → Documentation personnelle

---
