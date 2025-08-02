## 📘 Fichier : `HC1T7.md`

````md
# 🌡️ HC1T7 — Tâche 7 : Conversion Fahrenheit → Celsius

---

## 🎯 Objectif

Écrire une fonction `fToC` qui prend une température en degrés Fahrenheit et la convertit en Celsius. C’est une transformation mathématique simple, mais elle illustre bien la pureté fonctionnelle de Haskell.

---

## 🧪 Formule utilisée

La formule officielle de conversion est :

$$ C = \frac{5}{9} \times (F - 32) $$

---

## 🔧 Définition de la fonction

```haskell
fToC :: Float -> Float
fToC f = (f - 32) * 5 / 9
```

- **Typage** : J’ai utilisé `Float` car les températures peuvent être décimales.
- **Soustraction** : On retire 32 à la température Fahrenheit.
- **Multiplication et division** : Le résultat est multiplié par 5 puis divisé par 9.

---

## 🎉 Exemples utiles

| Fahrenheit (F) | Celsius (C)        |
|----------------|--------------------|
| `32`           | `0.0`              |
| `212`          | `100.0`            |
| `98.6`         | `37.0`             |
| `-40`          | `-40.0`            |

Ces cas montrent à la fois des points de référence (zéro, ébullition, température corporelle) et des cas particuliers comme `-40`, identique dans les deux unités.

---

## 📚 Ce que j’ai compris

| Concept         | Détail                                                  |
|-----------------|----------------------------------------------------------|
| Pureté          | Une transformation exacte, sans effets de bord           |
| Typage précis   | Le choix de `Float` est essentiel ici                    |
| Arithmétique    | Chaque étape de calcul est lisible et exprimée clairement|
| Vérification    | On peut comparer les résultats à des références connues  |

---

## 💬 Mon ressenti

Cette tâche était rapide mais instructive. Elle m’a permis de manipuler des **valeurs flottantes** et de consolider ma compréhension de la **notation infixée** en Haskell. Le typage simple mais explicite m’a rappelé combien il est utile de penser à la nature des données qu’on manipule — surtout quand elles viennent du monde réel.

---

## 📂 Fichiers associés

- `HC1T7.hs` → Code avec tests
- `HC1T7.md` → Documentation commentée

---
