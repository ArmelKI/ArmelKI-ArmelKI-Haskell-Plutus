````md
# 🔗 HC1T2 — Fonction pure : Calculer l’aire d’un cercle

---

## 📝 Présentation

Cette fois, j’ai voulu écrire une fonction simple mais 100 % **pure**, c’est-à-dire sans dépendance à une variable externe, ni effets de bord. L’idée : calculer l’aire d’un cercle en fonction de son rayon.

Haskell m’offre directement `pi`, donc la formule devient naturelle : `pi * r * r`.

---

## 🎯 Ce que j’ai cherché à comprendre

- Ce que signifie “fonction pure” en pratique
- Comment bien typer la fonction pour qu’elle accepte des flottants (`Float`, `Double`)
- Comment tester proprement le comportement avec des cas concrets

---

## 🔧 Code que j’ai écrit

```haskell
circleArea :: Floating a => a -> a
circleArea r = pi * r * r
```

La fonction est minimale — une seule ligne — mais typée pour rester générique (`Floating a`) et rester fidèle au style Haskell.

---

## ✅ Quelques tests avec `main`

Dans mon fichier `.hs`, j’ai ajouté cette fonction pour afficher les résultats :

```haskell
main :: IO ()
main = do
  print (circleArea 1)     -- Aire pour rayon = 1
  print (circleArea 2.5)   -- Rayon décimal
  print (circleArea 0)     -- Rayon nul
```

Et voici ce que j’obtiens en sortie :

| Rayon | Résultat           |
|--------|--------------------|
| 1      | 3.141592653589793  |
| 2.5    | 19.634954084936208 |
| 0      | 0.0                |

---

## 📚 Ce que j’ai retenu

| Concept          | Ce que j’en comprends clairement                                         |
|------------------|---------------------------------------------------------------------------|
| Fonction pure    | Aucun effet de bord, dépend uniquement de l’entrée → testable et fiable  |
| Typage générique | `Floating a` autorise plusieurs types de données (Double, Float, etc.)   |
| Concision        | Une ligne suffit pour exprimer une logique claire et mathématique        |
| Expression directe | Pas besoin d’artifice : la formule se lit comme une vraie équation      |

---

## 🗒️ Mon avis personnel

J’aime beaucoup ce type d’exercice : il me permet de me concentrer sur la **clarté** et la **précision**. Ce que j’apprécie dans Haskell ici, c’est que le code ressemble presque à une formule mathématique — aucune distraction, juste l’essentiel.

C’est aussi là que je vois l’intérêt de documenter chaque étape. Même une petite fonction comme `circleArea` peut refléter un vrai choix de style et de conception. Et en la testant via `main`, je rends mon dépôt plus vivant et reproductible.

---

## 📂 Fichiers associés

- `HC1T2.hs` → Code Haskell avec `main`
- `HC1T2.md` → Ce fichier de documentation

---
