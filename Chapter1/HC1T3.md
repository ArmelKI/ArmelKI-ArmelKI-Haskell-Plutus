## 📘 Fichier : `HC1T3.md`

# 🔗 HC1T3 — Tâche 3 : Vérifier si un nombre est supérieur à 18

---

## 📝 Présentation

Dans cette tâche, je dois écrire une fonction Haskell nommée `greaterThan18`, qui **prend un entier et indique s’il est strictement supérieur à 18**. C’est un cas simple de logique booléenne, mais c’est aussi l’occasion de s’approprier la syntaxe minimaliste de Haskell et de réfléchir à la clarté des signatures.

La consigne que j’ai donnée est :
> Écrire une fonction `greaterThan18` qui vérifie si un nombre donné est supérieur à 18.

---

## 🔧 Code complet avec `main`

```haskell
-- HC1T3.hs

-- Vérifie si le nombre est strictement supérieur à 18
greaterThan18 :: Int -> Bool
greaterThan18 n = n > 18

main :: IO ()
main = do
  print (greaterThan18 10)  -- False
  print (greaterThan18 18)  -- False
  print (greaterThan18 19)  -- True
```

---

## 🗂️ Décryptage détaillé

### 🔸 `greaterThan18 :: Int -> Bool`

- La fonction prend un seul **entier** (`Int`) et renvoie un **booléen** (`True` ou `False`).
- La signature est très directe, et c’est une bonne pratique de l’écrire même si Haskell peut l’inférer — ça **clarifie le contrat attendu**.

### 🔸 `greaterThan18 n = n > 18`

- L’expression `n > 18` utilise un opérateur de comparaison standard.
- Elle est **pure** : pas d’effets de bord, pas de contexte externe, juste une évaluation logique sur l’entrée.

### 🔸 `main`

- J’ai ajouté des appels de test dans la fonction `main`, pour observer le comportement avec plusieurs cas :
  - Un nombre en dessous
  - Le seuil lui-même
  - Un nombre au-dessus

---

## ✅ Cas de test

| Entrée `n` | Sortie attendue | Commentaire                          |
|------------|------------------|--------------------------------------|
| `10`       | `False`          | En dessous du seuil                  |
| `18`       | `False`          | Égale au seuil, test important       |
| `19`       | `True`           | Strictement supérieur, doit valider  |

---

## 📚 Ce que j’ai compris

| Concept             | Ce que j’ai retenu                                                             |
|---------------------|--------------------------------------------------------------------------------|
| Fonction simple      | En Haskell, une logique booléenne s’exprime en une seule ligne claire         |
| Signature explicite  | Même pour une fonction triviale, préciser le type améliore la lisibilité      |
| Testabilité          | Tester différents cas limite est crucial (égalité, dépassement, sous-seuil)   |

---

## 🗒️ Mon avis personnel

Ce genre d’exercice me paraît fondamental : il **crée les bons réflexes**. Même si la logique est triviale, on s’entraîne à :
- Écrire des signatures claires
- Penser en mode test dès le départ
- Respecter le style Haskell (déclaratif, épuré)

Je commence à mieux voir ce que Haskell attend de moi : **des fonctions isolées, lisibles, et naturellement testables**. Et chaque petite tâche, bien faite, devient un bloc solide dans mon portfolio.

---

## 📂 Fichiers associés

- `HC1T3.hs` → Code source avec `main` et tests intégrés
- `HC1T3.md` → Cette documentation rédigée à la première personne

---
