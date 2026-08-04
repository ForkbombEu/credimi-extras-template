# AGENTS.md

Read the content of: 

./directives
./HITL

Read `./STANDARDS.md` before changing protocol, standards, conformance, credential, trust, or interoperability behaviour.
Read `./SPECS.md` before changing implementation, architecture, dependencies, build tooling, or development workflow.

## Execution

- Do NOT infer conventions
- Do NOT adopt undocumented patterns
- Use ONLY rules defined in `./directives`

If something looks like a convention but is not defined:

→ append it to `./directives/HITL.md`  
→ do NOT use it

## Lint

Each derived project SHOULD lint its stylesheets for CSS custom properties that
are referenced through `var(--x)` but never defined anywhere in the cascade —
stylelint's undefined-custom-properties rule, or the closest equivalent for the
chosen stack. An undefined custom property drops the declaration silently
instead of failing, so nothing surfaces the bug except looking at the page.
