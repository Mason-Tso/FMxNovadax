# FMxNovadax — Landing Page

Partnership landing page for **Freeport Markets x NovaDAX**, built as a single-file static site.

## Project structure

```
index.html                      # Entire site — HTML, CSS, JS in one file
FMlogo.png                      # Original Freeport Markets logo (rectangular badge)
New Freeport Markets logo.png   # Ship icon only (used in nav + footer)
Novologo.png                    # NovaDAX orbital mark (white bg, shown in white circle)
Realtimenewsfeed.png            # App screenshot — news feed section
USstocks.png                    # App screenshot — US stocks section
preipo.png                      # App screenshot — Pre-IPO section
smartanalyst.png                # App screenshot — AI analyst section
```

## Tech stack

- Pure HTML/CSS/JS — no build step, no framework
- **Satoshi** font via Fontshare CDN (`api.fontshare.com`)
- **GSAP 3.12.5** + ScrollTrigger via Cloudflare CDN for scroll animations
- Open directly in browser — `index.html`

## Sections (top to bottom)

1. **Nav** — FM ship icon + "Freeport Markets" | NovaDAX orbital mark + "NovaDAX" | "Resgatar Créditos" CTA
2. **Hero** — two floating phone mockups (USstocks behind, smartanalyst front), headline, CTA buttons
3. **Partnership** — dedicated section with both logos, watermark background text
4. **Credits promo** — NovaDAX referral link offer card
5. **Features x4** — alternating left/right layout, each with a phone mockup screenshot:
   - Real-time news feed (`Realtimenewsfeed.png`)
   - US stocks (`USstocks.png`)
   - Pre-IPO (`preipo.png`)
   - AI analyst (`smartanalyst.png`)
6. **Steps** — 3-step onboarding
7. **CTA** — final call to action
8. **Footer** — both logos, legal, links

## Phone mockup

CSS-only phone frame — no extra image file needed. Structure per mockup:

```html
<div class="phone-shell">       <!-- gradient glow border -->
  <div class="phone-glow"></div>
  <div class="phone-body">      <!-- rounded rect, black bg -->
    <div class="phone-notch">   <!-- notch bar + camera dot -->
    <img class="phone-screen" src="screenshot.png">
    <div class="phone-home-bar">
  </div>
  <div class="pb-power"></div>  <!-- side buttons -->
  <div class="pb-silent"></div>
  <div class="pb-volup"></div>
  <div class="pb-voldn"></div>
</div>
```

## Design tokens

| Token | Value |
|-------|-------|
| Primary green | `#00D45A` |
| NovaDAX teal | `#0BC47A` |
| Background | `#000000` |
| Dark section bg | `#060606` |
| Border | `rgba(255,255,255,0.07)` |
| Body font | Satoshi 400 |
| Heading font | Satoshi 700 |

## Language

All copy is in **Brazilian Portuguese**. No em dashes (`—`) anywhere in text.

## Responsive breakpoints

- `max-width: 900px` — single column layout, back phone hidden, reduced padding
- `max-width: 480px` — smaller fonts, full-width buttons, nav hides brand text labels

## To update

- **Credits amount** — edit the credits promo section in `index.html` (search for "Resgatar Créditos" card)
- **Referral link** — replace `href="#"` on `.btn-credits` with the actual NovaDAX referral URL
- **Phone frame PNG** — if a `phoneframe.png` overlay is added later, wrap each `.phone-body` with a relative container and overlay the PNG at `z-index:2` with `pointer-events:none`
