# Gifted Touch Therapeutic Massage

Website for **Gifted Touch Therapeutic Massage**. Etete Agbabune, LMT.
Huntsville, Alabama. Board Certified NCTMB 403638-00 · Alabama LMT 1745. Est. 2006.

Live at **[giftedtouch.org](https://giftedtouch.org)**

> Anointed hands. A gifted touch.

## Stack

A single, self-contained static page. No build step, no dependencies, no framework.

```
index.html     the entire site
img/           studio photography and body care product shots
vercel.json    headers and caching
```

Open `index.html` in a browser to work on it locally.

## Brand

Light and warm. Etete reviewed a first dark build and asked for a brighter
palette, so the site now ships **four bright themes** she can compare live.

| Theme | key | Ground | Accent | Text |
|---|---|---|---|---|
| Vesper Bronze *(default)* | `vesper` | `#F9F5EE` | `#8F5A2A` | `#0E3C3B` teal |
| Anointed Dawn | `dawn` | `#FCF7F0` | `#9C5524` | `#3B2242` plum |
| Morning Balm | `balm` | `#F8F5EF` | `#8A5A2B` | `#1E2420` |
| Lavender Linen | `heather` | `#F8F5EF` | `#856022` | `#2F2036` |

Vesper Bronze is the default because teal, bronze and purple are the three
colours Etete named herself in her brand discovery.

Every colour on the page is a CSS custom property on `:root`, overridden per
theme by `[data-theme="key"]` on `<html>`. There are no hardcoded colours in
the stylesheet, so a theme swap is total. All four pass WCAG AA on every text
pairing that occurs on the page.

Mark: a roundel lotus, three petals in a hairline ring. It is drawn with
`currentColor` so it inherits the active accent, and it doubles as a foil
stamp for product lids.

Type: **Cormorant Garamond** for display, **Jost** for information.

House rules: no em dashes, no emojis.

### Choosing a theme

A palette picker sits at the lower left so Etete can preview all four on the
real site. Her choice is remembered in `localStorage`. **Once she picks, remove
it**: delete the `#palette` element, its CSS block, and the picker JS block in
`index.html`, then set the winning tokens on `:root`. All three are marked
`REVIEW TOOL`.

## Booking

Her ClinicSense scheduler is embedded directly in the page as a section
(`#book`), so clients book without leaving the site. On-page CTAs scroll to it;
a fallback link opens it in a new tab if the frame fails.

`https://giftedtouchtherapeuticmassage.clinicsense.com/book/`

The widget renders its own blue header, which is a ClinicSense brand setting
inside Etete's account, not something this site controls.

## Content sources

Copy, rates, testimonials, and FAQs were carried over from the previous site
(anointedgtm.com) and the 2026 Brand Discovery. Testimonials are client words,
kept verbatim. Rates come from Etete's own price list.

Per Etete's August 2026 call: mobile massage is no longer advertised up front
(it is offered on request), corporate and chair massage takes its place, warm
stone replaced hot stone, sports massage is not advertised, and travel past
20 miles may carry an additional fee.

## Deploy

Hosted on Vercel, project `gifted-touch` under The Coast's projects.

Pushes to `main` deploy to production automatically. Pull requests and
other branches get their own preview URLs.

To ship from the CLI instead:

```bash
vercel deploy --prod
```

## DNS

`giftedtouch.org` is registered at Namecheap. Advanced DNS should hold:

| Type | Host | Value | TTL |
|---|---|---|---|
| A | `@` | `216.198.79.1` | Automatic |
| CNAME | `www` | `cname.vercel-dns.com.` | Automatic |

Remove Namecheap's default parking records first (the `@` and `www`
URL Redirect / CNAME rows pointing at `parkingpage.namecheap.com`).
Vercel issues the TLS certificate automatically once DNS resolves.

---

The Coast Global Inc.
