# wisdomup.pk — structure & colour scheme audit

**Checked:** 2026-09-19 · **Source:** live site HTML + its compiled stylesheets (`_next/static/chunks/*.css`)
**Stack:** Next.js (App Router, Turbopack) + Tailwind v4, headless CMS at `admin.wisdomup.co`

---

## 1. Colour scheme — the actual tokens

The site ships **one dark theme only** (no light mode defined). Values below are the literal hex in the stylesheet.

### Core

| Token | Hex | Role |
|---|---|---|
| `--primary` | **`#E40014`** | Brand red. CTAs, prices, badges, active states, focus ring |
| `--primary-foreground` | `#FFFFFF` | Text on red |
| `--surface-0` / `--background` | **`#030303`** | Page ground (near-black) |
| `--surface-1` | `#090909` | Raised band |
| `--surface-2` / `--card` | `#0D0D0D` | Cards |
| `--surface-3` / `--muted` / `--secondary` / `--accent` | `#161616` | Chips, inputs, secondary buttons |
| `--foreground` | `#FAFAFA` | Primary text |
| `--muted-foreground` | `#A4A4A4` | Captions, meta, helper text |
| `--border` | `#FFFFFF` @ 10% | Hairlines |
| `--border-strong` | `#FFFFFF` @ 20% | Emphasised edges |
| `--border-accent` | `--primary` @ 55% | Highlighted cards |

### Status

| Token | Hex |
|---|---|
| `--success` | `#2BBB71` |
| `--warning` | `#EFA831` |
| `--destructive` | `#E8395C` |

### Shape & depth

- `--radius: 0.625rem` (10px) · `--radius-sm: 6px` · `--radius-lg: 16px` · `--radius-pill: 9999px`
- `--shadow-glow: 0 18px 44px` of primary @ 34% — the red glow under hero CTAs and featured cards
- `--ring: --primary` at 70% mixed toward white

### Not a brand colour

The violet/purple you see across the hero is **campaign artwork** (`hero-slide-web.png`), not a token. Nothing in the stylesheet defines purple. Treat red-on-black as the brand; the purple is one seasonal banner.

### Contrast notes

- White on `#E40014` → **4.87:1** — passes AA for body text, just.
- `#E40014` on `#030303` → **4.23:1** — fine for headings 24px+, **fails** for small red body text. Use it for large type, fills and rules, not paragraphs.
- `#A4A4A4` on `#030303` → 8.3:1 — comfortable.

---

## 2. Typography

| Role | Face | Notes |
|---|---|---|
| Display / headings | **Bricolage Grotesque** | `--font-display-face`, self-hosted via next/font |
| Body | **Geist** | `--font-body-face` |
| Mono | **Geist Mono** | numerics, spec labels |

**Scale** (all multiplied by a `--scale` variable):

| Step | Size |
|---|---|
| display | `clamp(2.5rem, 5.5vw, 4rem)` |
| h1 | `clamp(2rem, 3.5vw, 2.75rem)` |
| h2 | `clamp(1.75rem, 3vw, 2.5rem)` |
| h3 | `1.25rem` |
| body | `1rem` |
| caption | `0.8125rem` |
| micro | `0.75rem` |

**Tracking:** display `-0.035em` · heading `-0.02em` · body `0` · **eyebrow `0.22em`**
**Leading:** display `1` · heading `1.15` · body `1.6` · relaxed `1.625`

The wide-tracked eyebrow over a tight-tracked display heading is the signature move of the site. Weights run 300–700.

---

## 3. Page structure — homepage, top to bottom

1. **Sticky header** — logo · category links (Smart Watches, Earbuds, Headphones, Speakers) · Products · Live · Bulk Order · About Us · a "Shop By" dropdown · search / cart / account icons · hamburger on mobile
2. **Hero slider** — full-bleed campaign art, h1 + "Shop Now" + feature chips (RGB LED Lights · Customized EQ Modes · IPX6 Splash Resistance). Two slides
3. **Shop by Category** — ~18 category tiles (Mobile Holder, Speaker, Headphone, Converter, Wireless Charger, Power Bank, Mouse, Neckband, Mic, Charger, Electronics, Car Electronics, Earbuds, Speakers & Soundbars …)
4. **Brand band** — "Pure Sound. Smart Design." + short paragraph + Shop Now
5. **New Arrivals / Best Sellers** — tabbed product grid; each card: image, category label, name, price, struck compare-at price, `% off` badge, "View product"
6. **Featured Products** — heading + one-line subtitle + grid
7. **Explore Big Deals** — heading + subtitle + grid
8. **"Feel Every Beat"** — image + copy band
9. **Testimonials** — "What people are saying / Loved by listeners", 4 star-rated cards
10. **Engineered for Excellence** — 3 feature cards (Studio-grade drivers · All-day battery · Built to last)
11. **FAQ** — 5-item accordion
12. **Trust strip** — Fast, Free Shipping · 30-Day Money-Back Guarantee · Hassle-Free Warranty · Lifetime Customer Support
13. **Mega footer** — 4 link columns (Products / Explore / Support / Contact Us) + newsletter signup + policies row + copyright

### Real company facts found on /about

These fill several blanks in our draft — **confirm before publishing**:

- **Founded 2014**, bootstrapped, homegrown
- **12+ product lines · 180k customers · 98% 5-star reviews**
- **Designs and assembles in-house** — "unlike many brands that outsource production, WisdomUp retains complete control over the product lifecycle"
- Positioning: *"Innovating tech. Inspiring Pakistan."* — explicitly Pakistan-rooted, globally benchmarked, affordable premium
- **Contact:** +92-327-9800153 · wisdomuppk@gmail.com · Mon–Sun, 10 AM – 6 PM

⚠️ The four testimonials (Amelia Chen, Marcus Bailey, Sofia Reyes, Robert Klein) read as placeholder content left in from a template.

---

## 4. What this means for the wisdomup.cn factory page

| Our draft | wisdomup.pk | Verdict |
|---|---|---|
| Light warm ground `#F2F1EC` | Near-black `#030303` | **Off-brand — change** |
| Cobalt accent `#2544D8` | Red `#E40014` | **Off-brand — change** |
| Space Grotesk / IBM Plex Sans / IBM Plex Mono | Bricolage Grotesque / Geist / Geist Mono | **Change to match** |
| Eyebrow tracking `0.16em` | `0.22em` | Match |
| Display tracking `-0.035em` | `-0.035em` | Already matches |
| Radius 2px (square) | 10px, pill for chips | Match |
| "[CITY], China" | Brand is Pakistan-based, in-house production | **Needs your answer** |

Two open questions before the re-skin:

1. **Dark or light?** Straight dark-and-red like .pk, or a lighter B2B variant built from the same tokens so the trade site reads differently from the consumer shop.
2. **Where is the factory?** Our draft assumed China because of the `.cn` domain, but the .pk brand story is explicitly Pakistani in-house production. Which does wisdomup.cn represent?
