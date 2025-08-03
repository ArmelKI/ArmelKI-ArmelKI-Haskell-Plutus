## 📘 Fichier : `HC1T5.md`

# 🌀 HC1T5 - Tâche 5 : Paresse en Haskell

---

## 📝 Présentation

Dans cette tâche, je définis une fonction `infiniteNumbers` qui génère une **liste infinie de nombres entiers**. Grâce à l’évaluation paresseuse de Haskell, je peux ensuite utiliser la fonction `takeFirstN` pour **extraire les n premiers éléments** sans provoquer d’erreur, ni charger toute la liste en mémoire.

L’idée principale : montrer que Haskell ne calcule que ce qui est demandé, même si la structure sous-jacente est _potentiellement infinie_.

La consigne exacte que j’ai donnée était :  
> Créer une fonction `infiniteNumbers` qui génère une liste infinie de nombres.  
> Extraire seulement les n premiers éléments.

---

## 🔧 Code complet avec `main`

```haskell
-- HC1T5.hs

-- Génère une liste infinie de nombres à partir de 1
infiniteNumbers :: [Int]
infiniteNumbers = [1..]

-- Extrait les n premiers éléments
takeFirstN :: Int -> [Int]
takeFirstN n = take n infiniteNumbers

main :: IO ()
main = do
  print (takeFirstN 5)    -- [1,2,3,4,5]
  print (takeFirstN 10)   -- [1,2,3,4,5,6,7,8,9,10]
  print (takeFirstN 0)    -- []
```

---

## 🗂️ Décryptage détaillé

### 🔸 `infiniteNumbers :: [Int]`

- Utilise `[1..]` pour créer une **liste infinie**, démarrant à 1.
- Haskell accepte ce genre de définition grâce à sa **paresse** : la liste est calculée au fur et à mesure.

### 🔸 `takeFirstN :: Int -> [Int]`

- La fonction `take` coupe une liste après `n` éléments.
- Même si la source est infinie, `take` ne demande que ce qu’il faut — et ça marche ✨

### 🔸 `main`

- Trois cas simples pour tester :
  - Extraire 5 éléments
  - Extraire 10 éléments
  - Demander 0 élément (cas limite)

---

## ✅ Cas de test

| `n` demandé | Résultat attendu          |
|-------------|---------------------------|
| `5`         | `[1,2,3,4,5]`             |
| `10`        | `[1,2,3,4,5,6,7,8,9,10]`  |
| `0`         | `[]`                     |

> Je pourrais aussi tester des valeurs bien plus grandes (`takeFirstN 100000`) — Haskell gérerait ça sans broncher 🧘

---

## 📚 Ce que j’ai compris

| Concept                   | Ce que j’en retiens                                                                 |
|---------------------------|--------------------------------------------------------------------------------------|
| Évaluation paresseuse     | Le programme calcule **seulement ce qui est demandé**, pas toute la liste infinie   |
| Génération infinie        | La notation `[1..]` permet de définir une suite sans fin                            |
| `take` + paresse          | Ensemble, ils permettent de **consommer une portion** d’une source illimitée        |
| Simplicité + puissance    | Un code minimal qui traduit une idée fondamentale du langage                       |

---

## 🗒️ Mon avis personnel

Cette tâche m’a ouvert les yeux sur la manière dont Haskell traite l’infini comme un outil — pas comme une limitation. En tant qu’étudiant, c’est motivant de voir que :

- Je peux penser en termes de flux, pas forcément de structures finies.
- Je peux raisonner sur une infinité tout en gardant le contrôle sur ce que j’extrais.
- Ça donne envie d’explorer les générateurs, les suites, les filtres…

> Et surtout, ça me donne une première preuve concrète que Haskell “ne fait rien tant que je ne lui demande pas” — et ça, c’est un super pouvoir 🦥✨

---

## 📂 Fichiers associés

- `HC1T5.hs` → Code Haskell complet avec `main`
- `HC1T5.md` → Cette fiche de documentation fidèle à ma consigne

---
