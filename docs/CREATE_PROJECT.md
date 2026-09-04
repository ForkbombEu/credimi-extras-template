# Create a Credimi Extra Project

1. Create a repository with GitHub's **Use this template** action.
2. Choose Go or Node.js with TypeScript.
3. Complete `SPECS.md`.
4. Review and populate `STANDARDS.md` with only confirmed applicable standards.
5. Copy `brand/` to a stack-appropriate runtime location, keeping `fonts/` a
   sibling of `style.css` so each `@font-face` `url()` resolves.
6. Add byte-equality tests for the four logo copies against the SHA-256 pins in
   `DESIGN.md` §1.
7. Load `brand/style.css` first on every HTML page, the application's own
   stylesheet after it. Take colours, radii, type and spacing from its tokens;
   never hardcode a value that already has one.
8. Add the Credimi Extras banner markup and styling described in `DESIGN.md`
   §13, using the assets from step 5. It goes in the application stylesheet,
   not in `brand/style.css`.
9. Implement only the CLI, web, and API interfaces the application needs.
10. Add stack-native build, format, lint, test, Docker, and CI configuration,
    including the undefined-custom-property lint `AGENTS.md` requires.

Choose Go when direct Go import, a self-contained binary, or low runtime
overhead materially matters. Choose Node.js with TypeScript when the existing
or consuming system is TypeScript or the Node ecosystem provides a concrete
advantage.

Use one backend stack. Do not silently select or migrate it, and keep an
existing application's current stack unless migration is a separately approved
task.
