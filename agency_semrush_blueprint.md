# Chinese SEO Knowledge Authority - Website Structural Blueprint

This document serves as the complete architectural, design, and content reference for building the Chinese-first SEO/GEO/AEO Authority Knowledge Hub. It documents the layout patterns, design system, directory logic, and editorial rules used across the platform.

---

## 1. SITE ARCHITECTURE

The website follows a clear hierarchy designed for an educational encyclopedia, data-driven ranking platform, and SEO research database.

**Home** (`index.html`)
 ├ **术语百科 (Definitions & Fundamentals)**
 │ ├ 什么是 SEO (`what-is-seo.html`)
 │ ├ 什么是 GEO (`what-is-geo.html`)
 │ ├ 什么是 AEO (`what-is-aeo.html`)
 │ └ 本地 SEO 指南 (`local-seo-malaysia.html`)
 ├ **搜商智库 (Knowledge Base & Guides)** 
 │ ├ Articles Hub (`articles.html`)
 │ ├ AI Search Hub (`ai-search-guide.html`)
 │ ├ Article: SEO Foundation (`articles/seo-keyword-research.html`)
 │ ├ Article: Tech SEO (`articles/technical-seo-guide.html`)
 │ ├ Article: Link Building (`articles/link-building-guide.html`)
 │ ├ Guide: ChatGPT SEO (`chatgpt-seo-guide.html`)
 │ ├ Guide: Google AI Overviews (`google-ai-overviews-seo.html`)
 │ ├ Guide: GEO Ranking (`geo-ranking-guide.html`)
 │ └ Guide: AEO Ranking (`aeo-ranking-guide.html`)
 ├ **行业指南 (Industry SEO Guides)**
 │ ├ E-commerce SEO (`ecommerce-seo-guide.html`)
 │ ├ B2B SEO (`b2b-seo-guide.html`)
 │ ├ Real Estate SEO (`real-estate-seo-guide.html`)
 │ └ Medical SEO (`medical-seo-guide.html`)
 ├ **机构排行榜 (Directory & Rankings)** 
 │ ├ SEO 公司排行榜平台 (`agencies.html`)
 │ ├ Global Rankings
 │ │ ├ `global-seo-agencies.html`
 │ │ ├ `global-geo-experts.html`
 │ │ ├ `global-aeo-companies.html`
 │ │ └ `ai-seo-companies.html`
 │ └ Malaysia Rankings
 │   ├ `malaysia-seo-experts.html`
 │   ├ `malaysia-seo-agencies.html`
 │   ├ `malaysia-geo-experts.html`
 │   └ `malaysia-google-ranking-experts.html`
 ├ **Programmatic Directories (Local/Industry Intersections)**
 │ ├ `/[region]-[industry]-seo-agencies.html` (e.g., `malaysia-ecommerce-seo-agencies.html`)
 │ └ `/[region]-[service]-experts.html` (e.g., `us-geo-experts.html`)
 └ **平台信托 (Platform Trust Pages)**
   ├ 排名机制 (`ranking-methodology.html`)
   ├ 关于平台 (`about-platform.html`)
   └ 提交机构 (`submit-agency.html`)

---

## 2. REVISED NAVIGATION LABELS (CHINESE-FIRST)

- **SEO 基础** (SEO Fundamentals)
- **术语百科** (Definitions & Glossary)
- **搜索原理** (Search Principles & AI Search)
- **行业指南** (Industry Guides)
- **机构排行榜** (Agency Rankings)
- **阅读指南 / 探索排行榜** (Primary CTAs - Informational)

---

## 3. PAGE TYPES

The website utilizes reusable page templates strictly focused on education and neutral data.

### A. Directory Hub / Homepage Template (`index.html`)
- **Purpose:** Primary hub establishing the platform as an authority encyclopedia and ranking index.
- **Structure:** Hero Section (Search & Data focus) -> SEO/GEO/AEO Definition Blocks -> AI Search Section -> Global Rankings Preview -> Malaysia Rankings Preview -> Industry SEO Guides -> Knowledge Hub Articles -> Neutral Footer.

### B. Definition Template (`what-is-*.html`)
- **Purpose:** Deep-dive educational pages explaining specific concepts.
- **Structure:** Split Hero with visual -> Definition -> Explanation -> Example -> Comparison -> Checklist -> FAQ -> Footer. (Strictly no sales pitches or value propositions).

### C. Article Hub Page (`articles.html`)
- **Purpose:** Central repository for all educational blog posts.
- **Structure:** Minimal Hero Header -> 4-Column Responsive Grid containing Article Cards  -> CTAs: "阅读指南" -> Footer.

### D. Knowledge Article / Guide Page (`*-guide.html`)
- **Purpose:** Long-form content consumption.
- **Structure:** Minimal Header taking up max-w-3xl -> Pill Tags & Reading Time -> H1 Title -> Author Meta -> Hero Image -> `.prose` Container (Rich Text) -> Bottom CTA Banner (Download Research Report / View Rankings) -> Footer.

### E. Ranking Directory Page (`agencies.html` & Programmatic variants)
- **Purpose:** A neutral ranking database allowing users to filter and find providers.
- **Structure:** Centered Hero -> Multi-select Search & Filter Bar -> Results Grid (Agency Cards) -> Pagination -> CTA: "提交机构" -> Footer.

### F. Platform Trust Pages
- **Purpose:** Establish E-E-A-T.
- **Structure:** Text-heavy, transparent methodology explanations, origin of data, and submission forms.

---

## 4. DIRECTORY SYSTEM DESIGN

Acts strictly as an **SEO 公司排行榜平台**.

- **No hiring CTAs allowed.** Buttons must read: "Visit Website", "Read Full Review".
- **Call to Action for Agencies:** "Submit Your Agency".
- **Filtering System:**
  - Search Input (Text)
  - Country Dropdown (MY, SG, CN, US)
  - Industry Dropdown (Ecom, SaaS, Finance, Medical, Real Estate)
  - Service Dropdown (SEO, Content, Link, AEO, GEO)
- **Data Model per Agency:** 
  - `Name`: Agency Name
  - `Rating`: 5-Star Rating
  - `Authority Score`: Platform-specific metric out of 100
  - `Tags`: 3 Core Tags
  - `Description`: Truncated to 3 lines
  - `Country`: Region focus
  - `Industry`: Vertical focus

---

## 5. PROGRAMMATIC SEO SYSTEM

Scalable structure designed to capture long-tail semantic searches without manual page creation.

- **Generation Rules:** Data from the directory backend populates templated ranking pages.
- **Pattern 1:** `/[region]-[industry]-seo-agencies`
  - *Example:* `/malaysia-ecommerce-seo-agencies`
  - *Content:* "Top E-commerce SEO Agencies in Malaysia", filtered list of agencies matching Region=Malaysia, Industry=Ecommerce.
- **Pattern 2:** `/[region]-[service]-experts`
  - *Example:* `/global-b2b-seo-agencies`, `/us-geo-experts`
  - *Content:* Filtered lists with authoritative descriptions of the service in that region, linking back to core Definitions (`what-is-geo.html`).
- **Internal Linking:** Programmatic pages link to the methodology page, related industry guides, and parent regional hubs.

---

## 6. INTERNAL LINKING ENGINE

A rigid, automated contextual linking system.

- **Automatic Keyword Linking Rules:**
  - Whenever `SEO` appears, link first instance to `what-is-seo.html`.
  - Whenever `GEO` appears, link first instance to `what-is-geo.html`.
  - Whenever `AEO` appears, link first instance to `what-is-aeo.html`.
  - Whenever `AI 搜索` or `AI Search` appears, link to `ai-search-guide.html`.
- **Hub-and-Spoke Mapping:**
  - `articles.html` acts as the master hub.
  - Definition pages (`what-is-*.html`) act as topic cluster centers. All child articles (e.g., `technical-seo.html`) must link back to their parent definition.
  - Articles link contextually to Ranking Pages when referencing "finding partners" or "industry standards."

---

## 7. CONTENT POSITIONING

- **Rule:** Every page must follow an educational flow: `Definition -> Explanation -> Example -> Comparison -> Checklist -> FAQ`.
- **Prohibited:** Sales pitches, "Why choose us", "Our Value Proposition", conversion funnels leading to a service cart.

---

## 8. DESIGN SYSTEM CONSISTENCY

- **Typography:** `Montserrat` (or similar geometric sans). Primary language is Chinese, so a highly legible Chinese web font stack (`PingFang SC`, `Microsoft YaHei`) takes precedence.
- **Color System:** Metric UI (SEMrush-inspired). Primary: Coral Orange (`#ff642d`), Secondary: Vibrant Green (`#00ce7d`), Text: Charcoal (`#1c1c1c`).
- **Component System:** No legacy agency styles. CTA banners must be strictly informational (`bg-brand-gray` or light semantic colors) promoting downloads or directory exploration, not commercial consultation requests.
