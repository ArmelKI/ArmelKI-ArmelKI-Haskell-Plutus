## 📘 Fichier : `HC1T2.md`

# 🔗 HC1T2 — Tâche 2 : Exemple de fonction pure `circleArea`

---

## 📝 Présentation

Dans cette tâche, j’écris une fonction **pure** en Haskell appelée `circleArea`, qui calcule l’aire d’un cercle à partir de son rayon. Elle ne dépend d’aucun état externe, n’a aucun effet de bord, et renvoie toujours le même résultat pour une même entrée. C’est exactement ce qu’on attend d’une fonction pure.

L’exercice me permet aussi de travailler le **typage générique** avec la classe de type `Floating`, qui regroupe des types capables de représenter des nombres à virgule (`Float`, `Double`, etc.).

---

## 🔧 Code complet avec `main`

```haskell
-- HC1T2.hs

-- Calcule l’aire d’un cercle de rayon r
circleArea :: Floating a => a -> a
circleArea r = pi * r * r

main :: IO ()
main = do
  print (circleArea 1.0)     -- 3.141592653589793
  print (circleArea 2.5)     -- 19.634954084936208
  print (circleArea 0.0)     -- 0.0
```

---

## 🗂️ Décryptage détaillé

### 🔸 `circleArea :: Floating a => a -> a`

- Cette signature signifie que la fonction accepte **n’importe quel type flottant** (`Float`, `Double`, etc.).
- L’usage de la contrainte `Floating a` me permet d’avoir une fonction **générique mais contrôlée** : je ne peux pas passer un `Int`, mais je peux passer un `Float`, ce qui est logique pour une formule mathématique.
- La fonction est **pure** : elle ne lit ni écrit aucune donnée externe, ne change rien à l’état du programme, ne produit que son calcul.

### 🔸 `circleArea r = pi * r * r`

- J’utilise la constante `pi` fournie par Haskell, qui fait partie de la classe `Floating`.
- L’expression correspond exactement à la formule classique de l’aire d’un cercle : π × r²
- Elle est **déclarative** : pas de variable intermédiaire, pas d’imperatif — juste une équation.

### 🔸 `main`

- J’ai intégré plusieurs appels dans `main` pour tester avec des rayons différents.
- Tous les appels produisent une sortie directe, reproductible, sans interaction.

---

## ✅ Cas de test

| Rayon (`r`) | Résultat attendu (`π × r²`)     |
|-------------|----------------------------------|
| `1.0`       | `3.141592653589793`              |
| `2.5`       | `19.634954084936208`             |
| `0.0`       | `0.0`                            |

---

## 📚 Ce que j’ai compris

| Concept            | Ce que j’ai retenu                                                          |
|--------------------|-----------------------------------------------------------------------------|
| Fonction pure       | Dépend uniquement de l’entrée, aucune influence externe, résultat constant |
| Typage générique    | `Floating a => a -> a` permet de manipuler plusieurs types compatibles     |
| Expression mathématique | Le code ressemble à une équation, ce qui rend la logique très naturelle |
| Testabilité         | Facile à tester, à prévoir, et à intégrer dans d’autres fonctions          |

---

## 🗒️ Mon avis personnel

C’est un très bon exercice pour **comprendre la pureté** en Haskell. Rien ne change dans l’environnement, tout repose sur une transformation exacte et transparente. Je vois aussi que Haskell me pousse à **choisir un type adapté**, ce qui renforce la rigueur : pas possible ici d’utiliser un entier sans convertir.

Ce genre de fonction peut être la base pour une bibliothèque de calculs scientifiques, ou pour construire des modules pédagogiques. Elle me donne envie de creuser plus loin la classe `Floating` et d’essayer des généralisations vers des calculs avec des cercles, des sphères, etc.

---

## 📂 Fichiers associés

- `HC1T2.hs` → Code source avec `main`
- `HC1T2.md` → Documentation structurée et commentée

---

---
