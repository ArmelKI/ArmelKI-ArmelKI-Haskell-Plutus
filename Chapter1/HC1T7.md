## 📘 Fichier : `HC1T7.md`

# 🌡️ HC1T7 - Tâche 7 : Conversion Fahrenheit → Celsius

---

## 📝 Présentation

Dans cette tâche, je définis une fonction `fToC` qui prend une température en **degrés Fahrenheit** et la convertit en **degrés Celsius**. Ce genre de fonction est simple mais emblématique : elle me permet de manipuler des calculs de base, de typer explicitement les entrées et sorties, et surtout de **coder une transformation réelle** que j’ai rencontrée dans la vie quotidienne.

La consigne exacte que j’ai donnée était :  
> Écrire une fonction `fToC` qui convertit des degrés Fahrenheit en Celsius.

---

## 🔧 Code complet avec `main`

```haskell
-- HC1T7.hs

-- Conversion Fahrenheit vers Celsius
fToC :: Float -> Float
fToC f = (f - 32) * 5 / 9

main :: IO ()
main = do
  print (fToC 32)     -- 0.0
  print (fToC 212)    -- 100.0
  print (fToC 98.6)   -- 37.0
```

---

## 🗂️ Décryptage détaillé

### 🔸 `fToC :: Float -> Float`

- La signature indique que la fonction prend un `Float` (Fahrenheit) et retourne un `Float` (Celsius).
- J’utilise `Float` pour gérer les **valeurs décimales**, ce qui est indispensable ici (ex: 98.6°F = 37.0°C).

### 🔸 La formule mathématique

```txt
°C = (°F - 32) × 5 / 9
```

- C’est une conversion standard.
- Elle me montre comment **coder une transformation mathématique précise**, sans artifice.

### 🔸 `main`

- Trois cas bien choisis :
  - 32°F → le point de congélation de l’eau → résultat : `0.0`
  - 212°F → le point d’ébullition → résultat : `100.0`
  - 98.6°F → température corporelle typique → résultat : `37.0`

---

## ✅ Cas de test

| Fahrenheit | Celsius attendu |
|------------|-----------------|
| `32`       | `0.0`           |
| `212`      | `100.0`         |
| `98.6`     | `37.0`          |
| `0`        | `-17.78`        |
| `100`      | `37.78`         |

> À noter : j’utilise des `Float`, donc les résultats sont arrondis naturellement par Haskell.

---

## 📚 Ce que j’ai compris

| Concept                 | Ce que j’en retiens                                                       |
|-------------------------|----------------------------------------------------------------------------|
| Signature explicite     | Permet de clarifier les types attendus, surtout en présence de décimales  |
| Opérations arithmétiques | Les transformations mathématiques s’écrivent de manière intuitive en Haskell |
| Cas concrets            | Le lien entre le code et la réalité rend la tâche motivante               |

---

## 🗒️ Mon avis personnel

Ce genre de tâche m’aide à consolider mes bases. Même si l’idée est simple, je suis attentif à :

- La clarté du typage (`Float`)
- La précision de la formule
- La cohérence dans les tests

Et j’en profite pour imaginer une suite :
- Ajouter une fonction `cToF`
- Présenter un menu utilisateur (saisie interactive)
- Créer une fiche de conversion automatique 📈

---

## 📂 Fichiers associés

- `HC1T7.hs` → Code Haskell complet avec `main`
- `HC1T7.md` → Cette fiche claire et fidèle à ma consigne

---
