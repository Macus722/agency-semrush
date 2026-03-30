# Agency Ahrefs - Website Structural Blueprint

This document serves as the complete architectural, design, and content reference for rebuilding the Agency Ahrefs website. It documents the layout patterns, design system, directory logic, and editorial rules used across the platform.

---

## 1. SITE ARCHITECTURE

The website follows a clear hierarchy designed for SEO, educational content, and directory mapping.

**Home** ([index.html](file:///c:/Users/desmo/Herd/landing_page/index.html))
 ├ **Solutions** (Service & Definition Pages)
 │ ├ 什么是 SEO ([seo-services.html](file:///c:/Users/desmo/Herd/landing_page/solutions/seo-services.html))
 │ ├ 什么是 GEO (`geo-services.html`)
 │ ├ 什么是 AEO (`aeo-services.html`)
 │ └ 本地 SEO 指南 ([local-seo-malaysia.html](file:///c:/Users/desmo/Herd/landing_page/local-seo-malaysia.html))
 ├ **Knowledge Base** 
 │ ├ Articles Hub ([articles.html](file:///c:/Users/desmo/Herd/landing_page/articles.html))
 │ ├ Article: SEO Foundation ([seo-keyword-research.html](file:///c:/Users/desmo/Herd/landing_page/articles/seo-keyword-research.html), etc.)
 │ ├ Article: Tech SEO ([technical-seo-guide.html](file:///c:/Users/desmo/Herd/landing_page/articles/technical-seo-guide.html))
 │ ├ Article: Link Building ([link-building-guide.html](file:///c:/Users/desmo/Herd/landing_page/articles/link-building-guide.html))
 │ └ *(9 core articles in total)*
 ├ **Directory** 
 │ └ SEO 数据平台 ([agencies.html](file:///c:/Users/desmo/Herd/landing_page/agencies.html))
 ├ **Programmatic Directories (Local/Industry Intersections)**
 │ ├ `/knowledge/` (e.g., `全球-医疗-seo-agencies.html`)
 │ └ `/industries/` (e.g., `b2b.html`, `ecommerce.html`)
 └ **Resources & Case Studies**
   ├ 行业研究 (`case-studies.html`)
   ├ AI Search Optimization (`ai-search-optimization.html`)
   └ SEO vs GEO vs AEO (`seo-vs-geo-vs-aeo.html`)

---

## 2. PAGE TYPES

The website utilizes 5 distinct, highly reusable page templates.

### A. Homepage Template (`index.html`)
- **Purpose:** Primary marketing landing page, establishing authority and directing users to key funnels.
- **Structure:** Split-screen Hero &#8594; Client Logos &#8594; Service/Framework Grid &#8594; Case Studies Grid &#8594; Articles Hub Preview &#8594; Footer.

### B. Service / Solution Page (`seo-services.html`)
- **Purpose:** Deep-dive educational and sales pages explaining specific offerings (SEO, GEO, AEO).
- **Structure:** Split Hero with visual &#8594; "Why it matters" intro &#8594; 3 Pillars (Grid) &#8594; 4-Step Framework (List) &#8594; Comparison Table &#8594; Value Proposition &#8594; Checklist &#8594; Mid-page CTA &#8594; FAQ Accordion &#8594; Footer.

### C. Article Hub Page (`articles.html`)
- **Purpose:** Central repository for all educational blog posts.
- **Structure:** Minimal Hero Header &#8594; 4-Column Responsive Grid containing Article Cards  &#8594; Footer.

### D. Knowledge Article Page (`articles/*.html`)
- **Purpose:** Long-form content consumption optimized for reading experience and SEO ranking.
- **Structure:** Minimal Header taking up max-w-3xl &#8594; Pill Tags & Reading Time &#8594; H1 Title &#8594; Author Meta &#8594; Hero Image &#8594; `.prose` Container (Rich Text) &#8594; Bottom CTA Banner &#8594; Footer.

### E. Directory Page (`agencies.html`)
- **Purpose:** A functional database UI allowing users to filter and find SEO agencies.
- **Structure:** Centered Hero &#8594; Multi-select Search & Filter Bar &#8594; Results Grid (Agency Cards) &#8594; Pagination &#8594; Footer.

---

## 3. LAYOUT STRUCTURE

### Global Elements
- **Navigation:** Fixed, glassmorphism (`bg-white/95 backdrop-blur-md`), with a logo on the left and links/CTA on the right. Includes a mobile hamburger menu that toggles a sliding panel.
- **Footer:** Dark (`bg-brand-navy`), 4-column layout containing Logo/Bio, Solutions Links, Resources Links, and bottom copyright/contact info.

### Article Page Layout Example
1. **Article Meta:** Top tags (`bg-brand-blue/10 text-brand-blue`) and reading time.
2. **Hero:** `H1` title (3xl/4xl) + Author/Date + Full-width Hero Image (`rounded-2xl`).
3. **Content Body (`.prose`):** `H2` sections, `H3` sub-sections, unordered lists, and data tables.
4. **Bottom CTA:** A uniquely styled colored box (`bg-orange-50 border-brand-orange/20`) capturing leads after they finish reading.

---

## 4. DESIGN SYSTEM

### Typography
- **Primary Font:** `Inter`, falling back to `system-ui`, `sans-serif`.
- **Headings:** Bold (`font-extrabold` for H1/H2, `font-bold` for H3), tightly tracked (`tracking-tight`), colored in `brand-navy`.
- **Body Text:** `text-sm` or `text-base`, colored in `brand-gray` or `brand-navy/70`, loose line-height (`leading-relaxed`).

### Color System
- **Primary / Accent (Orange):** `#ff8000` — Used for primary CTAs, active states, and highlights.
- **Secondary Accent (Blue):** `#1462ff` — Used for secondary links, hover states, and tech-focused badges.
- **Text & Dark Backgrounds (Navy):** `#012f56` — Used for all headings, default text, and the Footer background.
- **Secondary Text (Gray):** `#5e617d` — Used for paragraphs, metadata, and borders.
- **Background (Light):** `#f8fafc` — Used for alternating section backgrounds and subtle card fills.

### Component Styling
- **Buttons (CTAs):** Fully rounded (`rounded-full`), padded (`px-8 py-3`), with slight shadow and transform interactions (`hover:-translate-y-0.5`).
- **Cards:** `bg-white`, `rounded-2xl`, subtle borders (`border-gray-200`), with `hover:shadow-xl` and `hover:border-brand-blue` transitions.
- **Spacing:** Extensive use of vertical whitespace (`py-24`, `pt-32`) to create a premium, uncrowded feel. Max width for readablity is strictly controlled (`max-w-6xl` for grids, `max-w-3xl` for articles).

---

## 5. CONTENT STRUCTURE RULES

- **Paragraph Length:** Short, punchy paragraphs (rarely exceeding 3-4 lines) to accommodate mobile readers.
- **Scannability:** Heavy reliance on bullet points (`<ul>` with custom colored bullets like `<span class="text-brand-orange">•</span>`) instead of comma-separated lists.
- **Heading Hierarchy:** Strict usage of `H1` (once per page) -> `H2` (main sections) -> `H3` (subsections).
- **Data Visualization:** Tabular data is wrapped in `overflow-x-auto` to prevent mobile breaking, with branded header rows (Navy background, white text in articles; transparent in service pages).
- **Voice & Tone:** Professional, data-driven, authoritative, yet accessible. Avoids fluff.

---

## 6. INTERNAL LINKING STRUCTURE

- **Topic Clusters:** Content is heavily clustered around "SEO", "GEO" (Generative Engine Optimization), and "AEO" (Answer Engine Optimization).
- **Contextual Linking:** Whenever "GEO", "AEO", or "SEO" is mentioned in a paragraph, it is often hyperlinked to its respective Service Definition page (`/solutions/...`).
- **Hub-and-Spoke:** `articles.html` acts as the hub. Individual articles link back to the hub or to the `agencies.html` directory via the bottom CTA.
- **Directory Spidering:** Programmatic pages in `/knowledge/` (e.g. Local + Industry combinations) are designed to capture long-tail search traffic and internally link back to the main `agencies.html` directory.

---

## 7. CONTENT CATEGORIES

The site's taxonomy revolves around the evolution of Search:
1. **Traditional SEO:** Tech, On-Page, Link Building, Keyword Research, Local SEO.
2. **AI Search (GEO & AEO):** Strategies for ranking in ChatGPT, Gemini, and Google AI Overviews.
3. **Industry Specifics:** SEO strategies tailored for E-commerce, Real Estate, Medical, B2B SaaS, and F&B.
4. **Geography / Local:** SEO data specific to Malaysia, Singapore, China/Taiwan/HK, and Global/US.

---

## 8. DIRECTORY SYSTEM (`agencies.html`)

The directory acts as a tool for users to find service providers.
- **Filtering System:**
  - Search Input (Text)
  - Country Dropdown (MY, SG, CN, US)
  - Industry Dropdown (Ecom, SaaS, Finance, Medical, Real Estate)
  - Service Dropdown (Tech, Content, Link, AEO, GEO)
- **Ranking Logic:** Displayed via a "综合机构指数" (Comprehensive Agency Index) out of 10.0, backed up by a 5-star rating system (e.g., ⭐ 5.0).
- **Data Model per Agency:** 
  - Logo `img`
  - Rating
  - Name
  - Execution Scope (e.g., Global, Local)
  - Description (truncated to 3 lines)
  - 3 Core Tags (e.g., AEO, AI 概览, 分发生态)
  - Index Score

---

## 9. COMPONENT LIBRARY

When rebuilding, developers should create the following reusable components:
1. `Navbar` (Glassmorphism, sticky over hero, responsive sliding menu)
2. `Footer` (Dark mode grid)
3. `HeroSplit` (H1 left, Image/Graphic right with absolute positioned badges)
4. `ArticleCard` (Tag, H3, description snippet, "Read more" link arrow)
5. `AgencyCard` (Logo, Title, Tags, Rating, Index Score footer)
6. `ComparisonTable` (Responsive table with branded table headers)
7. `FaqAccordion` (Toggleable answers via JS/CSS)
8. `CtaBanner` (Rounded colored box for mid-page or end-page conversion)
9. `PillTag` (Small rounded badges for categories/industries)

---

## 10. FINAL WEBSITE BLUEPRINT SUMMARY

- **Total Unique Templates:** 5 Core Templates + Programmatic variants.
- **Design System:** Inter font, Orange/Blue/Navy palette, heavily rounded corners, generous padding (`py-24`), card-based grid layouts.
- **Content Architecture:** A highly interlocking ecosystem of Educational Articles &#8594; Service Explanations &#8594; Agency Directory.
- **Result:** A cohesive, premium, and lightning-fast static site architecture beautifully optimized for modern SEO and AI-Search discovery. This reference allows any front-end framework (React, Vue, Astro) or CMS layer to safely adapt and rebuild the entire visual front without losing structural integrity.
