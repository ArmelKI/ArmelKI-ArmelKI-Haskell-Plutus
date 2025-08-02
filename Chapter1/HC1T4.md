## 📘 Fichier : `HC1T4.md`

````md
# 🧑‍💻 HC1T4 — Tâche 4 : Composition de fonctions pour trier des joueurs

---

## 🧩 Objectif

Créer une fonction `getTopThreePlayers` qui prend une liste de joueurs avec scores, trie par score décroissant, extrait les trois premiers, et renvoie uniquement les noms.

---

## 🧠 Étapes logiques

| Fonction          | Rôle                                                                 |
|-------------------|----------------------------------------------------------------------|
| `extractPlayers`  | Récupérer les noms (`fst`) dans une liste de `(nom, score)`          |
| `sortByScore`     | Trier selon le score (`snd`), en ordre décroissant                   |
| `topThree`        | Extraire les 3 meilleurs joueurs après le tri                        |
| `getTopThreePlayers` | Composition des trois précédentes pour un pipeline clair           |

---

## 🧪 Tests intégrés

```haskell
main :: IO ()
main = do
  let players = [("Alice", 78), ("Bob", 95), ("Charlie", 82), ("Dave", 67), ("Eve", 90)]
  print (extractPlayers players)         -- ["Alice","Bob","Charlie","Dave","Eve"]
  print (sortByScore players)            -- Trié par scores décroissants
  print (topThree players)               -- Top 3 après tri
  print (getTopThreePlayers players)     -- Noms du top 3
```

| Fonction              | Résultat                            |
|-----------------------|-------------------------------------|
| `extractPlayers`      | `["Alice","Bob","Charlie","Dave","Eve"]` |
| `sortByScore`         | `[("Bob",95),("Eve",90),("Charlie",82),...]` |
| `topThree`            | `[("Bob",95),("Eve",90),("Charlie",82)]`    |
| `getTopThreePlayers`  | `["Bob","Eve","Charlie"]`                    |

---

## ✍️ Mon retour d’apprenant

J’ai beaucoup aimé cette tâche car elle m’a permis de jouer avec `map`, `take`, `sortBy`, `comparing`, et surtout de **composer** des fonctions pour construire un pipeline lisible et efficace. Le fait que `getTopThreePlayers` soit purement déclaratif est très satisfaisant à lire. Le typage fait tout le travail, et les étapes sont claires.

---

## 🗂️ Fichiers livrés

- `HC1T4_T4.hs` → Code et tests intégrés
- `HC1T4_T4.md` → Documentation complète

---
