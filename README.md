# BLCKSMTH — Menu

A minimal, animated digital menu for BLCKSMTH coffee. Single HTML file, no build step, no dependencies beyond Google Fonts.

## Features

- **Entrance animations** — the brand name slides up on load with a slow red glow pulse; menu sections fade and expand in as you scroll
- **Scroll-triggered reveals** — each section label draws a line across the page as it enters view; items stagger in with a subtle slide-up
- **Price count-up** — prices animate from zero when a menu item scrolls into view
- **Drink animation overlay** — tap any menu item to see a black cup fill with the right ingredients (coffee drops, milk drops, tumbling ice cubes) specific to that drink, then a liquid fill that matches the drink's colour profile. Tap anywhere or press Escape to dismiss

## Stack

Pure HTML/CSS/JS — one file, zero frameworks, zero build tools.

| Thing | Choice |
|---|---|
| Fonts | Bebas Neue (display), Barlow Condensed (body) via Google Fonts |
| Animations | CSS keyframes + IntersectionObserver |
| Drink overlay | Vanilla JS DOM + CSS transitions |

## Menu

| Section | Items |
|---|---|
| Espresso | Double Espresso, Americano, Cortado, Cappuccino, Flat White, Latte |
| Iced | Iced Double Espresso, Iced Americano, Iced Latte |
| Cold | Cold Brew, Cold Coffee |
| Add-ons | Almond Milk +₹90, Oat Milk +₹90 |

## Running locally

No server needed — just open `index.html` in a browser.

```bash
open index.html
```

## Updating the menu

All items live in `index.html`. To add a drink:

1. Add a `.item` row inside the relevant `.menu-section`
2. Add a matching entry to `DRINK_CONFIG` in the script block, specifying the ingredient drops and liquid colour

```html
<div class="item">
  <span class="item-name">New Drink</span>
  <span class="item-price" data-price="320">320</span>
</div>
```

```js
'New Drink': { drops:[['coffee',2],['milk',2]], liquidColor:'#5a2e14' },
```

Ingredient types: `coffee` (dark brown teardrop), `milk` (cream teardrop), `ice` (tumbling blue-white cube).
