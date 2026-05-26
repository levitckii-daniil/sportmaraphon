# Sport Marafon Fest Schedule

Static website with the Sport Marafon Fest schedule, useful festival links, and a map link.

## Local Preview

Open `index.html` in a browser, or run a small local server:

```bash
python3 -m http.server 8080
```

Then open `http://localhost:8080`.

## Easy Deployment

### Netlify, fastest manual option

1. Go to `https://app.netlify.com/drop`.
2. Drag this folder into the page.
3. Netlify will publish the site and give you a URL.

### GitHub Pages, best simple source-controlled option

1. Create a GitHub repository.
2. Upload these files to the repository root:
   - `index.html`
   - `styles.css`
3. Open repository Settings -> Pages.
4. Set Source to `Deploy from a branch`.
5. Select branch `main` and folder `/root`.
6. The site will be available at `https://<username>.github.io/<repo-name>/`.

### Vercel or Cloudflare Pages

Import the repository and keep default static-site settings. No build command is needed.
