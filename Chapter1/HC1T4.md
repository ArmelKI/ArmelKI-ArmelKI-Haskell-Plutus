## 📘 Fichier : `HC1T4.md`

# 🔗 HC1T4 - Tâche 4 : Composer une fonction pour traiter des données de joueurs

---

## 📝 Présentation

Dans cette tâche, je construis une fonction `getTopThreePlayers` qui prend une liste de joueurs avec leur score, et renvoie les noms des **trois meilleurs joueurs**, triés par score décroissant. Pour cela, je dois d’abord écrire et combiner les fonctions suivantes :

- `extractPlayers` : extrait uniquement les noms des joueurs à partir d'une liste de `(nom, score)`
- `sortByScore` : trie la liste par score décroissant
- `topThree` : garde les trois premiers joueurs
- Puis composer tout ça dans `getTopThreePlayers` grâce à la composition fonctionnelle.

C’est une tâche riche — elle me fait manipuler des listes, des tuples, des fonctions d’ordre supérieur, et surtout me fait voir **comment construire un pipeline fonctionnel clair**.

La consigne exacte que j’ai donnée était :  
> `extractPlayers` : Prend une liste de tuples ((nom, score)) et extrait les noms des joueurs.  
> `sortByScore` : Trie la liste des joueurs par score décroissant.  
> `topThree` : Retourne les trois meilleurs joueurs.  
> Composez ces fonctions dans `getTopThreePlayers`.

---

## 🔧 Code complet avec `main`

```haskell
-- HC1T4.hs

import Data.List (sortBy)
import Data.Ord (comparing)

-- Type synonyme pour clarté
type Player = (String, Int)

-- Extrait les noms des joueurs
extractPlayers :: [Player] -> [String]
extractPlayers xs = map fst xs

-- Trie les joueurs par score décroissant
sortByScore :: [Player] -> [Player]
sortByScore = sortBy (flip (comparing snd))

-- Prend les trois premiers
topThree :: [Player] -> [Player]
topThree = take 3

-- Composition des trois transformations
getTopThreePlayers :: [Player] -> [String]
getTopThreePlayers = extractPlayers . topThree . sortByScore

main :: IO ()
main = do
  let players = [("Alice", 20), ("Bob", 15), ("Charlie", 25), ("Dana", 10)]
  print (getTopThreePlayers players) -- ["Charlie", "Alice", "Bob"]
```

---

## 🗂️ Décryptage détaillé

### 🔸 `extractPlayers :: [Player] -> [String]`

- Cette fonction transforme une liste de `(nom, score)` en une liste de noms, en extrayant le premier élément du tuple avec `map fst`.

### 🔸 `sortByScore :: [Player] -> [Player]`

- Utilise `sortBy` et `comparing` pour trier la liste selon les scores (`snd`).
- Le `flip` est essentiel ici pour obtenir un **ordre décroissant** (du plus grand au plus petit).

### 🔸 `topThree :: [Player] -> [Player]`

- Coupe la liste après 3 éléments, grâce à `take 3`.
- Fonction très simple, mais utile pour rendre le code modulaire.

### 🔸 `getTopThreePlayers`

- C’est la **composition des trois fonctions précédentes**, enchaînées avec l’opérateur `(.)`.
- Elle permet de construire une transformation claire sans variable intermédiaire.

### 🔸 `main`

- J’ai intégré un exemple avec 4 joueurs aux scores variés.
- Le résultat final est une liste de **noms** triés par performance.

---

## ✅ Cas de test

| Liste d’entrée                             | Résultat attendu                |
|--------------------------------------------|----------------------------------|
| `[("Alice", 20), ("Bob", 15), ("Charlie", 25), ("Dana", 10)]` | `["Charlie", "Alice", "Bob"]` |
| `[("Zoe", 5), ("Leo", 30), ("Amy", 30), ("Max", 28)]`         | `["Leo", "Amy", "Max"]`       |

> À noter : en cas d’égalité de scores, `sortBy` garde l’ordre initial — ce que je pourrais améliorer avec un tri secondaire (ex: alphabétique).

---

## 📚 Ce que j’ai compris

| Concept                | Ce que j’en retiens                                                                |
|------------------------|-------------------------------------------------------------------------------------|
| Composition de fonctions | Permet de construire une logique sans variable intermédiaire                      |
| Tri personnalisé         | `sortBy` + `comparing` + `flip` pour gérer l’ordre croissant ou décroissant       |
| Modularité du code       | Chaque fonction est isolée, testable, et compréhensible séparément                |
| Clarté fonctionnelle     | Le pipeline `extractPlayers . topThree . sortByScore` se lit comme une recette    |

---

## 🗒️ Mon avis personnel

C’est le genre de tâche qui me montre **à quel point Haskell pousse à structurer les transformations**. En composant les fonctions étape par étape, je me rends compte que :
- La **lisibilité** est bien meilleure que si j’avais tout écrit en une seule fonction.
- Chacune des fonctions peut être réutilisée dans d’autres contextes.
- La signature explicite de chaque transformation aide à comprendre rapidement ce qu’elle fait.

Et ça m’amène à réfléchir à des évolutions :
- Gérer les égalités de score plus finement
- Présenter le résultat dans un format de tableau ou de classement
- Construire une interface ou une sortie textuelle plus riche (ex: “🥇 Charlie – 25 pts”)

---

## 📂 Fichiers associés

- `HC1T4.hs` → Code Haskell complet avec `main`
- `HC1T4.md` → Cette fiche de documentation, rédigée dans ma voix

---
