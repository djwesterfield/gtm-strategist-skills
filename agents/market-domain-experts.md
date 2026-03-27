# Market Domain Experts (Merged ai-marketing-claude + gtm-strategist-skills)

This guide creates one expert role per core marketing domain by reusing and unifying the existing ai-marketing-claude subagents and GTM Strategist skill phases.

## Purpose
- Give users a clear, single entrypoint for SEO, CRO, Copywriting, SEA, Strategy, and Growth.
- Keep existing `/market` commands working and add explicit domain expert naming.
- Leverage the proven workflows from both repositories.

## Expert Roles

### SEO Expert (market-seo)
- Base: `ai-marketing-claude/agents/market-technical.md` + GTM `running-marketing` SEO channel tasks.
- Focus: on-page SEO audit, technical crawl health, content topic mapping, keyword funnel fit, schema markup, internal linking, page speed.
- Output: `SEO-AUDIT.md` + prioritized tech/content roadmap.

### CRO Expert (market-cro)
- Base: `ai-marketing-claude/agents/market-conversion.md` + GTM funnel + customer journey optimization from `gtm-foundations` and `building-communication-engine`.
- Focus: conversion path leak analysis, CTA optimization, trust signals, social proof, friction removal, A/B test hypothesis generation.
- Output: `CRO-ANALYSIS.md` + action plan + test backlog.

### Copywriting Expert (market-copywriting)
- Base: `ai-marketing-claude/agents/market-content.md` + GTM `crafting-positioning` and `running-marketing` content strategy.
- Focus: value proposition clarity, persuasive messaging, narrative consistency, headlines, content pillar frameworks, before/after rewrites.
- Output: `COPYWRITING-RECOMMENDATIONS.md` + top 5 rewrite examples.

### SEA / Paid Ads Expert (market-sea)
- Base: `ai-marketing-claude/skills/market-ads/SKILL.md` + GTM funnels and channel strategy actions.
- Focus: paid search structure (Google Ads, Microsoft Ads), keyword match types, ad copy testing, landing page relevance, budget pacing.
- Output: `PAID-SEARCH-PLAN.md` + campaign structure table.

### Strategy Expert (market-strategy)
- Base: `ai-marketing-claude/agents/market-strategy.md` + GTM foundations, positioning, and launch planning phases.
- Focus: GTM narrative, quadrant planning, differentiator architecture, go-to-market channel mix, growth loops.
- Output: `MARKET-STRATEGY-ROADMAP.md`.

## Runtime behavior
- `/market seo <url>` uses the SEO expert workflow and writes `SEO-AUDIT.md`.
- `/market cro <url>` uses CRO expert workflow and writes `CRO-ANALYSIS.md`.
- `/market copy <url>` remains powered by copywriting expert workflow.
- `/market sea <goal>` enters the paid media expert path.
- `/market strategy <context>` fuses market strategy + GTM strategic narrative.

## Integration guidance
- Keep existing `market/*` skills as the implementation foundation.
- Use GTM `my-gtm-context.md` and `outputs/` from `gtm-strategist-skills` as optional input sources when present.
- Add the new agent names to command reference and documentation in `market/SKILL.md`.
