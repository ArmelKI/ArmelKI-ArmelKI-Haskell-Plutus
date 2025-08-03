## 📘 Fichier : `HC1T6.md`

# ➕ HC1T6 - Tâche 6 : Utilisation de signatures de type

---

## 📝 Présentation

Dans cette tâche, je définis une fonction `addNumbers` qui prend deux entiers en entrée et retourne leur **somme**. L’objectif est de m’initier à l’écriture de **signatures de type explicites** en Haskell — une pratique essentielle pour rendre le code lisible, rigoureux et compréhensible dès le premier coup d’œil.

La consigne exacte que j’ai donnée était :  
> Définir une fonction `addNumbers` qui prend deux entiers et retourne leur somme.

---

## 🔧 Code complet avec `main`

```haskell
-- HC1T6.hs

-- Signature de type : deux Int → un Int
addNumbers :: Int -> Int -> Int
addNumbers x y = x + y

main :: IO ()
main = do
  print (addNumbers 3 4)   -- 7
  print (addNumbers 10 5)  -- 15
  print (addNumbers (-2) 8) -- 6
```

---

## 🗂️ Décryptage détaillé

### 🔸 `addNumbers :: Int -> Int -> Int`

- La signature `Int -> Int -> Int` signifie :
  - Prend un premier `Int`
  - Prend un deuxième `Int`
  - Retourne un `Int` (leur somme)

- C’est aussi une bonne occasion de comprendre **l’associativité à droite** des flèches :
  - `Int -> Int -> Int` est équivalent à `Int -> (Int -> Int)`
  - Autrement dit, `addNumbers` peut être vue comme une fonction **qui retourne une fonction**

### 🔸 `addNumbers x y = x + y`

- Le corps de la fonction est simple : une addition classique.

### 🔸 `main`

- Je vérifie que la fonction se comporte comme prévu avec des exemples concrets.

---

## ✅ Cas de test

| Entrée          | Résultat attendu |
|-----------------|------------------|
| `addNumbers 3 4`  | `7`              |
| `addNumbers 10 5` | `15`             |
| `addNumbers (-2) 8` | `6`           |

---

## 📚 Ce que j’ai compris

| Concept                    | Ce que j’en retiens                                              |
|----------------------------|------------------------------------------------------------------|
| Signature de type          | Permet de **documenter le contrat** attendu entre entrées et sortie |
| Clarté fonctionnelle       | Une signature claire rend le code auto-explicite                |
| Currying en Haskell        | Toute fonction à plusieurs arguments est en fait une suite de fonctions |
| `Int -> Int -> Int`        | Me prépare à mieux comprendre les fonctions d’ordre supérieur   |

---

## 🗒️ Mon avis personnel

Même si cette tâche est courte, elle pose une brique fondamentale de mon style Haskell :  
Je veux que chaque fonction soit **aussi lisible que testable**, avec une signature explicite qui me permet de comprendre **ce qu’elle fait sans lire son corps**.

C’est une étape vers :
- Des fonctions plus abstraites
- Des compositions plus claires
- Une documentation naturelle par le typage

---

## 📂 Fichiers associés

- `HC1T6.hs` → Code Haskell avec signature explicite
- `HC1T6.md` → Cette fiche claire, précise, et fidèle à ma progression

---
