# Marketing AI Agents (Unified)

**Your all-in-one marketing AI command center.** Executes expert workflows for SEO, CRO, copy, paid media, and go-to-market strategy.

## What this repo contains
- `ai-marketing-claude`: core marketing agent engine with command routing and 5 analysis subagents.
- `gtm-strategist-skills`: strategic GTM phase workflow with deep planning and execution templates.
- unified commands in `market/SKILL.md`: `/market seo`, `/market cro`, `/market copywriting`, `/market sea`, `/market strategy`, plus audit/copy/email/report flows.

## Agent specialties

### SEO expert (`/market seo`)
- technical health (site speed, indexing, schema)
- on-page keyword fit and content structure
- internal linking and topic cluster recommendations
- output: `SEO-AUDIT.md`

### CRO expert (`/market cro`)
- conversion path audit (entry > checkout/lead)
- CTA and friction analysis
- social proof, trust, urgency optimization
- A/B hypothesis and quick-win backlog
- output: `CRO-ANALYSIS.md`

### Copywriting expert (`/market copywriting`)
- headline/value proposition clarity
- narrative framework, message hierarchy
- rewrite examples and conversion-focused language
- output: `COPYWRITING-RECOMMENDATIONS.md`

### SEA expert (`/market sea`)
- paid search campaign structure and keyword strategy
- ad copy to landing page alignment
- budget pacing, bid strategy, and ROI tracking
- output: `PAID-SEARCH-PLAN.md`

### Strategy expert (`/market strategy`)
- GTM positioning and messaging stack
- channel mix and launch roadmaps
- growth loop and systemization guidance
- output: `MARKET-STRATEGY-ROADMAP.md`

## Quick start
1. Install: `./install.sh`
2. Run one of the main workflows:
   - `/market audit https://example.com`
   - `/market copy https://example.com`
   - `/market seo https://example.com`
   - `/market cro https://example.com`
   - `/market strategy "product details"`
3. Find outputs in `outputs/`.

## No collaborator names
This README intentionally avoids referencing individuals or legacy collaborator credits. It is focused on tools, value, and direct usage.

## License
MIT
## Platform support

This repo works across multiple AI platforms:

- **Claude (Code/Cowork/AI)**: primary tested mode with direct skill folder injection.
- **ChatGPT (OpenAI Plus or enterprise)**: use via the OpenAI API + local harness or prompt engineering adapters.

### Install directions

#### Claude mode
1. Run `./install.sh` in this repo.
2. Launch Claude Code or Cowork with this folder as workspace.
3. Use commands: `/market seo`, `/market cro`, `/market copywriting`, etc.

#### ChatGPT mode
1. Install a local CLI wrapper such as `gpt-engineer`, `langchain` script, or your own prompt orchestrator.
2. Load the SKILL.md files as context into the model prompt chain.
3. Dispatch commands from your wrapper in the same syntax:
   - `market seo https://example.com`
   - `market cro https://example.com`
   - `market strategy "product details"`
4. Persist outputs to files under `outputs/`.

## Why this is useful

- Reuses the same workflow logic from both repos in a single workspace.
- Runs in Claude natively plus portable to ChatGPT + tooling layer.
- Supports audit + execution outputs ready for client reports.
