# Changelog

## [1.0.0] — 2026-05-18

First stable release. Framework + AI tooling cho travel growth marketing tại Việt Nam.

### Added
- **01 — User Segmentation**: 4-segment framework (Connection Seeker, Relaxation Seeker, Family Traveler, Explorer) với behavioral profile, frustration points, và retention levers cho mỗi segment
- **02 — Journey Map**: 6-stage multi-modal journey (Inspire → Search → Plan → Book → Post-book → Post-trip) với cross-vertical opportunity mapping
- **03 — Promotion**: 5-type promotion framework (ATL, BTL, Partnership, Gamification, Loyalty) + budget allocation matrix + vertical-specific mechanics
- **04 — Seasonal Calendar**: Vietnam annual demand calendar với 4 phases, monthly budget split, và timing cho từng vertical
- **05 — Retention**: 90-day booking-1-to-booking-2 playbook với 4-phase execution + segment-specific approaches
- **06 — Partner Co-marketing**: 4-question partnership evaluation framework + partner-type-specific mechanics (airline, bus, hotel, experience)
- **07 — AI Prompts**: Thư viện prompt AI cho travel growth (segment, campaign, retention, partner, seasonal)

### Infrastructure
- `CLAUDE.md` — Context file cho Claude Code, hỗ trợ `/segment`, `/journey`, `/promotion`, `/seasonal`, `/retention`, `/partner`, `/prompts`
- `SKILL.md` — Skill definitions cho từng module (tương thích Claude Code, Codex, Cursor)
- `.claude/skills/` — Symlink directory cho Claude Code auto-discovery
- `BENCHMARKS.md` — Industry benchmarks: retention rates, CAC estimates, promotion performance, Vietnam seasonal demand index, conversion funnel
- `CHANGELOG.md` — Version tracking (file này)

### Tools
- [Campaign Brief Generator](https://thaolst.github.io/travel-ai-tools/campaign-brief-generator.html) — AI tool chạy trên framework module 01-04
- [Retention Cohort Diagnose](https://thaolst.github.io/travel-ai-tools/retention-diagnose.html) — AI tool chạy trên framework module 05

### Known limitations
- Benchmarks là ước tính từ công bố công khai + kinh nghiệm thực chiến, cần calibrate theo platform cụ thể
- Framework focus vào B2C travel booking, chưa cover B2B travel hoặc corporate travel
- AI prompts chưa được systematic eval (dùng heuristic quality check)
