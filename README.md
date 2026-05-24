# Red from Pallet

A tiny single-page tribute to the iconic Pokémon Red starter-choice scene. Pick Bulbasaur, Charmander, or Squirtle, see their Gen 1 Pokédex entry, base stats, height, weight, and type — then share your choice with a friend.

## Live site

Once published via GitHub Pages it will be available at:
`https://<your-username>.github.io/<repo-name>/`

## Running locally

It's a single self-contained HTML file. Either:

- Open `index.html` directly in a browser **via a local web server** (the abacus counter API fetch is blocked from `file://` origins in modern browsers), or
- Use `python -m http.server` from this folder and visit `http://localhost:8000`.

## How the global counter works

When a visitor clicks "Choose [Pokemon]", a `GET` request is sent to
[abacus.jasoncameron.dev](https://abacus.jasoncameron.dev) — a free public hit-counter API — to increment a counter keyed by the chosen starter. All visitors see the same percentages because they're served from the same shared keys.

The namespace is set near the top of the inline `<script>`:

```js
var COUNTER_NS = "pokeredfrompallet-ghpages";
```

Change this string to reset the counters to zero (e.g. bump to `-v2`).

## Per-user state

Each browser stores its own choice in `localStorage` under `chosenStarter` so visitors can only pick once. To let yourself pick again during testing, clear it from DevTools → Application → Local Storage.

## Credits

- Sprites: Pokémon Yellow (Bulbagarden) — animated using a small 2-frame bob
- Hero screenshot: Pokémon Red, Game Boy
- Font: VT323 (Google Fonts)
- UI: Bootstrap 3
