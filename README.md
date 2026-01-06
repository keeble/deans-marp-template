# deans-marp-template

a template repo for marp presentations which dean thinks looks nice. Based off the new Diamond corporate branding.

Written using [marp](https://marp.app/)

## Publishing (GitHub Pages on release) [beta, _kinda_ works]

This template includes a GitHub Actions workflow that renders the presentation to HTML and publishes it to GitHub Pages whenever a repository *release* is published.

How it works:

- On `release` the action installs `@marp-team/marp-cli`, renders `src/slides.md` to `public/index.html`, copies the `assets/` folder into `public/`, and deploys the `public` directory to GitHub Pages branch `gh-pages`, which you can then enable through the repo's settings. 

Why it only _kinda_ works: 

- the sizing isn't correct. You can confirm this by rendering locally and it looks the same so this looks to be one of those fun undocumented differences between the vscode marp and the cli

```
npx @marp-team/marp-cli@latest -o public/index.html --html --allow-local-files --theme-set ./assets/diamond.css -- slides.md
```