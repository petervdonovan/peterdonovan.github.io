# Peter Donovan’s website

Use Node.js 24 and npm. Run `npm ci` to install dependencies and
`npm run dev` to start the local server. Run `npm run build` to generate
`dist/` and `npm run preview` to serve that build locally.

Edit the introduction in `src/App.vue` and the citations in
`src/publications.js`.

## GitHub Pages

In the GitHub repository, open **Settings → Pages** and select **GitHub
Actions** as the source under **Build and deployment**. Each push to
`main` builds and publishes the site. You can also run **Deploy to GitHub
Pages** manually from the Actions tab on `main`.
