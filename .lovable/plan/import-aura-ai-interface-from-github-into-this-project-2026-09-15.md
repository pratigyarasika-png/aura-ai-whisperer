# Import "Aura AI Interface" from GitHub into this project

## What this does

Restores the existing Aura AI Interface app (AI academic research platform) from
`github.com/pratigyarasika-png/aura-ai-interface` into this Lovable project, so
you can continue working on it here. Both projects use the same underlying
stack, so this is a faithful copy of the code — the preview will look and behave
like the original.

The app includes:
- **Home** — circular AI hub, collapsible sidebar (history, saved projects,
  recent sessions), top status bar with live activity badges, theme/background
  color picker.
- **Search** — academic paper search with filters and results.
- **Write** — AI writing assistant (flash / pro / expert / deep / journal
  modes) with PDF/Word export, LaTeX support.
- Library of saved papers stored in the browser (no database needed).

## Steps

1. **Copy the code**
   - Replace `src/` and `public/` with the repository's versions (pages,
     components, styles, search + AI logic).
   - Copy supporting config files (vite config, tsconfig, eslint, prettier,
     components.json) from the repository.

2. **Install dependencies**
   - Use the repository's dependency list and lockfile, then run an install so
     the AI SDK, PDF/Word export libraries, charts, forms, and other extras
     used by the app are available.

3. **Remove unused backend wiring**
   - The app stores all data in the browser and never reads from a database,
     but it ships with generated database client files that would fail without
     credentials. Remove that unused wiring (it is only referenced from the
     startup file) so the app boots cleanly. Cross-site request protection and
     error handling in the startup file are kept.

4. **Verify the AI assistant**
   - The Write page's AI features call the Lovable AI Gateway. Check the
     project's secrets; if the AI gateway key is not present, enable Lovable
     AI (Lovable Cloud) so the assistant works end to end.

5. **Verify everything works**
   - Confirm the build succeeds with no errors.
   - Open the app and check the Home, Search, and Write pages render and the
     AI assistant responds.

## Notes

- No data migration is needed: the original app has no database tables; saved
  papers live in the user's browser storage.
- Page titles, descriptions, and social preview tags are preserved from the
  original code.
