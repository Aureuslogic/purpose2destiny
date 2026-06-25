# Aulteus Logic, Full Developer Brief
### SEO, AEO, Schema Markup, Copy Fixes, and New Files
### Version: June 2026, Send to developer tonight

---

## Priority Order

Media articles and press are going live soon. Before those links land, the site must have:

1. Canonical domain locked and all redirects in place (backlinks need to land somewhere clean)
2. robots.txt and sitemap.xml live so Google can crawl from day one
3. OG/Twitter social cards live so every article share previews professionally
4. All schema markup in the page head
5. Banker's Code removed throughout

Do items in that order. Everything else can follow.

---

## SECTION 1: Copy Changes, Remove "The Banker's Code"

This phrase belongs to an existing book by another author. It is unwinnable in search and splits the brand signal. Every reference below must be removed or replaced with "Aulteus Logic," "Decision Governance," or "The Logic Engine" as appropriate.

### 1.1 Exact locations in the codebase

| Location | Current text | Action |
|---|---|---|
| `<title>` tag | `Non Linear Decision Intelligence \| Aulteus Logic & The Banker's Code` | Remove `& The Banker's Code` |
| Hero subtext paragraph | `We teach you the "Banker's Code"—the exact framework...` | Rewrite. Suggested: `We teach you Aulteus Logic, the exact decision framework used by the top 1% to govern Forex, Gold, Oil and Indices.` |
| Pricing card heading (tier 2) | `The Banker's Code Bundle` | Rename. Suggested: `The Aulteus Logic Complete Mentorship` or `Decision Governance Bundle` |
| Market Reality bullet | `How structure is read (The Banker's Way)` | Rewrite. Suggested: `How structure is read the institutional way` |
| Founder bio subline | `Creator of "The Banker's Code"` | Remove or replace. Suggested: `Inventor of the Aulteus Logic Decision Framework` |
| Footer, Product column | `The Banker's Code Bundle` | Rename to match the new pricing card name above |
| Nav breadcrumb note | No change needed here |  |

Run a full codebase text search for `Banker` (case insensitive) to catch anything in components, config files, or CMS entries not listed above.

---

## SECTION 2: Head Tag Updates (every page)

Replace or add the following inside `<head>` on the homepage. Subpages (privacy, terms, risk disclosure) should have their own unique title and description.

```html
<!-- TITLE, updated: Banker's Code removed, keywords added -->
<title>Non Linear Decision Intelligence | Aulteus Logic | Forex, Gold, Oil and Indices</title>

<!-- META DESCRIPTION, 157 characters, keyword-rich, matches page intent -->
<meta name="description" content="Stop Guessing. Start Trading with Institutional Precision. Aulteus Logic is the decision governance framework built for Forex, Gold, Oil and Indices traders." />

<!-- CANONICAL, locks the canonical domain, prevents split authority -->
<link rel="canonical" href="https://aulteuslogic.com/" />

<!-- OPEN GRAPH (Facebook, LinkedIn, WhatsApp previews; critical when media articles share your URL) -->
<meta property="og:type" content="website" />
<meta property="og:url" content="https://aulteuslogic.com/" />
<meta property="og:site_name" content="Aulteus Logic" />
<meta property="og:title" content="Non Linear Decision Intelligence | Aulteus Logic" />
<meta property="og:description" content="Stop Guessing. Start Trading with Institutional Precision. Aulteus Logic is the decision governance framework built for Forex, Gold, Oil and Indices traders." />
<meta property="og:image" content="https://aulteuslogic.com/assets/og-image.jpg" />
<meta property="og:image:width" content="1200" />
<meta property="og:image:height" content="630" />
<meta property="og:locale" content="en_GB" />

<!-- TWITTER / X CARD (controls how the link looks when shared on X) -->
<meta name="twitter:card" content="summary_large_image" />
<meta name="twitter:title" content="Non Linear Decision Intelligence | Aulteus Logic" />
<meta name="twitter:description" content="Decision governance for Forex, Gold, Oil and Indices. The framework built to help traders act with institutional precision." />
<meta name="twitter:image" content="https://aulteuslogic.com/assets/og-image.jpg" />
```

**Note on og:image:** Create a branded image at exactly 1200 x 630 pixels with the Aulteus Logic logo on a dark background. Save it as `/assets/og-image.jpg`. Without this, every media article share will show a blank or wrong preview image, which kills click-through.

---

## SECTION 3: All Schema Markup (JSON-LD, paste in `<head>`)

Paste each block as a separate `<script type="application/ld+json">` tag. Do not merge them into one object. Keep them separate so Google can parse each type independently.

### 3.1 WebSite Schema (enables search understanding and sitelinks)

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "WebSite",
  "name": "Aulteus Logic",
  "url": "https://aulteuslogic.com",
  "description": "A non linear decision asset framework for Forex, Gold, Oil and Indices traders. Decision governance, not financial advice.",
  "inLanguage": "en-GB",
  "publisher": {
    "@type": "Organization",
    "name": "Aulteus Logic",
    "url": "https://aulteuslogic.com"
  }
}
</script>
```

### 3.2 Organization Schema (builds Google Knowledge Graph entity; critical for brand searches and AI citations)

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "Aulteus Logic",
  "url": "https://aulteuslogic.com",
  "logo": "https://aulteuslogic.com/assets/logo-new.png",
  "description": "Aulteus Logic is a non linear decision asset framework expressed through Agentic AI. It helps traders decide whether to act, remain neutral, or wait during uncertain market conditions. It does not place trades, is not a trading platform, and can be used alongside any trading platform worldwide.",
  "email": "Hello@aulteuslogic.com",
  "knowsAbout": [
    "Forex trading decision frameworks",
    "Institutional trading methodology",
    "Non linear decision intelligence",
    "Commodities trading education",
    "Gold and Oil trading",
    "Decision governance under uncertainty",
    "Agentic AI for market analysis"
  ],
  "founder": {
    "@type": "Person",
    "name": "Sam Onigbanjo"
  },
  "sameAs": [
    "ADD LINKEDIN URL HERE",
    "ADD YOUTUBE CHANNEL URL HERE",
    "ADD X/TWITTER URL HERE"
  ]
}
</script>
```

**Note:** Fill in the sameAs URLs with the actual social profile links. These are how Google connects your brand name to your social presence. The more consistent your name across platforms, the stronger the entity signal.

### 3.3 Person Schema (establishes Sam Onigbanjo as an authority; helps E-E-A-T for YMYL finance content)

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Person",
  "name": "Sam Onigbanjo",
  "jobTitle": "Inventor of Aulteus Logic",
  "description": "After years in corporate strategy and capital markets, Sam Onigbanjo created Aulteus Logic, a non linear decision framework to govern trading decisions under uncertainty. He observed the same pattern repeatedly: intelligent people making poor decisions under pressure not because they lacked knowledge, but because they lacked a decision asset.",
  "image": "https://aulteuslogic.com/assets/author.jpg",
  "worksFor": {
    "@type": "Organization",
    "name": "Aulteus Logic",
    "url": "https://aulteuslogic.com"
  },
  "url": "https://aulteuslogic.com",
  "sameAs": [
    "ADD SAM'S LINKEDIN PROFILE URL HERE"
  ]
}
</script>
```

### 3.4 BreadcrumbList Schema (matches the existing breadcrumb on the page)

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    {
      "@type": "ListItem",
      "position": 1,
      "name": "Home",
      "item": "https://aulteuslogic.com/"
    },
    {
      "@type": "ListItem",
      "position": 2,
      "name": "Agentic Decision Intelligence",
      "item": "https://aulteuslogic.com/"
    },
    {
      "@type": "ListItem",
      "position": 3,
      "name": "Aulteus Logic",
      "item": "https://aulteuslogic.com/"
    }
  ]
}
</script>
```

### 3.5 FAQPage Schema (enables Google AI Overviews and ChatGPT to cite these answers directly; built from the live page text, word for word)

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "Is Aulteus Logic regulated by the Financial Conduct Authority?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "No. Aulteus Logic is not authorised or regulated by the Financial Conduct Authority. Aulteus Logic does not carry on any regulated activity under the Financial Services and Markets Act 2000 or the Regulated Activities Order."
      }
    },
    {
      "@type": "Question",
      "name": "Does Aulteus Logic provide investment advice or financial advice?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "No. Aulteus Logic does not provide investment advice, financial advice, personal recommendations, or suitability assessments. All content and outputs are provided strictly for educational and informational purposes only and are general in nature."
      }
    },
    {
      "@type": "Question",
      "name": "Does Aulteus Logic tell users what trades to place?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "No. Aulteus Logic does not instruct users to place trades, execute trades, or take any specific financial action. Any market analysis, scenarios, probabilities, or decision frameworks are provided solely to illustrate educational concepts and analytical thinking. All decisions remain the sole responsibility of the user."
      }
    },
    {
      "@type": "Question",
      "name": "Does Aulteus Logic make personal recommendations?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "No. Aulteus Logic does not make personal recommendations as defined by the Financial Conduct Authority. The platform does not consider individual financial circumstances, objectives, experience, or risk tolerance. All information is non-personalised and non-advisory."
      }
    },
    {
      "@type": "Question",
      "name": "Is Aulteus Logic a trading platform or broker?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "No. Aulteus Logic is not a trading platform, broker, execution venue, or intermediary. Aulteus Logic does not connect to brokerage accounts, does not execute transactions, and does not hold client funds. Users independently choose their own trading platforms or brokers if they decide to participate in markets."
      }
    },
    {
      "@type": "Question",
      "name": "Does Aulteus Logic use automated or algorithmic trading?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "No. Aulteus Logic does not trade on behalf of users and does not provide automated trading, discretionary trading, or account control. Any intelligence produced by Aulteus Logic is used at the discretion of the user as part of their own independent decision making process."
      }
    },
    {
      "@type": "Question",
      "name": "Does Aulteus Logic guarantee profits or outcomes?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "No. Aulteus Logic makes no guarantees regarding performance, profitability, accuracy, or outcomes. Capital markets involve risk and losses may occur. Past examples or illustrations are not indicative of future results."
      }
    },
    {
      "@type": "Question",
      "name": "Does Aulteus Logic tell users when not to trade?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Aulteus Logic may identify market conditions that are presented educationally as unclear, unstable, or high risk. In such cases, remaining neutral or taking no action may be highlighted as a valid educational outcome. This does not constitute advice or a recommendation and remains part of general decision education."
      }
    },
    {
      "@type": "Question",
      "name": "Who is responsible for decisions made using Aulteus Logic?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "The user is fully and solely responsible for all decisions made. Aulteus Logic does not accept responsibility for trades placed, losses incurred, or actions taken based on the use of its educational materials or tools. Users should seek independent advice from a suitably authorised professional if required."
      }
    },
    {
      "@type": "Question",
      "name": "Does Aulteus Logic fall within the FCA regulatory perimeter?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "No. Aulteus Logic is designed and operated to remain outside the FCA regulatory perimeter. The service does not involve advising on investments, dealing in investments, arranging transactions, portfolio management, or discretionary management."
      }
    },
    {
      "@type": "Question",
      "name": "Can Aulteus Logic be used with any trading platform?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Yes. Because Aulteus Logic is not a trading platform, it may be used alongside any broker or platform chosen independently by the user. Aulteus Logic does not integrate with, endorse, or monitor third party platforms."
      }
    },
    {
      "@type": "Question",
      "name": "Does Aulteus Logic hold or process client money?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "No. Aulteus Logic does not hold, receive, process, or control client funds or financial accounts. All financial transactions related to market participation are conducted independently by users through third party providers."
      }
    }
  ]
}
</script>
```

**Important:** If the FAQ answer copy on the page ever changes, this schema block must be updated to match exactly. Schema text that contradicts visible page text causes Google to disable the rich result.

---

## SECTION 4: New Files to Create

### 4.1 robots.txt (create at site root: `https://aulteuslogic.com/robots.txt`)

```
User-agent: *
Allow: /
Disallow: /api/

# Explicitly allow AI crawlers for AEO (Answer Engine Optimisation)
# This ensures ChatGPT, Perplexity, Claude, and Google AI can read and cite the site
User-agent: GPTBot
Allow: /

User-agent: Claude-Web
Allow: /

User-agent: Google-Extended
Allow: /

User-agent: PerplexityBot
Allow: /

User-agent: CCBot
Allow: /

User-agent: anthropic-ai
Allow: /

Sitemap: https://aulteuslogic.com/sitemap.xml
```

### 4.2 sitemap.xml (create at site root: `https://aulteuslogic.com/sitemap.xml`)

Update the `<lastmod>` date each time you make content changes.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://aulteuslogic.com/</loc>
    <lastmod>2026-06-24</lastmod>
    <changefreq>weekly</changefreq>
    <priority>1.0</priority>
  </url>
  <url>
    <loc>https://aulteuslogic.com/privacy-policy</loc>
    <lastmod>2026-06-24</lastmod>
    <changefreq>yearly</changefreq>
    <priority>0.3</priority>
  </url>
  <url>
    <loc>https://aulteuslogic.com/terms-of-service</loc>
    <lastmod>2026-06-24</lastmod>
    <changefreq>yearly</changefreq>
    <priority>0.3</priority>
  </url>
  <url>
    <loc>https://aulteuslogic.com/risk-disclosure</loc>
    <lastmod>2026-06-24</lastmod>
    <changefreq>yearly</changefreq>
    <priority>0.3</priority>
  </url>
</urlset>
```

### 4.3 llms.txt (create at site root: `https://aulteuslogic.com/llms.txt`)

This is an emerging standard (2025) that helps AI systems like ChatGPT, Perplexity, and Claude understand what a site is about and cite it accurately. Think of it as a robots.txt for AI understanding, not just crawling permission.

```
# Aulteus Logic
> A non linear decision asset framework for Forex, Gold, Oil and Indices traders.

Aulteus Logic is an institutional decision governance framework expressed through Agentic AI. It helps traders decide whether to act, remain neutral, or wait during uncertain market conditions.

## What Aulteus Logic Is
- A non linear decision framework for use alongside any trading platform
- An educational tool teaching institutional decision governance
- A bounded autonomous decision asset that governs judgement, not execution

## What Aulteus Logic Is Not
- Not a trading platform or broker
- Not financial advice or investment advice
- Not an algorithmic or automated trading system
- Not regulated by the Financial Conduct Authority
- Not a personal recommendation service

## Founder
Sam Onigbanjo, inventor of Aulteus Logic. Background in corporate strategy and capital markets.

## Contact
Email: Hello@aulteuslogic.com
Website: https://aulteuslogic.com

## Key Topics Covered
- Non linear decision intelligence
- Institutional trading methodology
- Forex decision framework
- Gold, Oil and Indices trading education
- Decision governance under uncertainty
- Market structure analysis
- Agentic AI for trading decisions
- Multi timeframe analysis
- Institutional volume and liquidity
- Volatility regime assessment
```

---

## SECTION 5: Link and Domain Fixes

### 5.1 Login button
Currently points to: `https://aureus-logic.vercel.app/login`
Fix: Move the production login to a branded subdomain. Create `app.aulteuslogic.com` and point the button there. A raw vercel.app URL in a finance product reads as unfinished to a cautious prospect.

### 5.2 Domain consolidation
There are currently two spellings in use: `aulteuslogic.com` (the main domain) and `aureuslogic.com` (appears in the footer's "Aulteus Logic Framework" link, which may be a typo).

Action: Confirm whether `aureuslogic.com` is intentionally a second domain or a typo. If a typo, fix the footer link. If it is a real second domain, set up a 301 permanent redirect from `aureuslogic.com` to `aulteuslogic.com` so all traffic and backlink authority flows to one address.

### 5.3 Dead footer links
Both of these point to `#` and need real destination pages before the media articles land:

- `The Banker's Code Bundle` (being renamed, see Section 1) should link to the product detail page or the pricing section anchor
- `War Room Access` should link to a War Room information page or the same pricing section

Placeholder `#` links on a finance site that is about to receive press attention will be clicked and will bounce. Fix them or remove them.

### 5.4 Image alt text
Confirm these two images have meaningful alt text in the code:
- Logo image: should have `alt="Aulteus Logic logo"`
- Founder photo: should have `alt="Sam Onigbanjo, Inventor of Aulteus Logic"`

---

## SECTION 6: After Deploy, Do These Immediately

- [ ] Go to Google Search Console (`search.google.com/search-console`), add and verify `aulteuslogic.com`, and submit the sitemap URL
- [ ] Go to Bing Webmaster Tools (`bing.com/webmasters`), verify the domain, and submit the sitemap URL
- [ ] Use Google's Rich Results Test (`search.google.com/test/rich-results`) on the live homepage URL to confirm all schema blocks are being read correctly
- [ ] Test the OG image at `opengraph.xyz` to confirm media article shares will preview correctly
- [ ] Check `robots.txt` is live at `aulteuslogic.com/robots.txt` and `sitemap.xml` is live at `aulteuslogic.com/sitemap.xml`

---

## Keyword Targets for Developer Reference

These are the search phrases the site should be optimised to appear in, listed in order of commercial priority. Use them in page copy, alt text, and any future content pages.

Primary: `forex decision framework`, `institutional trading methodology`, `non linear decision intelligence`, `decision governance trading`, `agentic AI forex`

Secondary: `how banks trade forex`, `institutional order flow trading`, `gold oil indices trading education`, `forex education framework`, `market structure trading course`

Long tail (high intent, low competition): `non linear decision framework forex`, `how to trade like banks`, `institutional trading decision tool`, `FCA compliant forex education UK`, `forex trading decision governance tool`

---

*File prepared by Claude, June 2026. All FAQ schema text pulled verbatim from the live aulteuslogic.com accordion content. Do not alter the schema text unless the visible page text is also changed at the same time.*
