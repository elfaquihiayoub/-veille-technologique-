---
marp: true
title: Alpine.js — Présentation
description: Une présentation simple d’Alpine.js pour le développement web
theme: default
paginate: true
html: true
size: 16:9
style: |
  section {
    background: #0b1220;
    color: #5a76a6;
    font-family: "Aptos", "Segoe UI", sans-serif;
    padding: 52px 64px;
    font-size: 25px;
  }
  h1, h2, h3 { color: #7ee7a8; }
  h1 { font-size: 2.05em; letter-spacing: -0.03em; }
  h2 { font-size: 1.45em; margin-bottom: .5em; }
  h3 { font-size: 1em; }
  strong { color: #7ee7a8; }
  a { color: #7ee7a8; }
  code { background: #18263b; color: #13a549; border-radius: 5px; padding: .08em .25em; }
  pre { background: #eeeff0; border: 1px solid #346ec1; border-radius: 12px; padding: 17px 20px; font-size: .72em; }
  pre code { background: transparent; padding: 0; }
  table { width: 100%; border-collapse: collapse; font-size: .76em; }
  th { color: #7ee7a8; background: #142238; }
  th, td { border: 1px solid #2b3d55; padding: 10px 12px; }
  blockquote { border-left: 5px solid #7ee7a8; color: #cbd8e9; background: #101c2e; padding: 8px 18px; }
  ul, ol { margin-top: .35em; }
  li { margin: .28em 0; }
  section::after { color: #8192aa; font-size: 13px; }
  section.lead { background: radial-gradient(ellipse at 78% 22%, #163b37 0%, #0b1220 48%); justify-content: center; }
  section.lead h1 { font-size: 2.65em; margin-bottom: .12em; }
  section.lead h2 { color: #c5d6e9; font-size: 1.15em; font-weight: 400; }
  section.lead p { color: #b9c8dd; }
  section.lead .eyebrow { color: #7ee7a8; text-transform: uppercase; letter-spacing: .18em; font-size: .62em; }
  .eyebrow { color: #7ee7a8; text-transform: uppercase; letter-spacing: .13em; font-size: .65em; font-weight: 700; }
  .small { font-size: .68em; color: #b9c8dd; }
  .callout { color: #c9f7da; background: #132b2a; border: 1px solid #2c6352; border-radius: 12px; padding: 12px 16px; }
  .muted { color: #b9c8dd; }
  .tag { color: #7ee7a8; border: 1px solid #356d58; border-radius: 18px; padding: 5px 12px; font-size: .66em; }
  section.lead .logos { display: flex; align-items: center; gap: 24px; margin-top: 12px; height: 70px; }
  section.lead .logos img:first-child { width: 64px; height: 64px; object-fit: contain; }
  section.lead .logos img:last-child { width: 190px; height: 70px; object-fit: cover; object-position: center 25%; transform: translateY(-20px); }
---

<!-- _class: lead -->

<div class="eyebrow">Présentation technique · Développement web</div>

# Alpine.js

## Des pages web interactives avec HTML

**Présenté par :** Ayoub El Faquihi<br>
**Encadrant :** ES-Saraj Fouad

**Solicode Tanger — OFPPT**

<div class="logos">
  <img src="ofppt.png" alt="Logo OFPPT">
  <img src="solicode.png" alt="Logo Solicode">
</div>

<!--
Bonjour, je m’appelle Ayoub. Aujourd’hui, je vais vous présenter Alpine.js.
-->

---

## Plan de la présentation

1. Introduction et contexte
2. Le problème
3. Qu’est-ce qu’Alpine.js ?
4. Comment ça marche ?
5. Exemple de code
6. Installation
7. Avantages et limites
8. Exemples d’utilisation
9. Conclusion

<!--
Voici les étapes de ma présentation.
-->

---

## 1 · Introduction et contexte

- Un site web montre des informations.
- L’utilisateur clique sur des boutons et ouvre des menus.
- HTML crée le contenu de la page.
- CSS change l’apparence de la page.
- JavaScript ajoute des actions.
- Alpine.js aide à ajouter des actions simples dans HTML.

<!--
Sur un site web, nous utilisons des boutons, des menus et des formulaires.
-->

---

## 2 · Le problème

### Une page a du contenu et des actions

| HTML / CSS | JavaScript |
|---|---|
| Le contenu de la page | Les actions de l’utilisateur |
| Boutons, formulaires, menus | Ouvrir un menu, montrer un message |
| L’apparence de la page | Changer la page |

- Problème : beaucoup de code pour une petite action
- Solution : une action simple avec Alpine.js

<!--
Pour ajouter une petite action, JavaScript demande parfois beaucoup de code.
-->

---

## 3 · Qu’est-ce qu’Alpine.js ?

<div class="eyebrow">Définition</div>

- Petit outil JavaScript
- Code ouvert à tous
- Attributs spéciaux : *directives*

| Idée | Explication |
|---|---|
| Directives HTML | Elles ajoutent des actions |
| Données qui changent | La page change quand les données changent |
| Ajout progressif | On peut ajouter Alpine.js à une page existante |

- Alpine.js utilise JavaScript
- Actions simples dans une page web

<!--
Alpine.js est un petit outil JavaScript pour ajouter des actions à une page web.
-->

---

## 4 · Comment ça marche ?

### Quatre directives utiles

| Directive | Action | Exemple |
|---|---|---|
| `x-data` | Crée des données | `x-data="{ open: false }"` |
| `x-show` | Montre ou cache un élément | `x-show="open"` |
| `x-on:click` / `@click` | Répond à un clic | `@click="open = !open"` |
| `x-model` | Lie un champ à une donnée | `x-model="name"` |

- `x-data` garde les données
- Les directives changent la page
- `@click` est une forme courte de `x-on:click`

<!--
Les directives relient les données aux actions de la page.
-->

---

## 5 · Exemple de code

<!--
Je vais montrer cet exemple dans ma page de pratique.
-->

---

## 6 · Installation

### Deux façons de commencer

#### 1 · CDN

```html
<script defer
  src="https://cdn.jsdelivr.net/npm/alpinejs@3.17.4/dist/cdn.min.js">
</script>
```

- Ajouter cette ligne dans `<head>`.
- Une connexion Internet est nécessaire.

#### 2 · npm

```bash
npm install alpinejs
```

```js
import Alpine from 'alpinejs'
window.Alpine = Alpine
Alpine.start()
```

<!--
Il y a deux façons d’installer Alpine.js : avec un CDN ou avec npm.
-->

---

## 7 · Avantages et limites

| Avantages | Limites |
|---|---|
| Petit et léger | Beaucoup d’actions rendent le HTML difficile à lire |
| Facile pour des actions simples | Moins d’aide pour un grand projet |
| Moins de code JavaScript séparé | Les composants complexes sont difficiles à organiser |
| Fonctionne avec une page existante | Il faut connaître JavaScript |

- Alpine.js : actions simples
- Grande application : outil plus complet

<!--
Alpine.js est simple pour les petites actions, mais il est moins adapté aux grands projets.
-->

---

## 8 · Exemples d’utilisation

### Des actions dans un site web

| Élément | Exemple |
|---|---|
| Menus | Montrer des liens |
| Fenêtres | Montrer un formulaire |
| Onglets | Montrer une partie de la page |
| Formulaires | Montrer un mot de passe |
| Tableaux de bord | Ouvrir un menu |

- Bibliothèque :
  - Alpine.js : fenêtre pour ajouter un livre
  - PHP : demandes
  - MySQL : livres et membres

<!--
Dans une bibliothèque, Alpine.js peut ouvrir une fenêtre pour ajouter un livre.
-->

---

## 9 · Conclusion

### À retenir

1. **Quoi ?** Un petit outil JavaScript.
2. **Comment ?** Avec des directives dans HTML.
3. **Pourquoi ?** Pour ajouter des actions avec peu de code.
4. **Quand ?** Pour ajouter des actions à une page web.

- Alpine.js : actions simples dans HTML
- Choisir l’outil selon le projet

<!--
Alpine.js aide à ajouter des actions simples dans une page HTML.
-->
