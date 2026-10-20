---
marp: true
title: Alpine.js — Technology Watch
description: An introduction to Alpine.js for web development
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
---

<!-- _class: lead -->

<div class="eyebrow">Technology watch · Web development</div>

# Alpine.js

## Lightweight interactivity, written in HTML

A practical introduction to a small JavaScript framework

<br>

<span class="tag">HTML-first</span> &nbsp; <span class="tag">Reactive</span> &nbsp; <span class="tag">Lightweight</span>

---





## 1 · Plan de formation

### qu est ce que un framework
### A web page has st
### A web page has structure — but it also needs interaction


**The opportunity:** use a lightweight tool when a complete frontend framework would be more than the project needs.

---

## 2 · The problem it solves

### A web page has structure — but it also needs interaction

| HTML / CSS | JavaScript |
|---|---|
| Structure and content | Responses to user actions |
| Buttons, forms, menus | Open a menu, show a message, switch tabs |
| Appearance and layout | Update the interface when data changes |

**The challenge:** for small interactions, plain JavaScript can require repetitive code to select elements, listen for events, and update the DOM.

**The opportunity:** use a lightweight tool when a complete frontend framework would be more than the project needs.

---

## 3 · What is Alpine.js?

<div class="eyebrow">Definition</div>

**Alpine.js is a lightweight, open-source JavaScript framework** for adding interactive behavior to HTML pages through special attributes called *directives*.

| Key idea | What it means |
|---|---|
| HTML directives | Describe behavior next to the relevant elements |
| Reactive data | The interface updates when data changes |
| Progressive integration | Enhance an existing page without rebuilding the whole frontend |

<div class="callout">Alpine.js does not replace JavaScript. It provides a convenient syntax for common UI interactions with less separate code.</div>

---

## 4 · How does it work?

### Four directives to know

| Directive | Purpose | Example |
|---|---|---|
| `x-data` | Defines a component's data | `x-data="{ open: false }"` |
| `x-show` | Shows or hides an element | `x-show="open"` |
| `x-on:click` / `@click` | Responds to a click | `@click="open = !open"` |
| `x-model` | Connects an input to data | `x-model="name"` |

**The principle:** data defined with `x-data` is available to its child elements. Directives connect this data to events and what appears on the page.

<div class="small">`@click` is shorthand for `x-on:click`.</div>

---

## 5 · Live code demonstration

### Build a button that shows and hides a message

```html
<div x-data="{ open: false }">
  <button @click="open = !open">
    Toggle message
  </button>

  <p x-show="open">
    Hello, Alpine.js!
  </p>
</div>
```

| Step | Result |
|---|---|
| Initial state: `open = false` | Message is hidden |
| First click: `open = true` | Message appears |
| Second click: `open = false` | Message is hidden again |

<div class="callout"><code>x-data</code> stores the state · <code>@click</code> changes it · <code>x-show</code> responds to it.</div>

---

## 6 · Installation and ecosystem

### Two common ways to get started

**1 — CDN: quick to try**

```html
<script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.17.4/dist/cdn.min.js"></script>
```

- Add the script tag inside the HTML `<head>`.
- Convenient for demos and simple pages.
- Requires network access to load the library from the CDN.

**2 — npm: for a JavaScript project**

```bash
npm install alpinejs
```

```js
import Alpine from 'alpinejs'
window.Alpine = Alpine
Alpine.start()
```

**Ecosystem:** Alpine.js works with existing HTML, server-rendered pages such as PHP templates, and CSS tools like Tailwind CSS. Tailwind styles the interface; Alpine.js adds behavior.

---

## 7 · Alpine.js vs other frameworks

| | Alpine.js | React | Vue.js |
|---|---|---|---|
| Typical fit | Small interactions in an existing page | Rich component-based interfaces | Interfaces from small to large |
| Approach | Directives in HTML | UI built from components | Templates, components, reactivity |
| Enhancing an existing HTML page | Very convenient | Usually needs frontend setup | Can be introduced progressively |
| Large app conventions | More limited | Rich application ecosystem | Rich application ecosystem |

**Examples:** Alpine.js for a dropdown in a PHP page; React for a complex dashboard; Vue.js to progressively enhance a page or build a structured frontend.

<div class="small">These are common use cases, not strict limits. All three tools can support a range of projects.</div>

---

## 8 · Advantages and limitations

| Advantages | Limitations |
|---|---|
| Lightweight approach | Many interactions can make HTML harder to read |
| Easy to learn for common interactions | Fewer built-in conventions for a large application |
| Less separate JavaScript for common UI behavior | Complex relationships between components require careful organization |
| Can enhance existing pages | JavaScript fundamentals are still necessary |

<div class="callout"><strong>Rule of thumb:</strong> choose Alpine.js for focused UI interactions; consider a larger framework when the frontend needs extensive routing, components, and complex application-wide state.</div>

---

## 9 · Real-world use cases

### Interactions found on everyday websites

| Component | Example |
|---|---|
| Dropdown menus | Expand navigation links |
| Modals and popups | Confirm an action or display a form |
| Tabs and accordions | Reveal a section when requested |
| Interactive forms | Show a password or conditional fields |
| Dashboards | Open action menus or toggle filters |

**Example: a library management system**

- **Alpine.js:** open an “Add a book” modal or show book details.
- **PHP:** process requests and apply business rules.
- **MySQL:** store books, members, and loans.

---

## 10 · Conclusion

### Four things to remember

1. **What?** A lightweight JavaScript framework.
2. **How?** HTML directives connect data, events, and the interface.
3. **Why?** Common interactions need less separate JavaScript.
4. **When?** When you want to enhance a page without necessarily adopting a full frontend framework.

<div class="callout">Alpine.js is a simple way to add interactivity to HTML. The right choice still depends on the complexity of the project.</div>

---

## Sources and further reading

- **Official website:** [alpinejs.dev](https://alpinejs.dev/)
- **Getting started:** [alpinejs.dev/start-here](https://alpinejs.dev/start-here)
- **Installation guide:** [alpinejs.dev/essentials/installation](https://www.alpinejs.dev/essentials/installation)
- **`x-data` directive:** [alpinejs.dev/directives/data](https://www.alpinejs.dev/directives/data)
- **Source code and releases:** [github.com/alpinejs/alpine](https://github.com/alpinejs/alpine)
- **React documentation:** [react.dev](https://react.dev/)
- **Vue.js documentation:** [vuejs.org](https://vuejs.org/guide/introduction.html)

<div class="small">Primary source: the official Alpine.js documentation. For production, check the latest release and pin a specific version in the CDN URL.</div>
