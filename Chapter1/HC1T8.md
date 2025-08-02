## 📘 Fichier : `HC1T8.md`

````md
# 🔁 HC1T8 — Tâche 8 : Fonctions d’ordre supérieur avec `applyTwice`

---

## 🎯 Objectif

Créer une fonction `applyTwice` qui prend :

- Une fonction `f`
- Une valeur `x`

et qui renvoie le résultat de `f (f x)` — autrement dit, appliquer `f` **deux fois** à `x`.

---

## 🧠 Concepts clés

| Concept                  | Description |
|--------------------------|-------------|
| Fonction d’ordre supérieur | Une fonction qui prend une autre fonction en argument |
| Application multiple     | `f (f x)` applique `f` une première fois, puis à nouveau |
| Polymorphisme            | Le type peut être générique si `f :: a -> a` |

---

## 🧪 Définition

```haskell
applyTwice :: (a -> a) -> a -> a
applyTwice f x = f (f x)
```

- `(a -> a) -> a -> a` : la fonction prend une transformation de type `a -> a`, une valeur `a`, et retourne un `a`
- Cela permet d'utiliser `applyTwice` avec des fonctions comme `(+1)`, `(*2)`, `reverse`, etc.

---

## 🌟 Exemples

| Appel                    | Résultat          | Explication |
|--------------------------|-------------------|-------------|
| `applyTwice (+1) 3`      | `5`               | `(+1)` appliqué deux fois : `4`, puis `5` |
| `applyTwice (*2) 2`      | `8`               | `2*2=4`, puis `4*2=8` |
| `applyTwice reverse "abc"` | `"abc"`         | `reverse "abc" = "cba"`, puis `reverse "cba" = "abc"` |

---

## 💬 Mon ressenti

J’adore ce genre de fonctions ! En les écrivant, je comprends mieux ce que signifie “traiter une fonction comme une valeur”. Haskell rend cela très fluide — on ne fait pas juste du calcul, on **compose des comportements**. C’est aussi très utile pour décomposer des chaînes de traitement ou réutiliser des transformations.

---

## 📂 Fichiers associés

- `HC1T8.hs` → Code avec tests
- `HC1T8.md` → Documentation commentée

---
