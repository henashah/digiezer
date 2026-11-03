# DigiEzer website plan

## Product direction
DigiEzer is a managed outsourcing and pragmatic automation partner for organizations that want useful capacity, not more complexity. The site must connect two commercial services—human resource outsourcing and problem-led automation—to a credible employment pathway for underprivileged youth in India.

## Design direction

- **Design movement:** contemporary editorial business design with warm modernism: confident typography, tactile paper-like surfaces, and precise interface details instead of a generic SaaS gradient.
- **Core principles:** (1) clear before clever, (2) human outcomes over tool hype, (3) evidence in the details, (4) business value and social value in the same frame.
- **Color philosophy:** a deep ink base signals seriousness and trust; warm bone surfaces keep the page human and legible; a signature coral-orange acts like a highlighter for momentum and action; a muted teal-green marks the impact engine and responsible progress.
- **Layout paradigm:** an editorial scroll with oversized headline blocks, offset cards, ruled dividers, and a recurring vertical “path” motif that visually connects client problems to employment outcomes. Avoid symmetric card grids wherever the story can unfold as a sequence.
- **Signature elements:** a hand-drawn-style path line built with CSS borders and dots; pill-shaped “signal” labels; offset ink/coral blocks that feel like a working document rather than a polished-but-empty template.
- **Interaction philosophy:** interactions should clarify choice and reduce hesitation. Buttons have visible hover lift and arrow movement; the services switcher exposes a quick fit summary; the mobile menu is simple and reversible; FAQ answers expand without taking the user to another page.
- **Animation:** subtle reveal-up transitions on scroll; path dots pulse once when entering the impact section; no looping decorative motion that competes with reading.
- **Typography system:** use a high-contrast serif display stack (`Iowan Old Style`, `Palatino Linotype`, `Book Antiqua`, `Georgia`) for major headlines and an accessible sans stack (`Inter`, `Avenir Next`, `Segoe UI`, `Helvetica Neue`) for UI and body. Headlines use tight leading and selective italic emphasis; body text stays calm at 1.65 line-height.
- **Brand essence:** “Practical capacity for ambitious organizations—and a better first job for someone in India.” Personality: grounded, generous, exacting.
- **Brand voice:** direct, warm, specific. Example lines: “Start with the bottleneck.” and “Your growth can open someone else’s next chapter.” Avoid vague claims such as “unlock the future.”
- **Wordmark & logo:** a compact `D` + `E` ligature made from two offset rounded rectangles, suggesting a doorway and a digital cursor; pair it with a slightly condensed wordmark so `DigiEzer` feels ownable without relying on a default font.
- **Signature brand color:** `#F36B4F` (DigiEzer coral), used sparingly for action, emphasis, and the “move” moments in the story.

## Implementation approach

- Build a lightweight static site with no external runtime dependencies: semantic HTML, one CSS file, and one small ES module for mobile navigation, service switching, FAQ disclosure, and intersection reveals.
- Serve the site from a minimal Node HTTP server on port 3000 so Preview can load the complete experience. The same repository can produce a static `dist/` directory for a future static checkpoint build.
- Use a single responsive route (`/`) plus a static `manus-routes.json` manifest. Anchor navigation provides clear service, impact, and contact pathways without introducing unnecessary page complexity.
- Keep copy in the HTML so the initial document is crawler-visible and the value proposition is readable without JavaScript.
- Use CSS-generated visuals instead of stock photography: a “capacity map” in the hero, service signal diagrams, and the impact pathway. This keeps the brand original, fast, and focused on the business/mission relationship.

## Project structure

- `public/index.html` — complete semantic marketing page and content.
- `public/styles.css` — responsive visual system, layout, motion, focus states, and reduced-motion handling.
- `public/main.js` — progressive enhancement for navigation, service switcher, FAQ, and reveal effects.
- `public/manus-routes.json` — declared page route manifest for the platform.
- `public/favicon.svg` / `public/logo.svg` — small brand marks for browser/platform identity.
- `server.mjs` — dependency-free local/Preview server with static file handling and SPA-safe fallback.
- `package.json` — start/build scripts.
- `app.config.ts` — quoted platform logo URL literal once the durable uploaded logo URL is available.
- `TODO.md` — outcome-level acceptance clauses copied from the request.
