# Autonomous AI Tools Site

A Next.js site that operates itself, generating and maintaining SEO pages for AI tools autonomously.

## Features

- **60 AI tools** across 12 categories, all with detailed reviews
- **Programmatic SEO** with 78 static pages pre-rendered
- **Mega footer** with comprehensive internal linking for SEO
- **Dark mode** editorial design with Instrument Serif + DM Sans
- **Full SEO optimization** (meta tags, JSON-LD, OpenGraph, sitemap)
- **Autonomous content engine** (ready for OpenClaw integration)

## Tech Stack

- Next.js 15 with App Router
- TypeScript
- Tailwind CSS
- Static generation for maximum SEO
- JSON data store

## Project Structure

```
├── app/                    # Next.js app directory
│   ├── page.tsx           # Homepage
│   ├── tools/[slug]/      # Dynamic tool pages
│   ├── categories/[category]/  # Category listing pages
│   ├── sitemap.ts         # Dynamic sitemap
│   └── robots.ts          # Robots.txt
├── components/            # React components
│   ├── Header.tsx
│   └── Footer.tsx         # Mega footer with SEO links
├── lib/                   # Utilities
│   ├── tools-data.ts      # Data access functions
│   └── content-engine.ts  # AI content generation (stub)
├── data/                  # JSON data store
│   ├── tools.json         # 60 tool entries
│   └── categories.json    # 12 categories
└── scripts/               # Autonomous operations
    └── cron-orchestrator.ts  # Daily content generation

```

## Local Development

```bash
npm install
npm run dev
```

Open [http://localhost:3000](http://localhost:3000)

## Build

```bash
npm run build
npm start
```

## Deploy to Vercel

1. Push to GitHub
2. Import project in Vercel
3. Set environment variables:
   - `SITE_URL` - Your production domain
   - `DEPLOY_HOOK_URL` - Vercel deploy hook (optional, for autonomous rebuilds)
4. Deploy

## Autonomous Operation

The site is designed to operate autonomously via OpenClaw cron:

1. **Daily**: `scripts/cron-orchestrator.ts` discovers new AI tools
2. **Generates** detailed entries using Claude
3. **Commits** to git
4. **Triggers** Vercel rebuild

### Setting up OpenClaw Cron

```bash
# Run the orchestrator manually
npm run generate

# Or set up daily cron via OpenClaw
# (See scripts/cron-orchestrator.ts for details)
```

## Content Structure

Each tool entry includes:
- Full SEO metadata (title, description, OpenGraph)
- JSON-LD structured data (SoftwareApplication schema)
- Detailed review (description, features, pros/cons, pricing)
- Related tools for internal linking

## SEO Strategy

- **Mega footer**: All categories + top tools linked from every page
- **Internal linking**: Related tools on each page
- **Static generation**: All pages pre-rendered as HTML
- **Structured data**: JSON-LD on every tool page
- **Comprehensive sitemap**: Auto-generated from data

## Stats

- **60** AI tools reviewed
- **12** categories
- **78** static pages generated
- **90+** Lighthouse score target

---

Built with autonomy in mind.
