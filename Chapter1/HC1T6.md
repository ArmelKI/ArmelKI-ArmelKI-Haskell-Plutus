## 📘 Fichier : `HC1T6.md`

````md
# ➕ HC1T6 — Signature de type et addition d'entiers

---

## 🎯 Objectif

Définir une fonction `addNumbers` qui prend deux entiers en entrée, et retourne leur somme. L’accent est mis sur l’importance de **la signature de type** claire et explicite.

---

## 🧠 Démarche

```haskell
addNumbers :: Int -> Int -> Int
addNumbers x y = x + y
```

La signature dit tout : `Int -> Int -> Int` signifie que la fonction attend **deux** `Int` successifs et renvoie un `Int`. C’est une des syntaxes les plus lisibles et pédagogiques en Haskell.

---

## ✅ Tests intégrés

```haskell
main :: IO ()
main = do
  print (addNumbers 2 3)    -- 5
  print (addNumbers 10 5)   -- 15
  print (addNumbers (-3) 7) -- 4
  print (addNumbers 0 0)    -- 0
```

| Appel                   | Résultat |
|-------------------------|----------|
| `addNumbers 2 3`        | `5`      |
| `addNumbers 10 5`       | `15`     |
| `addNumbers (-3) 7`     | `4`      |
| `addNumbers 0 0`        | `0`      |

---

## 📚 Ce que j’ai retenu

| Concept              | Description |
|----------------------|-------------|
| Signature `::`       | Elle explicite les types attendus et retournés |
| Currying             | Les fonctions en Haskell prennent leurs arguments un par un |
| Clarté typée         | On comprend la logique juste en lisant le type |
| Pureté fonctionnelle | `addNumbers` est une fonction pure — même entrée, même sortie |

---

## 💬 Mon ressenti

Ce genre de fonction est simple à écrire, mais c’est justement ce qui la rend pédagogique : elle montre comment on explicite les types, et elle peut servir dans beaucoup de contextes plus complexes par la suite (addition vectorielle, somme d’éléments, etc.). Le typage m’a semblé naturel ici, mais je vois déjà comment il peut guider la conception de fonctions plus grandes.

---

## 📂 Fichiers associés

- `HC1T6.hs` → Code avec tests
- `HC1T6.md` → Documentation commentée

---
