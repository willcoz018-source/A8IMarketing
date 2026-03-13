# Activ8 Insights — Company Context for Claude Code
> Load this file at the start of any development session. This is the authoritative reference for everything about Activ8 Insights — brand, product, team, data, and strategy.

---

## 1. Company Identity

**Company Name:** Activ8 Insights
**Parent Entity:** Activ8 Finance LLC
**Website:** activ8insights.com
**Tagline:** "The Short Side of Wall Street"
**HQ:** Boston, MA

Activ8 Insights is a financial news company and data platform focused exclusively on activist short selling. It operates as a **news-first organization** — high-quality journalism builds the audience, and a subset converts into paying data product subscribers.

### Three Pillars
- **Cover** — Report on short selling campaigns like a dedicated newsroom
- **Educate** — Teach investors how activist short selling works
- **Equip** — Give sophisticated investors data tools to act on what they've learned

---

## 2. Brand

### Colors (CSS Variables — always use these)
```css
--bg:           #08090C;   /* Page background */
--surface:      #0F1117;   /* Card background */
--surface-2:    #151820;   /* Elevated card */
--surface-3:    #1B1E28;   /* Deepest surface */
--border:       #1F2333;   /* Default border */
--border-bright:#2A2F42;   /* Hover border */
--text:         #E4E7EF;   /* Primary text */
--text-mid:     #9BA1B8;   /* Secondary text */
--text-dim:     #6B7190;   /* Muted text */

/* Accent Colors */
--orange:       #FF6B2C;   /* Primary accent — breaking news, CTAs */
--blue:         #4B8BFF;   /* Weekly content, data */
--green:        #34D399;   /* Educational, success */
--purple:       #A78BFA;   /* Monthly reports */
--teal:         #2DD4BF;   /* Articles, analysis */
--amber:        #F59E0B;   /* Media recommendations */
--rose:         #F43F5E;   /* News, alerts */
--cyan:         #22D3EE;   /* LinkedIn, info */
--yellow:       #FBBF24;   /* Warnings */
--red:          #FB7185;   /* Negative, decline */
```

### Typography
```
Display/Headlines: 'Outfit' (weights 700–800)
Monospace/Labels:  'IBM Plex Mono' (weights 400–600)
Body:              'Outfit' (weights 400–500)

Google Fonts import:
@import url('https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;500;600&family=Outfit:wght@300;400;500;600;700;800&display=swap');
```

### Visual Identity Rules
- Dark backgrounds only — never light mode
- Subtle grain/noise texture overlays on hero sections
- Colored top-border stripe (3px) on cards to indicate content type
- `border-radius: 12px` on cards, `8px` on small elements
- Backdrop blur on sticky navs: `backdrop-filter: blur(20px)`
- All data/labels use IBM Plex Mono, all prose uses Outfit
- Orange is the primary action color — use for CTAs, primary highlights, breaking news
- Never use generic sans-serif fallbacks (no Arial, no system-ui as primary)

---

## 3. Team

| Name | Role | Notes |
|------|------|-------|
| Will Coz | Founder & CEO | Strategy, editorial, PR, personal outreach lead |
| Kai Rojo | CTO | All technical implementation |
| Gabe Verzino | Chief Data Officer | Dashboard data, analytics, automation |
| Matt Coz | Journalist / Editor | Content, articles, PR outreach support |
| Kenna | Marketing Contractor | Content operations |
| Truc | Data Science Intern | Data support |
| Kaitlyn Yaffe | Financial Journalism Intern | Content support |
| Close Up Marketing | External Marketing Agency (Spain) | Social media, paid media, content creation |

---

## 4. Products

### News Product
- activ8insights.com — original journalism on activist short selling
- Covers new reports as they break, tracks developments, educational content
- Free accounts give access to monthly reports (top-of-funnel strategy)

### Data Product (Dashboard) — PRIMARY REVENUE DRIVER
**Status:** Hard launch April 2, 2026

**What it is:** A subscription data dashboard covering stocks reported on by activist short sellers.

**Data scale:**
- 1,048+ activist short reports
- 849+ unique stocks tracked
- 4 daily analytics scripts (price updates, researcher returns, stock returns, company profiles)
- 30+ PostgreSQL database tables
- 65% average short seller success rate
- 110 reports tracked in 2025

**Dashboard features:**
- Activist and researcher-level filtering
- Top Decliners / Top Defiers views
- Activ8 Watchlist
- Latest News integration
- Data refresh timestamps (must be visible)
- Alerts for new short reports (must-have for launch)

### Subscription Pricing (Final)
| Tier | Price | Refund Policy |
|------|-------|---------------|
| Monthly | $99/mo | Cancel any time |
| Quarterly | $235 | No refund |
| Founders | $1,199 (2-year) | No refund, ever |

**Founders Tier Benefits:**
- Periodic exclusive Q&A conversations with activist investors
- Direct input / voting on the Activ8 analytics feature backlog
- Pre-release metrics and data access

**No Annual plan** — removed to reduce decision fatigue and push users toward Founders.

---

## 5. Current Metrics (February 2026 Baseline)

### Website (Plausible Analytics)
| Metric | Value |
|--------|-------|
| Unique Visitors | 741 |
| Total Visits | 811 |
| Total Pageviews | 1,900 |
| Views per Visit | 2.36 |
| Bounce Rate | 68% |
| Avg Visit Duration | 2m 20s |

**Top Traffic Sources:** Direct (419), Organic Search (236), Email (47), Organic Social (42), Referral (6)
**Top Referring Sites:** Google (101), Bing (61), ChatGPT (44), Twitter (38), DuckDuckGo (19)

### Newsletter (Buttondown)
- 606 total subscribers
- 12% open rate
- Weekly publication (Sundays)

### Social Media
| Platform | Followers | Status |
|----------|-----------|--------|
| X / Twitter | 211 | Primary channel — FinTwit |
| Instagram | 17 | Active — growing |
| TikTok | 0 | Business account verified |
| Facebook | 1 | Early stage |
| LinkedIn | ~19 | Just started |
| YouTube | — | Barely started |

---

## 6. Competitive Landscape

### Breakout Point
- Data-focused short selling tracker
- No journalism, no track records, no editorial voice
- **Activ8 strategy:** Go hard on direct comparison. Breakout Point is THE competitor to beat on the pricing page.

### Insightia
- Institutional-grade, expensive, covers both long and short activism
- Not a direct competitor at the retail level

### The Gap
No dedicated newsroom exists for activist short selling. Bloomberg, WSJ, Reuters cover it only tangentially. Activ8 owns this white space.

---

## 7. Marketing Partners & Tools

### Close Up Marketing (External Agency, Spain)
- Website: closeupmarketing.com
- Handles: social media content, paid media, Meta Ads, TikTok, Instagram
- February 2026 deliverables: 5 reels, 20+ graphic designs, profile optimization, TikTok Business verification, DM automations, Meta Ads setup with custom audiences
- March 2026 focus: Launch engagement/traffic campaigns, dashboard video, DM automations

### Tool Stack
| Tool | Purpose |
|------|---------|
| Plausible | Website analytics |
| Buttondown | Newsletter platform |
| Metricool | Social media scheduling |
| Meta Ads (Facebook/Instagram) | Paid social |
| Make.com | Automation orchestration |
| Placid.app | Branded image generation |
| Buffer | Social scheduling queue |
| Claude API | Copy generation |
| PostgreSQL | Data infrastructure |
| FMP (Financial Modeling Prep) | Real-time financial data |
| Marketstack | Financial data |

---

## 8. Writing & Tone Rules

When generating any copy, labels, descriptions, or UI text for Activ8:

- **No em dashes** — use colons or restructure the sentence
- **No corporate fluff** — be direct, punchy, human
- **Bullet points** preferred over long paragraphs
- **Tone:** Bloomberg Terminal meets sharp independent newsroom
- **Never** frame content as investment advice
- **Orange** for urgency, action, breaking news
- **Audience:** Sophisticated retail investors, FinTwit community

---

## 9. Key Dates

| Date | Event |
|------|-------|
| March 3, 2026 | Internal dashboard launch |
| March 9, 2026 | Soft launch |
| **April 2, 2026** | **Hard launch (public)** |
| H2 2026 | Global expansion (India + emerging markets) |
