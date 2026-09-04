# Credimi Extras mini-app Template

**Credimi** is the trustworthy compliance checker for decentralized identity
solutions, built and operated by Forkbomb BV (Amsterdam) under the NGI
TRUSTCHAIN programme. A Credimi Extra is a mini-app in that family.

This GitHub template starts a new Credimi Extras mini-app with its governance,
standards-neutral documentation, and authoritative Credimi design assets.

It deliberately contains no application implementation. A derived project may
use exactly one backend stack: Go or Node.js with TypeScript. Stack selection
happens in the derived project, based on its actual requirements; this template
does not select, scaffold, or implement either stack.

Complete [SPECS.md](SPECS.md) before implementation. It records the selected
backend, architecture, dependencies, commands, and runtime asset locations.
Populate [STANDARDS.md](STANDARDS.md) only with standards, versions, and
profiles confirmed to apply to the derived project.

The authoritative design assets are in [brand/](brand/) — one place, no second
token file to reconcile against:

```
brand/style.css                        the brand stylesheet — load this first
brand/fonts/InterVariable.ttf          brand sans      (SIL OFL 1.1)
brand/fonts/SourceCodeProVariable.ttf  brand monospace (SIL OFL 1.1)
brand/logos/credimi_logo.svg           mark, dark — also the favicon
brand/logos/credimi_logo_negative.svg  mark, negative
brand/logos/credimi_logo-transp.svg    wordmark, dark
brand/logos/credimi_logo-transp_white.svg  wordmark, white
```

The four logos are frozen and SHA-256 pinned in [DESIGN.md](DESIGN.md) §1.
`brand/style.css` is maintained, not frozen — it is where the brand lives.

[HITL/](HITL/) now holds only human briefs.

Follow [docs/CREATE_PROJECT.md](docs/CREATE_PROJECT.md) when creating a
project from this template. Design and branding rules are in
[DESIGN.md](DESIGN.md); governance instructions are in [AGENTS.md](AGENTS.md)
and [directives/](directives/).

The canonical brand specification is the Credimi Design System project at
<https://claude.ai/design/p/019e1703-03a5-73c9-9db0-028f11767c3f>.
[DESIGN.md](DESIGN.md) is that specification adapted to this template, and
`brand/style.css` merges the design system's tokens with the former
`HITL/style.css` — see [DESIGN.md](DESIGN.md) §16 for what that merge changed.
