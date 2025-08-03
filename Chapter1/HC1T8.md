## 📘 Fichier : `HC1T8.md`

# 🔁 HC1T8 - Tâche 8 : Fonctions d’ordre supérieur

---

## 📝 Présentation

Dans cette tâche, je définis une fonction `applyTwice` qui prend une **fonction `f`** et une **valeur `x`**, et renvoie le résultat de l’application de `f` deux fois sur `x` — soit `f (f x)`. C’est mon **premier vrai contact avec une fonction d’ordre supérieur**, c’est-à-dire une fonction qui **prend une fonction en paramètre**.

La consigne exacte que j’ai donnée était :  
> Créer une fonction `applyTwice` qui applique une fonction deux fois à une valeur d’entrée.

---

## 🔧 Code complet avec `main`

```haskell
-- HC1T8.hs

-- Applique une fonction deux fois à une valeur
applyTwice :: (a -> a) -> a -> a
applyTwice f x = f (f x)

main :: IO ()
main = do
  print (applyTwice (+1) 3)        -- 5
  print (applyTwice (*2) 4)        -- 16
  print (applyTwice reverse "abc") -- "abc"
```

---

## 🗂️ Décryptage détaillé

### 🔸 `applyTwice :: (a -> a) -> a -> a`

- Cette signature me dit :
  - La fonction prend un argument `f` qui va de `a` vers `a`
  - Puis une valeur `x` de type `a`
  - Et retourne une nouvelle valeur de type `a`
- Le type `a` est **générique** (paramétrique), ce qui rend la fonction réutilisable pour différents types.

### 🔸 `applyTwice f x = f (f x)`

- Le cœur de la fonction : j’applique `f` à `x`, puis `f` encore une fois au résultat.
- Exemple : `applyTwice (+1) 3` → `(+1) ((+1) 3)` → `(+1) 4` → `5`.

### 🔸 `main`

- Je teste trois cas très différents :
  - Une addition (`+1`)
  - Une multiplication (`*2`)
  - Une fonction sur des chaînes (`reverse`)

---

## ✅ Cas de test

| Fonction appliquée | Valeur | Résultat attendu |
|--------------------|--------|------------------|
| `(+1)`             | `3`    | `5`              |
| `(*2)`             | `4`    | `16`             |
| `reverse`          | `"abc"`| `"abc"`          |

> Dernier cas : `reverse (reverse "abc")` → la chaîne revient à sa version d’origine.

---

## 📚 Ce que j’ai compris

| Concept                     | Ce que j’en retiens                                                        |
|-----------------------------|-----------------------------------------------------------------------------|
| Fonction d’ordre supérieur  | Une fonction qui prend une autre fonction comme paramètre                   |
| Typage paramétrique         | Permet de rendre la fonction **générique** pour tout type `a`              |
| Composition de comportements| Je peux empiler plusieurs transformations sans changer leur nature          |

---

## 🗒️ Mon avis personnel

Cette tâche m’a fait **changer de perspective** : je ne manipule plus seulement des données, mais des **fonctions comme valeurs**, et ça ouvre tout un monde fonctionnel :

- Je peux écrire des fonctions comme outils réutilisables
- Je commence à **abstraire des patterns**, comme “faire une action deux fois”
- Je sens que je m’approche de la **composition fonctionnelle puissante**, où les fonctions deviennent les vraies briques de mon code

Et je vois déjà des extensions :
- Créer `applyN` pour appliquer une fonction `n` fois
- Composer dynamiquement des transformations
- Combiner `applyTwice` avec des map ou des filtres

---

## 📂 Fichiers associés

- `HC1T8.hs` → Code Haskell complet avec `main`
- `HC1T8.md` → Cette fiche vivante qui montre mon cheminement

---
