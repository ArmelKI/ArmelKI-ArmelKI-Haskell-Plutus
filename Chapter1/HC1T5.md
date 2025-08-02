## 📘 Fichier : `HC1T5_T5.md`

````md
# 🌀 HC1T5 — Tâche 5 : Paresse et listes infinies

---

## 🔍 Présentation

L’objectif est de créer une fonction `infiniteNumbers` qui génère une liste **infinie** de nombres, et de ne garder que les `n` premiers éléments. Cela semble impossible en programmation impérative... mais en Haskell, c’est une des forces du langage : **tout est évalué paresseusement** (lazy evaluation).

---

## 🧠 Concepts clés

| Concept             | Description |
|---------------------|-------------|
| Liste infinie       | `[1..]` génère tous les entiers à partir de 1 |
| Évaluation paresseuse | Les éléments ne sont calculés que lorsqu’on les demande |
| `take`              | Coupe une liste et garde les `n` premiers éléments |
| Composition         | `take n infiniteNumbers` reste une expression pure |

---

## 🔧 Code

```haskell
infiniteNumbers :: [Int]
infiniteNumbers = [1..]

takeFirstN :: Int -> [Int]
takeFirstN n = take n infiniteNumbers
```

---

## ✅ Tests

```haskell
main :: IO ()
main = do
  print (takeFirstN 0)    -- []
  print (takeFirstN 5)    -- [1,2,3,4,5]
  print (takeFirstN 10)   -- [1,2,3,4,5,6,7,8,9,10]
```

| Appel               | Résultat            |
|---------------------|---------------------|
| `takeFirstN 0`      | `[]`                |
| `takeFirstN 5`      | `[1,2,3,4,5]`       |
| `takeFirstN 10`     | `[1,2,3,4,5,6,7,8,9,10]` |

---

## 💬 Mon ressenti

C’est une des premières fois où j’ai senti que Haskell _pensait différemment_. En créant une liste infinie, je m’attendais à un crash ou un blocage... mais non : tant qu’on extrait un nombre fini d’éléments, tout reste rapide et précis. C’est à la fois déroutant et génial — une vraie porte vers la **programmation fonctionnelle élégante**.

---

## 📂 Fichiers associés

- `HC1T5.hs` → Code Haskell et tests
- `HC1T5.md` → Explication détaillée

---
