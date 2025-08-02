## 📘 Fichier : `HC1T3.md`

````md
# 🔗 HC1T3 — Vérifier si un nombre est supérieur à 18

---

## 📝 Présentation

Cet exercice est très simple en apparence, mais il pose les bases d'une logique claire et typée. J’ai écrit une fonction `greaterThan18` qui teste si un entier donné est strictement supérieur à 18. Elle renvoie un booléen (`True` ou `False`) — donc parfaite pour un usage dans des conditions ou des filtres.

---

## 🎯 Ce que j’ai voulu explorer

- Comment définir une fonction logique en Haskell
- Ce que `Bool` représente et comment l’utiliser
- L’intérêt de typer même les fonctions les plus simples

---

## 🔧 Code que j’ai écrit

```haskell
greaterThan18 :: Int -> Bool
greaterThan18 x = x > 18
```

Une seule ligne de définition, avec un typage clair : la fonction prend un `Int`, et renvoie un `Bool`.

---

## ✅ Tests dans `main`

J’ai intégré quelques cas dans `main` pour observer les sorties :

```haskell
main :: IO ()
main = do
  print (greaterThan18 10)   -- False
  print (greaterThan18 18)   -- False
  print (greaterThan18 19)   -- True
  print (greaterThan18 100)  -- True
```

| Entrée | Résultat |
|--------|----------|
| 10     | False    |
| 18     | False    |
| 19     | True     |
| 100    | True     |

---

## 📚 Ce que j’ai retenu

| Concept        | Ce que j’ai compris                                              |
|----------------|------------------------------------------------------------------|
| Comparaison    | Une opération simple mais essentielle pour toute logique         |
| Booléens       | `True` ou `False` permettent des décisions et des branches       |
| Typage clair   | Même une fonction basique a intérêt à être bien typée            |
| Précision      | `x > 18` est strict — `18` n’est pas accepté                     |

---

## 🗒️ Mon avis personnel

Ce genre d’exercice me paraît trivial à première vue, mais c’est en l’écrivant que j’ai réalisé pourquoi c’est important. Je peux maintenant imaginer `greaterThan18` dans un `filter`, ou dans une logique de validation utilisateur. Et en l’écrivant moi-même, je la comprends vraiment.

---

## 📂 Fichiers associés

- `HC1T3.hs` → Code Haskell avec `main`
- `HC1T3.md` → Documentation (ce fichier)

---
