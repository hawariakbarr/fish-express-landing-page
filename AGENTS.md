# Repository Guidelines

## Project Structure & Module Organization

This is a static landing page with no build system. The main page lives in `index.html`, which contains the HTML, CSS, and vanilla JavaScript for layout, theme switching, language support, and interactions. Deployment configuration is in `netlify.toml`; GitHub Pages deployment is defined in `.github/workflows/deploy-pages.yml`. The `images/` directory is reserved for local visual assets. Agent and tool metadata lives under `.agents/` and should not be changed unless updating contributor tooling.

## Build, Test, and Development Commands

- `xdg-open index.html` opens the site directly in a browser on Linux.
- `python3 -m http.server 8000` serves the repository at `http://localhost:8000/` for a closer production-like preview.
- `git diff --check` catches trailing whitespace and whitespace errors before committing.

There is no `npm install`, bundler, or generated asset step. GitHub Pages publishes the repository root on pushes to `master`; Netlify also publishes `.` with no build command.

## Coding Style & Naming Conventions

Keep changes small and localized inside `index.html`. Use 2-space indentation for HTML, CSS, and JavaScript blocks to match the existing file. Prefer semantic HTML, CSS custom properties, and vanilla JavaScript. Keep CSS class names descriptive and kebab-cased, for example `hero-card`, `delivery-info`, and `footer-grid`. Store translated text in the existing `i18n` object and keep Indonesian (`id`) and English (`en`) keys in sync.

## Testing Guidelines

No automated test suite is currently configured. Test changes manually in a browser before opening a pull request. Check desktop and mobile widths, especially around the existing breakpoints: `1024px`, `968px`, `560px`, and `400px`. Verify theme switching, language switching, navigation links, WhatsApp/Instagram links, and reduced-motion behavior when animation-related CSS or JavaScript changes.

## Commit & Pull Request Guidelines

Recent history uses concise, conventional-style prefixes such as `docs:`, `chore:`, and `ci:`. Follow that pattern, for example `docs: update contributor guide` or `chore: optimize landing page assets`.

Pull requests should include a short summary, the reason for the change, and manual test notes. Include screenshots or screen recordings for visual changes, with both mobile and desktop coverage when layout is affected. Link related issues when available, and call out any deployment configuration changes explicitly.

## Security & Configuration Tips

Do not commit secrets, API keys, or private customer data. Keep external contact links and deployment targets consistent across `index.html`, `README.md`, and `netlify.toml`.
