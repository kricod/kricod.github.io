# kricod.github.io

The landing page for the [kricod](https://github.com/kricod) organization,
live at **<https://kricod.github.io>**.

A single self-contained `index.html` — no build step, no dependencies, no
external requests. GitHub Pages serves it from the root of `main`, so pushing
here deploys it.

## Adding a project

Projects are cards in the grid inside `index.html`. Copy the existing
`card--live` block and edit the name, description, and URL:

```html
<a class="card card--live" href="https://github.com/kricod/REPO">
  <h3 class="card__name">REPO</h3>
  <p class="card__desc">One line on what it does.</p>
  <span class="card__go">View on GitHub&nbsp;→</span>
</a>
```

Keep the `card--open` "Reserved" card last, or drop it once the grid fills out.

## Local preview

Open `index.html` in a browser, or:

```sh
python3 -m http.server 8000
```
