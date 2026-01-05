# deans-marp-template

a template repo for marp presentations which dean thinks looks nice

Written using [marp](https://marp.app/)

## Some useful code snippets
### put an image to the right and have text on the left
```
![bg right width:634]
```

### centre an image
```
<style>
img[alt~="center"] {
  display: block;
  margin: 0 auto;
}
</style>
```

### Change the font weight of the paragraph
p = paragraph
```
<style scoped>
p {
   font-weight: 200;
}
</style>
```
````
## Publishing (GitHub Pages on release)

This template includes a GitHub Actions workflow that renders the presentation to HTML and publishes it to GitHub Pages whenever a repository *release* is published.

How it works:

- On `release` (type `published`) the action installs `@marp-team/marp-cli`, renders `src/slides.md` to `public/index.html`, copies the `assets/` folder into `public/`, and deploys the `public` directory to GitHub Pages.

Local preview and testing:

1. Install the Marp CLI:

```bash
npm install -g @marp-team/marp-cli
```

2. Render locally:

```bash
npx @marp-team/marp-cli@latest src/slides.md -o public/index.html --html --allow-local-files --theme ./assets/diamond.css
cp -R assets public/
```

3. Open `public/index.html` in a browser to preview the exported site.

Notes:

- The workflow runs only on GitHub Releases; create a new Release (Draft → Publish release) to trigger it.
- The action uploads the `public` directory as the Pages artifact and the Pages deploy action will create/replace the Pages deployment for the repository.

Files added:

- `.github/workflows/render-release.yml` — the release-triggered workflow that builds and publishes the site.

````
