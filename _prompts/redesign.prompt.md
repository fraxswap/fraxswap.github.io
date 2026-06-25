# Codex task: LIGHT premium redesign of the Fraxswap landing page (minimal style of Frax Finance)

Rebuild this static one-page site IN PLACE (your -C workdir): overwrite `index.html` + `style.css`, keep
every other file. No frameworks, no build, no external JS/libraries; tiny inline JS only. Premium and
polished -- NOT dry, NOT minimal-as-in-empty, NOT oversized.

IMAGES ARE FROZEN: never create, overwrite, download, replace, rename, or delete any image (`favicon.png`,
`eth.png`, `frax.png`, `og-cover.png`, any `*.png`/`*.svg`/`*.ico`). Use ONLY the images already in the
folder, byte-unchanged. Keep `<link rel="icon">` and the topbar brand `<img>` on the existing `favicon.png`
(no inline `<svg>` mark, no data-URI). Need an icon you do not have? Use a styled text chip.

PRESERVE from the current `index.html` (read it first): the exact keyword `Fraxswap` (as `<h1>` and in
`<title>`), the existing value sentence (deck `<p>` = `<meta description>`, word-for-word, light polish
only), the `<link rel=canonical>`, the money CTA target href, AND the existing topbar authority links
(Etherscan, CoinGecko, DeFi guide) -- keep all three, never drop them.

## THEME: LIGHT premium, in the minimal high-contrast spirit of Frax Finance (frax.finance)
- This is Fraxswap (the Frax AMM). Render it LIGHT but in Frax's REAL minimal aesthetic: a clean
  white / near-white base, sharp CHARCOAL / near-black text, crisp minimal cards with hairline neutral
  borders and a TIGHTER radius (~10-14px -- Frax is sharp and minimal, NOT soft/pastel/very-rounded).
- Frax is largely MONOCHROME: use near-black / charcoal as the primary accent (a BLACK premium primary
  button is the Frax signature). You MAY add ONE very subtle secondary hue if it helps, but keep it
  restrained and high-contrast. theme-color = the light base background.
- Quiet premium motion only (soft pulse on the Preview dot, gentle hover lift). Respect `prefers-reduced-motion`.

## Layout (desktop ONE screen, mobile CLEAN short scroll)
Inside `<main>`: a split hero, then a thin bottom texture band, then the footer.
- **Topbar:** brand mark (`favicon.png`) + `Fraxswap` wordmark LEFT; flexible spacer; the AUTHORITY NAV
  right (Etherscan / CoinGecko / DeFi guide, plain text, `target="_blank" rel="nofollow noopener noreferrer"`)
  -- MUST stay present and in source HTML. No topbar button.
- **Left column (basic):** `<h1>Fraxswap</h1>` (see H1 SIZE) -> the deck `<p>` value sentence (keyword in
  `<strong>`) -> EXACTLY THREE qualitative trust chips (e.g. `TWAMM swaps`, `Non-custodial`,
  `Best execution`) -> ONE prominent primary CTA `Enter App`. NO `<h2>` -- hero copy is only the H1 and its deck `<p>`.
- **H1 SIZE (IMPORTANT):** the hero `<h1>` must RENDER at ~80px on a 1280px desktop -- e.g.
  `font-size: clamp(2.9rem, 5.6vw, 5.1rem)`. NEVER under ~64px on desktop, NEVER a giant 120px+. Scale down on mobile.
- **Right column (the star -- a RICH swap preview, crisp light card):** light chrome + a small selector pill
  + a pulsing `Preview` pill; a From (ETH, `eth.png`) -> To (FRAX, `frax.png`) swap route in two panels with
  a SMALL GAP so the circular switch sits in a clean notch; the switch swaps the two; an abstract
  `Best route` micro-row (faint hop dots, NEVER fabricated numbers); a faint number-free hint; and the
  `Start Swap` CTA. Non-interactive preview, only the switch toggles icons. No wallet connect, no fake amounts.
- ONE tasteful bottom texture band (a light decorative strip or subtle pattern) -- brand-true, number-free, restrained.

## BUTTON STYLE (2026-modern, refined -- NOT chunky)
Both CTAs: moderate size (hero ~50px tall, card ~48px, NOT 60px+), refined radius ~12-13px, font-weight
~600-650 (never heavy 800+), slight negative letter-spacing. For Frax, a CHARCOAL/BLACK fill with a SUBTLE
top inner highlight (`inset 0 1px 0 rgba(255,255,255,.18)`) + a faint 1px ring; a TIGHT low shadow (e.g.
`0 10px 22px -12px rgba(0,0,0,.5)`), NOT a big glow. A small arrow (`&rsaquo;`) that nudges ~3px right on
hover with a gentle 1px lift. Restraint + a crisp micro-interaction.

## SEO spine (LOCKED)
- `<title>` = `Fraxswap &mdash; <short hook>` (em-dash entity, keyword first, <=60 chars, no weak suffix).
- Exactly one `<h1>` = `Fraxswap`. NO `<h2>` anywhere.
- Deck `<p>` wraps `<strong>Fraxswap</strong>` and equals `<meta description>` word-for-word.
- Schema `@graph` = WebSite + WebApplication + Organization, truthful, no FAQ/HowTo. SEO text in source HTML.

## Claims (light, crypto-friendly)
- Confident premium copy welcome. Two floors: (1) invent NO specific numbers (stats, TVL, fees, dates,
  audits, partnerships) -- qualitative only; (2) no "guaranteed / risk-free / 100%", no fake wallet-connect.
- One small footer line: `Information on this page is for educational purposes only and is not financial advice.`

## CTAs + footer
- Exactly TWO, distinct, both -> the preserved target href, `rel="noopener noreferrer"`: hero `Enter App` +
  card `Start Swap`. No third CTA, no topbar button.
- Footer: a `Fraxswap &mdash; 2026` brand line + the one educational line. Small and quiet.

## Technical / mobile
- SEO content in SOURCE HTML; tiny INLINE `<script>` for the switch only; every `<img>` has width+height.
- Desktop ONE screen: `body{min-height:100vh;min-height:100dvh}` + desktop media
  `{height:100vh;height:100dvh;overflow:hidden}` (vh BEFORE dvh); add a `max-height` desktop query to compress.
- MOBILE CLEAN: single column; swap card full-width; route stacks neatly (switch rotates vertical);
  comfortable spacing + tap targets; topbar collapses tidily (nav may hide but stays in source); short
  vertical scroll; ABSOLUTELY no horizontal overflow (`overflow-x:hidden` on html/body + on the band).
- Keep `lang="en"`; keep favicon/og/manifest/robots/sitemap referenced. Glyphs via HTML entities
  (`&mdash;`, `&rsaquo;`, `&darr;`), not literal non-ASCII.

## Self-QC
- [ ] LIGHT premium, Frax minimal spirit (white base, charcoal text, BLACK premium buttons, crisp cards); NOT dry.
- [ ] Authority links (Etherscan / CoinGecko / DeFi guide) present in topbar + source HTML.
- [ ] One `<h1>` = `Fraxswap`; NO `<h2>`; deck `<p>` == meta description; H1 RENDERS ~80px (not under 64).
- [ ] Modern refined buttons (~50/48px, weight ~640, radius ~12px, tight shadow, arrow nudge on hover).
- [ ] Split hero; desktop one screen no-scroll; MOBILE clean, no horizontal overflow.
- [ ] Rich number-free ETH->FRAX swap preview; real eth.png/frax.png; switch in a clean notch.
- [ ] Exactly TWO CTAs (`Enter App` + `Start Swap`) -> target; no topbar button.
- [ ] IMAGES byte-untouched; favicon still the icon + brand mark; footer brand line + one educational line.

Make it genuinely premium, Frax-minimal and LIGHT. Then stop.
