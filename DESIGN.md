# Credimi Design and Branding

## Canonical assets

The following human-supplied files are canonical and must not be modified,
regenerated, optimized, or converted:

| Canonical asset | SHA-256 |
| --- | --- |
| `HITL/style.css` | `ff452337f866cae1060057a8c417752b5a9767f59b748c9c7cde509c638387c7` |
| `HITL/credimi_logo.svg` | `031885760a9165e9d8d49eab45baca30ba5ed8dd1fbf0b4699fba2de5dc4feac` |
| `HITL/credimi_logo_negative.svg` | `32df33f9f5ffa696d452e1f65f5d6738b920415c5114db4b010af1f997a8cb3a` |
| `HITL/credimi_logo-transp.svg` | `8407a3ed0beddc137599f71498f1ca8e68766a2684dba80093ea25e17173eef7` |
| `HITL/credimi_logo-transp_white.svg` | `196017744fca7d3836720995aca8c55c8531908e8dcdafc5ca5e7b48ef8f7e10` |

`credimi_logo.svg` and `credimi_logo_negative.svg` are the icon-only mark, dark
and negative. `credimi_logo-transp.svg` and `credimi_logo-transp_white.svg` are
the full wordmark, icon plus the word "CREDIMI", in dark text for light
backgrounds and white text for dark backgrounds. The four are not
interchangeable.

Each derived web application must install unchanged runtime copies of all five
assets. It must load its application CSS after `style.css`, use
`credimi_logo.svg` on light backgrounds and
`credimi_logo_negative.svg` on dark backgrounds, and use
`credimi_logo.svg` directly as the favicon.

Apply this branding to every HTML page, including API documentation. Add tests
that prove each runtime copy is byte-for-byte equal to its canonical HITL
original. Do not generate PNG or ICO logo variants.

The chosen stack determines the runtime asset locations. Record those locations
in the derived project's `SPECS.md`; this template intentionally does not
prescribe paths.

## Credimi Extras cross-promotional banner

Every derived application must carry the Credimi Extras banner on every HTML
page, as two strips of the same sentence.

The copy is fixed and identical in every application:

> This app is part of **Credimi Extras**. Automate all your EUDI testing with
> **Credimi**

The top strip sits immediately above the topbar, as the first element inside
the page body. It uses the `--brand-secondary` background and `--brand-primary`
text of the application's own palette, centred content, and an inline 16px
`credimi_logo.svg` before the sentence. The trailing word "Credimi" is the link.

The bottom strip closes the existing footer, after any content already there,
on a translucent dark fill over the footer's own brand background rather than a
new colour. Its text is white at reduced opacity, and in place of the trailing
word it inlines the `credimi_logo-transp_white.svg` wordmark at about 16px
tall, with `alt="Credimi"`.

Both strips link to `https://credimi.io` in a new tab, with `rel="noopener"`.
Neither strip is sticky, dismissible, or animated, and neither is clickable as
a whole: only the trailing word or wordmark is an anchor, never the bar. The
sentence must read on one line at desktop width and wrap rather than truncate
at phone width, and the link must be keyboard reachable with a visible focus
state.

Take colours from the application's existing custom properties rather than
hardcoded values, and add the banner's rules to the application stylesheet that
loads after `style.css`, never to `style.css` itself.

The sibling Credimi Extras repositories `credimi-capture-wallet`,
`eudi-conformance-atlas`, `eudi-trusted-list-publisher` and
`eudi-trust-inspector` carry reference implementations of both strips across
four different stacks.

## Chips and badges

When a view shows a category badge next to a member of that category, only the
category gets a filled pill. The member's own label stays plain text, coloured
to match its category, with no background, border, or padding of its own. A
second nested pill compounds visual noise once several members share one
category, and it competes with the badge that actually carries the grouping.

Keep such colour mappings declarative in the stylesheet, one modifier class per
category, so the pill and the plain label cannot drift apart.
