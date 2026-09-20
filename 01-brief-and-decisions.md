# WISDOMUP wisdomup.cn — wholesale landing page

**Date:** 2026-09-19 · **Deliverable:** Design canvas, two artboards
**Canvas:** https://claude.ai/artifact/XPdVGH2uJemNaxXtxzv3Ja *(private — share from the page's Share menu)*

---

## 1. The brief, as it settled

Started as "a one page factory portfolio, very short intro, WISDOMUP mobile accessories brand". After checking wisdomup.pk it narrowed to:

> A **very light, one-screen page**, heavily modernized, in the brand red — whose entire job is the CTA: **send a wholesale order, or get in touch**.

**wisdomup.cn = the China manufacturing arm.** The .pk brand story is Pakistan-rooted in-house production; this site speaks for the OEM/ODM factory side, to overseas brands and distributors.

## 2. What changed from the first draft

| First draft | Now | Why |
|---|---|---|
| 3,760px scrolling portfolio, 7 sections | **One screen**, 1440 × 900 | The page sells one action, not a company history |
| Light warm ground + cobalt accent | **White + brand red `#E40014`** | Cobalt was off-brand; red is the .pk `--primary` |
| Space Grotesk / IBM Plex | **Bricolage Grotesque / Geist / Geist Mono** | The exact faces wisdomup.pk uses |
| 2px square corners | **Pill buttons, 16–20px cards** | Matches .pk (`--radius-pill`, `--radius-lg`) and reads modern |
| Six product cards, process, capability, stats | **Six category pills in a bottom strip** | Same coverage, one line, no scroll |

## 3. The look

**Light inversion of the .pk dark theme — same brand, opposite ground.**

| Role | Value | Comes from |
|---|---|---|
| Accent | `#E40014` | `.pk --primary`, unchanged |
| CTA glow | `0 16px 40px` accent @ 28% | `.pk --shadow-glow`, lightened |
| Ink | `#0A0A0A` | inverse of `.pk --foreground` |
| Body text | `#4A4A4A` | AA on white |
| Muted / mono labels | `#6E6E6E` | 5.2:1 on white |
| Ground | `#FFFFFF` | inverse of `--surface-0` |
| Strip / panel | `#FAFAFA` / `#F6F6F6` | inverse of `--surface-1/2` |
| Rules | `#ECECEC` / `#E0E0E0` | inverse of `--border` |

**Type** — Bricolage Grotesque 700 for the headline at `-0.035em` tracking, Geist for body, Geist Mono for the eyebrow and spec lines at `0.22em` tracking. All three are the .pk faces and all three are on Google Fonts.

**Wordmark** — `WISDOM` in ink, `UP` in red. One small modern move that ties the trade site to the shop.

**Contrast** — white on `#E40014` is 4.87:1 and red on white is 4.87:1, both AA for body text. Red is safe here as text, unlike on .pk's black where it drops to 4.2:1.

## 4. Layout

**Desktop 1440 × 900** — header (wordmark · `FACTORY · OEM & ODM` · email · ghost CTA) / hero split: copy left, image panel right / bottom strip: category pills + phone + city.

**Mobile 390 × 844** — same content, stacked; image panel flexes to fill; both CTAs full-width pills.

Everything sits inside one viewport. No scroll on either.

## 5. Still open

1. **Numbers and contacts** — `[YEAR]`, `[CITY]`, `[QTY]` MOQ, sample days, `[SALES@WISDOMUP.CN]`, `[+86 …]`. The .pk site gives 2014 founded and +92-327-9800153 / wisdomuppk@gmail.com, but those are the Pakistan retail arm — confirm what the China arm uses.
2. **One product image** — the single visual slot (1040 × 1120 desktop) carries the whole page. A clean product group shot or a line photo.
3. **Where the CTA goes** — a mailto, a WhatsApp/WeChat link, or a short wholesale form. Right now both buttons are placeholders.
