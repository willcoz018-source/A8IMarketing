# Activ8 Insights — Marketing Planning Dashboard
## Build Instructions for Claude Code

> Always load `ACTIV8_CONTEXT.md` alongside this file before starting any work. That file contains all brand colors, typography, team details, metrics, and product context.

---

## Project Overview

Build a **multi-tab internal marketing planning dashboard** for Activ8 Insights. This is used daily by the full team (Will, Gabe, Kai, Matt, Kenna) and by the external marketing agency Close Up Marketing (Spain). It is both a planning tool and a live status board.

**Stack:** Single HTML file with vanilla JS and CSS. No build tools, no frameworks. Must run by opening the file in a browser. All styles and scripts inline.

**Aesthetic direction:** Dark, editorial, news-terminal. Matches the Activ8 brand exactly — use the CSS variables from ACTIV8_CONTEXT.md. The design should feel like a Bloomberg Terminal crossed with a premium editorial newsroom dashboard. Monospace for data, Outfit for prose. Orange is the action color.

---

## File Structure

Single file: `activ8-marketing-dashboard.html`

All CSS in a `<style>` block in `<head>`.
All JS in a `<script>` block before `</body>`.
Google Fonts imported via `<link>` tag.

---

## Navigation

Sticky top bar with:
- Left: Activ8 logo mark (dark square with "A8" in orange, 7px border-radius) + "Activ8 Insights" wordmark + subtitle "Marketing HQ"
- Right: Current date displayed in IBM Plex Mono
- Below logo row: horizontal tab bar with all 7 tabs

**Tabs (in order):**
1. 🚀 Launch Planning
2. 📊 Metrics
3. 🎯 Campaign Goals
4. 📅 Content Calendar
5. 📣 Channel Strategy
6. 💰 Budget & Spend
7. 🎨 Brand Guidelines

Active tab: orange bottom border, white text.
Inactive tab: `--text-dim` color, no border.
Tab switching: JS click handler, smooth fadeIn animation on content panels.

---

## Tab 1: 🚀 Launch Planning

**Purpose:** Central command center for the April 2nd data product launch. This is the most important tab.

### 1.1 Launch Countdown
- Large countdown display showing days/hours/minutes/seconds until April 2, 2026
- Target date: `2026-04-02T09:00:00` (9 AM ET)
- Live JavaScript countdown that updates every second
- Orange number display, IBM Plex Mono font, large (48px+)
- Label below: "Until Data Product Hard Launch"
- Status badge next to it: "🔴 T-MINUS" in red/rose styling

### 1.2 Launch Readiness Checklist
Grouped checklist with categories. Each item has a checkbox (toggleable), owner badge, and priority tag.

**Group 1: Payment & Technical (Owner: Kai)**
- [ ] Full payment flow tested end-to-end
- [ ] Auto-pay functionality confirmed
- [ ] Refund processing confirmed
- [ ] Login sharing prevention implemented
- [ ] Replace reports table with PostgreSQL
- [ ] Data refresh timestamps visible on dashboard
- [ ] Alerts feature live (new short report notifications)
- [ ] First-time user onboarding flow complete
- [ ] User activity tracking set up (feature usage, session frequency)

**Group 2: Legal (Owner: Will)**
- [ ] Attorney Ken confirms refund policy legality
- [ ] Terms of service rewritten with final pricing
- [ ] Founders tier benefits documented legally

**Group 3: Marketing (Owner: Will + Close Up)**
- [ ] Pricing page live with Breakout Point comparison
- [ ] Dashboard screenshots on pricing page
- [ ] Email sequence 1 drafted (personal, from Will)
- [ ] Email sequence 2 drafted (trader use cases)
- [ ] Email sequence 3 drafted (tips & tricks)
- [ ] Dashboard walkthrough video produced (Close Up)
- [ ] Instagram launch content ready (Close Up)
- [ ] TikTok launch content ready (Close Up)
- [ ] Twitter pre-launch teaser posts scheduled
- [ ] Personal outreach email drafted (Will)
- [ ] Gabe personal outreach drafted

**Group 4: PR (Owner: Will + Matt)**
- [ ] Reporter outreach list built (WSJ, Bloomberg, Reuters, etc.)
- [ ] PR pitch email drafted (free 1-month license offer)
- [ ] Outreach started to top 10 reporters

**Group 5: Content (Owner: Matt + Kenna)**
- [ ] Matt's 20 backlog articles posted to site
- [ ] Guide/help page updated
- [ ] Media recommendations page updated
- [ ] Gabe's "how I use the dashboard as a trader" piece written

Show a progress bar at the top of the checklist: "X of Y items complete — Z% ready". Update dynamically as boxes are checked. Store checkbox state in memory (JS object) so it persists during the session.

### 1.3 Launch Email Sequence
Three cards side by side showing the email plan:

**Card 1 — Day 1: The Personal Note**
- Owner: Will / Gabe / Kai
- Tone: Personal, warm, founder-to-subscriber
- Key message: We built something. Here's why it matters to you.
- CTA: Log in and explore the dashboard
- Status badge: [DRAFT IN PROGRESS]

**Card 2 — Day 2: The Trader's Playbook**
- Owner: Gabe
- Tone: Practical, trader-to-trader
- Key message: Here's exactly how I use this dashboard in my own trading
- Content: Specific examples — following a short seller's pattern, sector targeting, building positions
- CTA: Try these strategies yourself
- Status badge: [NOT STARTED]

**Card 3 — Day 3: Tips & Tricks**
- Owner: Will
- Tone: Product, educational
- Key message: Power features you might have missed
- Content: Filters, watchlist, researcher profiles, data refresh protocol, alerts setup
- CTA: Upgrade to Founders for pre-release data
- Status badge: [NOT STARTED]

### 1.4 Personal Outreach Tracker
A section for tracking personal network outreach. This is separate from PR — this is friends, family, and personal connections.

**Header:** "Personal Network — Every Account Matters"
**Subtext:** "Even a free account signup and email open helps. Ask everyone."

Table or card grid with:
- Owner column: Will / Gabe / Kai / Matt
- Target count (how many contacts each person has committed to reaching)
- Status: Not Started / In Progress / Sent / Done
- Action: "View Email Template" button (opens a modal or inline section with the draft email)

**Draft personal outreach email template (inline, collapsible):**
```
Subject: I built something — would mean a lot if you checked it out

Hey [Name],

Quick favor to ask. I've been working on something called Activ8 Insights
for the past couple of years — it's a news platform and data dashboard
covering activist short selling on Wall Street.

We just launched our data product and even just creating a free account
and opening our emails genuinely helps us grow. It takes 60 seconds:

→ [activ8insights.com]

If you want to follow us on Twitter/Instagram that helps too.

No pressure at all — just means a lot to have people in my corner.

Thanks,
[Name]
```

### 1.5 PR Outreach Tracker
**Purpose:** Track outreach to journalists who cover short selling and could use/cite the Activ8 data product.

**Header:** "PR — Journalist Outreach"
**Strategy:** Reach out to reporters who cite Breakout Point. Offer free 1-month license. Position as the better source with journalism included.

Table with columns:
- Reporter Name
- Publication (WSJ / Bloomberg / Reuters / FT / etc.)
- Topic Focus
- Status (Not Contacted / Reached Out / Replied / Licensed)
- Owner (Will / Matt)
- Notes

Pre-populate with placeholder rows for the target outlets:
- Wall Street Journal — Short selling / markets
- Bloomberg — Activist investing
- Reuters — Financial fraud / markets
- Financial Times — Short selling
- Barron's — Markets
- Business Insider — Finance
- The Information — Tech shorts
- Dealbreaker — Wall Street

**PR Pitch template (collapsible):**
```
Subject: Better short selling data — free for journalists

Hi [Name],

I've been following your coverage of [topic] — great work on [article].

I wanted to introduce Activ8 Insights (activ8insights.com). We just
launched a data dashboard tracking 1,048+ activist short reports across
849 stocks, with journalist-grade sourcing and daily data updates.

We'd love to offer you a free license while you explore it. If you're
ever writing about short selling campaigns, we're happy to be a resource.

Reply here and I'll set you up.

Will Coz
Founder, Activ8 Insights
```

---

## Tab 2: 📊 Metrics Dashboard

**Purpose:** Live view of all key metrics across web, social, and newsletter. Designed for both the internal team and Close Up Marketing to check daily/weekly.

**Important:** Build this tab with placeholder data that exactly matches the real February 2026 numbers from ACTIV8_CONTEXT.md. Add a visible note at the top: "Connect live data via API keys in the CONFIG section at the top of this file." Add a `CONFIG` JS object at the top of the script block where keys can be dropped in.

```javascript
const CONFIG = {
  plausible: {
    apiKey: '', // Plausible API key
    siteId: 'activ8insights.com',
  },
  buttondown: {
    apiKey: '', // Buttondown API key
  },
  // When keys are present, the dashboard fetches live data.
  // When empty, it falls back to the BASELINE_DATA below.
};
```

### 2.1 KPI Strip (top row)
Six stat cards in a row:
1. Website Visitors (monthly) — 741 — trend arrow up
2. Newsletter Subscribers — 606 — trend arrow up
3. Newsletter Open Rate — 12% — trend neutral
4. Total Social Followers — 248 (sum of all platforms) — trend arrow up
5. Total Social Impressions (Feb) — 1,467 — new baseline
6. Total Social Interactions (Feb) — 33 — new baseline

Each card: large number in accent color, label below, small trend indicator.

### 2.2 Website Analytics (Plausible)
Two-column layout:

**Left — Core Metrics table:**
| Metric | Feb 2026 | Change |
|--------|----------|--------|
| Unique Visitors | 741 | +46% |
| Total Visits | 811 | +50% |
| Pageviews | 1,900 | +66% |
| Views/Visit | 2.36 | +10% |
| Bounce Rate | 68% | +3% |
| Avg Duration | 2m 20s | +9% |

**Right — Traffic Sources breakdown:**
Bar chart (CSS-only bars, no library needed) showing:
- Direct: 419
- Organic Search: 236
- Email: 47
- Organic Social: 42
- Referral: 6

Note at bottom: "ChatGPT.com drives 44 direct referrals — AEO is working."

### 2.3 Newsletter Metrics (Buttondown)
Stats: 606 subscribers, 12% open rate, weekly cadence (Sundays)
Open rate benchmark context: "Industry average ~21%. Target: 20%+ by Q3 2026."
Visual progress bar toward 1,000 subscriber goal.

### 2.4 Social Media Platform Cards
One card per platform. Each card shows:
- Platform name + colored icon area
- Follower count
- Posts this month
- Impressions
- Interactions
- Engagement rate (interactions / impressions)
- Status badge (Active / Early Stage / Not Started)

**Platform data (Feb 2026 baseline):**
- X / Twitter: 211 followers | Primary channel | No Meta data yet
- Instagram: 17 followers | 12 posts | 1,228 impressions | 27 interactions
- TikTok: 0 followers | 7 posts | 154 impressions | 4 interactions
- Facebook: 1 follower | 12 posts | 85 impressions | 2 interactions
- LinkedIn: 19 followers | Early stage | — impressions

### 2.5 Goals vs. Actuals Table
Show targets for end of Q2 2026 (June 30) vs. current baseline:

| Metric | Feb Baseline | Q2 Target | Progress |
|--------|-------------|-----------|----------|
| Twitter Followers | 211 | 1,000 | 21% |
| Instagram Followers | 17 | 500 | 3% |
| Newsletter Subscribers | 606 | 1,000 | 61% |
| Website Unique Visitors/mo | 741 | 2,500 | 30% |
| Paid Subscribers | 0 | 50 | 0% |

Progress shown as colored bars (green if on track, amber if behind, red if significantly behind).

---

## Tab 3: 🎯 Campaign Goals

**Purpose:** Define what we're trying to accomplish in 2026, with measurable outcomes tied to each goal.

### 3.1 2026 Primary Goals
Four goal cards:

**Goal 1: Launch & Grow the Data Product**
- Target: 50 paid subscribers by June 30, 2026
- Target: 200 paid subscribers by December 31, 2026
- Revenue at 200 subs (blended): ~$20,000 ARR estimate
- Key levers: Hard launch April 2, email sequence, PR, personal outreach

**Goal 2: Build Social Presence**
- Twitter: 1,000 followers by Q2
- Instagram: 500 followers by Q2
- Post cadence: 30+ posts/month across all platforms
- Key levers: Close Up Marketing, content automation, Gabe's Twitter Studio

**Goal 3: Grow Newsletter to 1,000 Subscribers**
- Current: 606
- Target: 1,000 by June 30, 2026
- Strategy: Meta paid campaigns, DM automations, social CTAs, personal outreach
- Improve open rate from 12% to 20%+

**Goal 4: Establish PR & Media Presence**
- Get cited in at least 3 financial publications by Q3 2026
- Build journalist relationship list (target: 20 reporters)
- Offer free licenses to all target reporters at launch

### 3.2 Launch Campaign Goals (April 2)
Specific targets for launch week:
- Day 1 email open rate target: 25%+
- Launch week signups target: 10 paid subscribers
- Launch week free account creations: 50+
- Twitter impressions launch week: 5,000+
- Personal outreach responses: 30%+ reply rate

---

## Tab 4: 📅 Content Calendar

**Purpose:** Show what content is planned and when. Designed for both internal team and Close Up Marketing.

### 4.1 Current Month View
Display a calendar grid for the current month (March 2026 or April 2026 depending on current date). Each day cell can hold content items.

Pre-populate with known recurring items:
- Every Friday: "This Week in Short Selling" (Weekly Summary)
- 1st of month: Monthly Report
- March 16: Soft launch social push (note)
- April 2: 🚀 HARD LAUNCH — full social blast + email sequence begins

Each content item shown as a small colored pill on the calendar:
- 🔴 Breaking Short Reports: orange
- 📝 Articles: teal
- 📚 Learning Guides: green
- 🎙️ Media Recs: amber
- 📰 News Posts: rose
- 📅 Weekly Summary: blue
- 📊 Monthly Report: purple

### 4.2 Content Volume Tracker
Show monthly target vs. actual for each content type:

| Content Type | Target/Month | Published | Remaining |
|---|---|---|---|
| Short Reports | Event-driven | — | — |
| Articles | 4 | 0 | 4 |
| Learning Guides | 2 | 0 | 2 |
| Media Recommendations | 2 | 0 | 2 |
| Short Selling News | 8–12 | 0 | 8–12 |
| Weekly Summaries | 4 | 0 | 4 |
| Monthly Report | 1 | 0 | 1 |

### 4.3 Launch Week Content Plan (April 2–8)
Detailed day-by-day plan for launch week with specific posts planned per platform.

---

## Tab 5: 📣 Channel Strategy

**Purpose:** Define the role of each channel, who owns it, current status, and what success looks like.

### 5.1 Channel Cards
One card per channel, with color-coded top stripe:

**X / Twitter (Primary — Orange)**
- Owner: Will + Gabe
- Audience: FinTwit — sophisticated retail investors, traders, short sellers
- Strategy: Breaking reports, data takes, trader perspective from Gabe, weekly recaps
- Current: 211 followers
- Target: 1,000 by Q2
- Tools: Metricool, Activ8 Twitter Studio (in development)
- Priority: HIGHEST

**Instagram (Growth — Pink)**
- Owner: Close Up Marketing
- Audience: Broader finance/investing community
- Strategy: Visual cards, carousels, reels, branded content
- Current: 17 followers
- Target: 500 by Q2
- Tools: Meta Business Suite, Close Up Managing
- Priority: HIGH

**Newsletter / Email (Conversion — Blue)**
- Owner: Will + Kenna
- Platform: Buttondown
- Audience: Existing subscribers — most likely to convert to paid
- Strategy: Weekly recap, product updates, launch announcements
- Current: 606 subscribers, 12% open rate
- Target: 1,000 subscribers, 20% open rate by Q2
- Priority: HIGH

**TikTok (Reach — Teal)**
- Owner: Close Up Marketing
- Audience: Younger retail investors, finance TikTok community
- Strategy: Short explainer videos, breaking news visual content
- Current: 0 followers (Business account verified)
- Target: 200 by Q2
- Priority: MEDIUM

**LinkedIn (Professional — Cyan)**
- Owner: Will
- Audience: Finance professionals, potential institutional partners
- Strategy: Thought leadership, monthly reports, product announcements
- Current: 19 followers
- Target: 200 by Q2
- Priority: MEDIUM

**Facebook (Supplemental — Purple)**
- Owner: Close Up Marketing (via Meta Ads)
- Strategy: Paid traffic + content distribution
- Current: 1 follower
- Priority: LOW (ads-first, not organic growth focus)

### 5.2 Paid Media Status
Card showing Meta Ads setup status:
- Meta Ads account: Connected ✓
- Meta Pixel: Installed ✓
- Custom Audiences built: ✓ (website visitors 30d, top 5%, IG followers, FB followers, engagement audiences)
- Campaigns launched: NOT YET — launching March/April
- Budget: TBD

---

## Tab 6: 💰 Budget & Spend

**Purpose:** Track marketing tool costs and agency spend.

### 6.1 Monthly Tool Costs

| Tool | Purpose | Cost/Month |
|------|---------|-----------|
| Make.com | Automation orchestration | $9 |
| Buffer | Social scheduling | $30 |
| Placid.app | Branded image generation | $29 |
| Canva Pro | Design templates | $13 |
| Claude API | Copy generation | ~$10 |
| Metricool | Social analytics/scheduling | TBD |
| Shutterstock / Adobe Stock | Editorial photos | $29 |
| **Tool Total** | | **~$120/mo** |

### 6.2 Agency Spend
| Agency | Scope | Cost |
|--------|-------|------|
| Close Up Marketing | Social, paid media, content | TBD — add actual monthly retainer |

### 6.3 Paid Media Budget
- Meta Ads (Facebook + Instagram): TBD — launching April
- Target: Engagement + traffic campaigns initially
- Budget tracking table with columns: Campaign, Platform, Budget, Spent, Results

### 6.4 Revenue Targets vs. Spend
Show simple ROI projection:
- Monthly tool + agency cost: ~$X
- Revenue needed to break even: $X / month
- Subscribers needed at blended rate: ~X paid subscribers
- Current: $0 ARR (pre-launch)
- April target: 10 paid subscribers = ~$X MRR

---

## Tab 7: 🎨 Brand Guidelines

**Purpose:** Reference for Close Up Marketing and any new team members. Single source of truth for all brand decisions.

### 7.1 Logo
- Primary mark: Dark background square with "A8" in orange, 7px border-radius
- Wordmark: "Activ8 Insights" in Outfit 700
- Tagline: "The Short Side of Wall Street™"
- Never use on light backgrounds

### 7.2 Color Palette
Display all CSS variables as swatches with hex codes and usage notes. (Use the full color list from ACTIV8_CONTEXT.md)

### 7.3 Typography
Show font specimens:
- Outfit 800: Display headlines
- Outfit 600: Section titles
- Outfit 400: Body copy
- IBM Plex Mono 600: Data labels, tags, metrics
- IBM Plex Mono 400: Code, timestamps

### 7.4 Content Type Color Coding
Show each of the 7 content types with their assigned accent color:
- Breaking Short Reports: Orange `#FF6B2C`
- Article Postings: Teal `#2DD4BF`
- Learning Guides: Green `#34D399`
- Media Recommendations: Amber `#F59E0B`
- Short Selling News: Rose `#F43F5E`
- Weekly Summaries: Blue `#4B8BFF`
- Monthly Reports: Purple `#A78BFA`

### 7.5 Voice & Tone Rules
- No em dashes — use colons or rewrite
- No corporate fluff — direct, punchy, human
- Bold and confident — "We go hard on Breakout Point comparisons"
- Never: investment advice framing
- Always: news-first framing
- Audience: sophisticated retail investors, FinTwit community

### 7.6 Post Visual Formula
Show the universal post visual formula:
- Dark background (grain texture overlay)
- Content type tag at top (IBM Plex Mono, colored pill)
- Bold white headline (Outfit 800, key term in accent color)
- Supporting stats row or subheadline
- activ8insights.com watermark at bottom
- 70–85% dark overlay when using photo backgrounds

---

## Technical Requirements

### Performance
- No external JS libraries
- No build tools — pure HTML/CSS/JS
- Loads instantly by opening in browser
- Smooth tab transitions (CSS fadeIn animation, ~0.3s)

### Interactivity
- Tab switching: click handler on nav tabs
- Checklist: toggleable checkboxes that update the progress bar in real time
- Countdown: live JS countdown to April 2, 2026 9AM ET
- Collapsible sections: email templates, PR pitch — click to expand/collapse
- Checkbox state persists in JS object (not localStorage — session only)

### Data Configuration
At the top of the `<script>` block, include a `CONFIG` object:
```javascript
const CONFIG = {
  plausible: { apiKey: '', siteId: 'activ8insights.com' },
  buttondown: { apiKey: '' },
};

const BASELINE_DATA = {
  website: {
    uniqueVisitors: 741, totalVisits: 811, pageviews: 1900,
    viewsPerVisit: 2.36, bounceRate: 68, avgDuration: '2m 20s',
    sources: { direct: 419, organicSearch: 236, email: 47, organicSocial: 42, referral: 6 }
  },
  newsletter: { subscribers: 606, openRate: 12 },
  social: {
    twitter: { followers: 211, posts: null, impressions: null, interactions: null },
    instagram: { followers: 17, posts: 12, impressions: 1228, interactions: 27 },
    tiktok: { followers: 0, posts: 7, impressions: 154, interactions: 4 },
    facebook: { followers: 1, posts: 12, impressions: 85, interactions: 2 },
    linkedin: { followers: 19, posts: null, impressions: null, interactions: null },
  }
};
```

When API keys are present in CONFIG, fetch live data and replace BASELINE_DATA values. When keys are empty, use BASELINE_DATA throughout. Display a subtle indicator in the Metrics tab: "🟡 Using baseline data — add API keys to CONFIG to go live."

### Responsive
- Desktop-first but readable on tablet
- Nav tabs scroll horizontally on small screens
- Cards stack vertically below 768px

### Footer
Every tab: small footer with "Activ8 Insights · The Short Side of Wall Street™ · Internal Use Only"

---

## Aesthetic Reference

The finished dashboard should feel like:
- A Bloomberg Terminal that got a design refresh
- A war room dashboard for a fast-moving news operation
- Something the Close Up Marketing team in Spain opens and immediately understands the urgency and ambition of what Activ8 is building

**Do not make it look like a generic SaaS admin panel.** It should feel specific, editorial, and alive. Every data point should feel meaningful. The countdown timer to April 2nd should create urgency every time someone opens the tab.
