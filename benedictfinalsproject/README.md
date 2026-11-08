# Benedict — Personal Portfolio

A responsive, dependency-free portfolio for a BSIT student at La Consolacion University Philippines. Built with semantic HTML, CSS, and vanilla JavaScript. No installation or build step is needed.

## Structure

```text
index.html
css/
  style.css
js/
  script.js
assets/
  images/
    favicon.svg
    profile-placeholder.svg
  resume.pdf                 # optional: supply your own real PDF
README.md
```

## Preview

Open the folder in VS Code. Install the Live Server extension if needed, right-click `index.html`, and choose **Open with Live Server**. You can also open `index.html` directly; resume detection needs an HTTP server. There is no npm setup.

## Personalize before publishing

- Edit `portfolio` at the top of `js/script.js`: replace the clearly marked sample email and add your GitHub and LinkedIn profile URLs. Blank social URLs display unavailable icons instead of fake links.
- Edit the `projects` array in the same file to update descriptions, technology tags, repository URLs, and demo URLs. Blank project links show a coming-soon state. The portfolio demo points to the actual local site.
- Add your resume at `assets/resume.pdf`. The page checks for a successful response and a real PDF signature before showing the download. Until then, it displays **Resume coming soon**. A missing PDF can appear as an expected 404 in browser developer tools; it does not cause an uncaught JavaScript error. Direct file previews keep the coming-soon state.
- Replace the illustrated profile placeholder with your photo, update the image source and alt text in `index.html`, and remove the small placeholder caption. Keep filenames and paths case-sensitive.
- Update the introduction and SEO description in `index.html`. Colors, content width, and common design tokens are at the top of `css/style.css`.

## GitHub

Install Git if needed (it was not available in the creation environment), then create an empty GitHub repository. In the VS Code terminal, from this folder, run:

```sh
git init
git add index.html css js assets README.md
git commit -m "Build Benedict personal portfolio"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
git push -u origin main
```

If a repository already exists, use its existing branch and remote instead of reinitializing or adding another origin. For later updates:

```sh
git add index.html css js assets README.md
git commit -m "Update portfolio"
git push
```

## Vercel deployment

1. Push this folder to GitHub with `index.html` at the repository root.
2. In Vercel, add a new project and import the repository.
3. Choose **Framework Preset: Other** and use the repository root as the Root Directory.
4. Leave the Build Command and Install Command empty (override auto-detection if shown). Leave Output Directory at the default, or use `.` if prompted. Do not set it to `public` or `dist`.
5. Deploy. Vercel serves the root HTML and its relative `./css`, `./js`, and `./assets` paths directly. Future pushes to the production branch update the deployment.

No framework, `package.json`, environment variables, or Vercel configuration file is required.

## GitHub Pages

In repository Settings → Pages, deploy from the `main` branch and `/ (root)`. The relative asset paths also work when hosted under a repository subpath.

## Accessibility and behavior

Includes keyboard navigation, a skip link, visible focus states, an accessible mobile menu with Escape support, active section navigation, reduced-motion support, progressive scroll reveals, copy-email feedback, and a back-to-top link. Content remains visible when IntersectionObserver is unavailable or reduced motion is requested. Project details include a no-JavaScript fallback. All artwork is local SVG or CSS; no external fonts, image services, trackers, or libraries are used.
