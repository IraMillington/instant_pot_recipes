# Instant Pot Recipes: Agent Guide

A static recipe site with no build step and no dependencies. `CLAUDE.md` imports
this file, so Claude Code and Codex read the same rules.

- `index.html` is the interactive page (Chicken Tikka Masala and Quesabirria).
  Its inline JavaScript scales ingredients and pressure-cook times by weight and
  builds a shopping list.
- `birria.html` is a plain Quesabirria page with JSON-LD `Recipe` markup, so
  recipe apps can import it from a URL. Keep `recipeInstructions` a flat array
  of strings, because some parsers reject `HowToStep` objects.
- `style.css` holds shared styles (responsive, mobile first).

## Verify

Open the pages in a browser, or serve them with `python -m http.server`, and
check both the desktop and phone widths. If you change the scaling logic,
check a few weights by hand: the cook times and amounts are what people follow.
For `birria.html`, keep the JSON-LD valid (paste it into a JSON parser).

## Deploy

GitHub Pages serves the `main` branch root at
https://iramillington.github.io/instant_pot_recipes/. Pushing to `main` is the
deploy, and it is live within a minute or two. There is no home-server part.
This repository is **public**: never commit personal data or keys.
