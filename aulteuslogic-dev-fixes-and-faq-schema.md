# Aulteus Logic, Developer Fix List and FAQ Schema

Hand this whole file to the developer. Section 1 is the tick list. Section 2 is ready to paste code for the FAQ schema markup.

## 1. Developer Tick List

### Remove "The Banker's Code" everywhere
This phrase already belongs to an unrelated, well known wealth building book, and it is competing with that book instead of building our own name. Every instance below needs to come out or be replaced with our own language (suggest leaning on "Aulteus Logic," "the Logic Engine," or "Decision Governance" instead).

- [ ] Page `<title>` tag: currently "Non Linear Decision Intelligence | Aulteus Logic & The Banker's Code". Remove the "& The Banker's Code" part.
- [ ] Hero subtext: "We teach you the 'Banker's Code', the exact framework used by the top 1% to dominate Forex, Gold, Oil and Indices." Rewrite without the phrase.
- [ ] Pricing card name: "The Banker's Code Bundle" (the Complete Mentorship tier). Rename.
- [ ] Pricing card bullet: "Full Education (How Banks Trade)" can stay if you want, just confirm it does not reintroduce the phrase.
- [ ] Market Reality section bullet: "How structure is read (The Banker's Way)". Rewrite.
- [ ] Founder bio line: "Creator of 'The Banker's Code'" under Sam Onigbanjo's name. Remove or replace.
- [ ] Footer, Product column: "The Banker's Code Bundle" link. Rename and point to a real page (see next item).
- [ ] Search the full codebase and CMS for the literal string "Banker's Code" to catch anything missed above, including image alt text and meta tags.

### Fix broken and misrouted links
- [ ] Login button currently points to `https://aureus-logic.vercel.app/login`. Stop pointing the production site at a raw Vercel preview URL. Point it to a branded subdomain instead, for example `app.aulteuslogic.com/login`, once that subdomain is set up.
- [ ] Footer link "Aulteus Logic Framework" currently points to `https://aureuslogic.com/` (no hyphen, different spelling from the main domain `aulteuslogic.com`). Confirm whether this is a typo or a real second domain. If it is a typo, fix it to point at the correct domain. If it is real, 301 redirect it into the main domain so we are not splitting authority across two spellings.
- [ ] Footer link "The Banker's Code Bundle" points to `#` (dead link). Either build the page it should point to, or remove the link until it exists.
- [ ] Footer link "War Room Access" points to `#` (dead link). Same as above.
- [ ] Pick ONE canonical domain (recommend `aulteuslogic.com`, since it is the one being marketed) and 301 redirect every variant (`aureuslogic.com`, the vercel.app login domain once moved, www vs non-www) into it.

### Technical SEO basics, currently missing
- [ ] `robots.txt` returns empty. Add one that allows crawling and points to the sitemap.
- [ ] `sitemap.xml` returns empty. Generate one listing the homepage, privacy policy, terms of service, and risk disclosure pages at minimum.
- [ ] Submit the sitemap to Google Search Console and Bing Webmaster Tools once it exists.
- [ ] Add a self referencing canonical tag (`<link rel="canonical">`) to every page, pointing at the chosen canonical domain.
- [ ] Add Organization schema (JSON-LD) for Aulteus Logic and Person schema for Sam Onigbanjo, separate from the FAQ schema below.
- [ ] Audit image alt text site wide, particularly the logo and the founder photo.

## 2. FAQ Schema Markup

This is built from the real, live answer text on the Regulatory and Compliance FAQ section (pulled directly from the accordion, not rewritten). Paste this entire block inside the `<head>` of the homepage, or wherever the FAQ section is rendered. This single addition is the highest leverage SEO and AEO fix available right now: it lets Google's AI Overviews and ChatGPT search pull these answers directly and cite Aulteus Logic as the source.

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

Note for the developer: if the FAQ answer copy ever changes on the page, this JSON-LD block must be updated to match exactly. Schema text that contradicts visible page text can get the rich result disabled or, worse, flagged.
