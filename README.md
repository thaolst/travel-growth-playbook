# Travel Growth Playbook

Growth marketing trong travel có những đặc thù mà framework từ e-commerce hay SaaS không cover được.

User book 2-4 lần mỗi năm. Không có habit tự nhiên. CAC cao. Retention phải được thiết kế riêng. Và cùng một chuyến đi nhưng mỗi người đi vì lý do hoàn toàn khác nhau — điều đó ảnh hưởng đến mọi thứ từ message đến promotion mechanic.

Repo này là tập hợp framework thực chiến cho growth marketing trong travel vertical, covering airline, bus, train, và hotel.

![Version](https://img.shields.io/github/v/release/thaolst/travel-growth-playbook?color=orange&label=version)
![Last Commit](https://img.shields.io/github/last-commit/thaolst/travel-growth-playbook?color=orange)
![License](https://img.shields.io/github/license/thaolst/travel-growth-playbook)
![Stars](https://img.shields.io/github/stars/thaolst/travel-growth-playbook?style=social)
![Language](https://img.shields.io/badge/language-VI%20%2B%20EN-blue)
![Free](https://img.shields.io/badge/free-forever-brightgreen)
![Domain](https://img.shields.io/badge/domain-travel%20%C3%97%20growth%20%C3%97%20AI-orange)

📖 [Benchmarks & Industry Data](./BENCHMARKS.md) · 📋 [Changelog](./CHANGELOG.md) · 🔗 [AI Tools](https://github.com/thaolst/travel-ai-tools)

## AI Tools — Dùng thử ngay

Framework trong repo này đã được đưa vào hai công cụ AI miễn phí. Không cần đọc hết tài liệu — dùng thẳng.

| Tool | Làm gì |
|---|---|
| [Campaign Brief Generator](https://thaolst.github.io/travel-ai-tools/campaign-brief-generator.html) | Chọn segment + vertical + mùa + goal → Full brief trong 2 phút |
| [Retention Cohort Diagnose](https://thaolst.github.io/travel-ai-tools/retention-diagnose.html) | Mô tả cohort → Risk level + root cause + 90-day playbook |

Cần Anthropic API key. Không lưu data. Chạy hoàn toàn trong browser. Không có API key thì dùng prompt chain backup có sẵn trong mỗi tool.

## Benchmarks & Industry Data

Xem số liệu tham khảo tại **[BENCHMARKS.md](./BENCHMARKS.md)** — retention rate, CAC ước tính, promotion performance, seasonal demand index, conversion funnel benchmarks.

Trích nhanh:

| Metric | Travel VN (ước tính) | Global Travel |
|---|---|---|
| Repeat booking rate (6mo) | 15-25% | 20-30% |
| Single-booking user ratio | 55-70% | 50-60% |
| Drop-off booking 1 → 2 | 60-75% | 50-65% |
| Avg bookings/user/year | 2-3 | 2.5-4 |

> Dùng các số này làm baseline để calibrate, không phải truth tuyệt đối. Số thực tế phụ thuộc vào platform, segment, và thị trường cụ thể.

## Mục lục & Nội dung

Mỗi folder là một module độc lập. Click để xem preview nội dung bên trong.

<details>
<summary><b>📁 01 — User Segmentation</b> — Segment travel user theo motivation, không phải demographics</summary>

**File chính:** [`01-user-segmentation/travel-segment-framework.md`](./01-user-segmentation/travel-segment-framework.md)

**4 segment thực sự có ý nghĩa trong travel:**

| Segment | Motivation | Frustration | Retention lever |
|---|---|---|---|
| 🤝 Connection Seeker | Đi để kết nối (với người) | UX phức tạp, service sau booking tệ | Social trigger, companion offer |
| 🌿 Relaxation Seeker | Đi để reset, plan kỹ | Thiếu thông tin, ảnh không đúng reality | Upgrade mechanic, loyalty tier |
| 👨‍👩‍👧‍👦 Family Traveler | Đi để cả nhà có kỷ niệm | Không có option cho trẻ em, multi-app hassles | Bundle, referral, seasonal timing |
| 🗺️ Explorer | Đi để trải nghiệm mới | Budget limit, không có discovery feature | Gamification, exclusive inventory |

**AI Prompt có sẵn:** Classify user vào segment → đề xuất retention mechanic.

**Dùng Claude Code:** `/segment`
</details>

<details>
<summary><b>📁 02 — Journey Map</b> — Multi-modal journey map — airline, bus, train, hotel</summary>

**File chính:** [`02-journey-map/multi-modal-journey-map.md`](./02-journey-map/multi-modal-journey-map.md)

**6 stage trong hành trình travel:**

| Stage | Key behavior | Growth opportunity |
|---|---|---|
| ✨ Inspire | Scroll social, nghe bạn bè kể | Content matching emotional state per segment |
| 🔍 Search & Planning | So sánh route, giá, ngày | SEO theo route, show real final price |
| 🤔 Consideration | Thu hẹp 2-3 lựa chọn | Trust signals, payment flex, cancel policy |
| ✅ Booking | Nhập thông tin, apply voucher | Friction tại payment là drop-off lớn nhất |
| 📬 Post-booking | Chờ ngày đi, tìm thêm dịch vụ | Cross-sell trong 30ph-24h sau booking |
| 🌟 Post-trip | Share, rate, plan tiếp | 48-72h post-trip là retention window |

**Cross-vertical opportunity lớn nhất:** Flight + Hotel bundle convert mạnh nhất. Cross-sell work tốt nhất trong 30 phút đến 24 giờ sau khi confirm vé máy bay.

**Dùng Claude Code:** `/journey`
</details>

<details>
<summary><b>📁 03 — Promotion</b> — ATL, BTL, partnership, gamification, loyalty</summary>

**File chính:** [`03-promotion/travel-promotion-framework.md`](./03-promotion/travel-promotion-framework.md)

**5 loại promotion và khi nào dùng:**

| Loại | Work khi | Không work khi |
|---|---|---|
| ATL (voucher, flash deal) | Cần acquire new user peak season | Gửi cho user sắp book anyway |
| BTL (behavioral trigger) | User vừa search/abandon — intent cao | Trigger generic/quá muộn |
| Partnership | Offer thực sự exclusive | Deal không beat direct channel |
| Gamification | Activate user lâu không book | Dùng như primary acquisition |
| Loyalty Program | Relaxation Seeker + Family Traveler | Reward quá xa (cần 10+ bookings) |

**Budget allocation theo user type:**
- New user (chưa book): 70-75% budget → ATL
- Current user (book trong 6 tháng): 20% → BTL + loyalty
- Lapsed user (6-12+ tháng): 5-10% → reactivation offer mạnh

**Dùng Claude Code:** `/promotion`
</details>

<details>
<summary><b>📁 04 — Seasonal Calendar</b> — Lịch campaign travel Vietnam theo mùa</summary>

**File chính:** [`04-seasonal/vietnam-campaign-calendar.md`](./04-seasonal/vietnam-campaign-calendar.md)

**4 phase trong năm:**

| Phase | Tháng | Demand | Focus |
|---|---|---|---|
| 🧧 Tết | Dec-Jan | Peak — transport dominant | Acquisition, fixed-price deals |
| 📉 Post-Tết | Feb | Thấp nhất — all verticals | Build (SEO, CRM, loyalty) |
| 🌸 Recovery | Mar-Apr | Growing — 30/4 spike | Bundle testing, Explorer + Z |
| ☀️ Summer | May-Aug | Peak — all verticals | Family, cross-sell, branding |
| 🍂 Post-Summer | Sep | Dropping | Retention của summer bookers |
| 🍃 Low | Oct | Thấp nhất | SEO, data clean, loyalty build |
| 🎄 Year-end | Nov-Dec | Rising toward Tết | Early-bird Tết, loyalty redeem |

**Budget allocation:** 35-40% ngân sách cả năm nên rơi vào Q3 (Summer). Tháng 10 đừng đổ budget vào conversion — dùng để build SEO và phát triển loyalty program.

**Dùng Claude Code:** `/seasonal`
</details>

<details>
<summary><b>📁 05 — Retention</b> — Giữ user từ booking 1 sang booking 2</summary>

**File chính:** [`05-retention/booking1-to-booking2-playbook.md`](./05-retention/booking1-to-booking2-playbook.md)

**90-day playbook:**

| Phase | Days | Action | Goal |
|---|---|---|---|
| 🌟 Capture | 1-3 | Review request, loyalty credit | Lock positive memory |
| 🗺️ Inspire | 14-30 | Destination suggestion, seasonal content | Plant seed for next trip |
| 🎯 Convert | 30-60 | Personalized offer, 30-45 day validity | Convert booking 2 |
| 💫 Reactivate | 60-90 | Stronger offer, acknowledge gap | Win back before churn |

**Key insight:** Nếu không có mechanic cụ thể trong 60-90 ngày sau booking đầu, phần lớn user sẽ không tự quay lại. Không phải vì họ không hài lòng — mà vì họ không có lý do cụ thể để chọn platform của bạn thay vì chỗ khác.

**Segment-specific approaches:**
- Connection Seeker → social trigger + companion offer
- Relaxation Seeker → quality assurance + upgrade mechanic
- Family Traveler → seasonal timing (school holidays)
- Explorer → gamification + exclusive inventory

**Dùng Claude Code:** `/retention`
</details>

<details>
<summary><b>📁 06 — Partner Co-marketing</b> — Làm việc với airline, bus operator, hotel đúng cách</summary>

**File chính:** [`06-partner-comarketing/partner-comarketing-framework.md`](./06-partner-comarketing/partner-comarketing-framework.md)

**Framework 4 câu hỏi trước mọi partnership:**

1. **Offer có thực sự exclusive không?** — Nếu user tìm được deal tương đương direct, partnership không có value thêm
2. **Có track được incrementality không?** — Setup tracking trước launch, không phải sau
3. **Audience overlap có không?** — Partner nhắm business traveler không giúp platform đang target young leisure
4. **Version nhỏ nhất là gì?** — 2 tuần exclusive deal trên 1 route cho biết nhiều hơn 6 tháng broad framework agreement

**Best mechanics theo partner type:**

| Partner | Best mechanic | Why it works |
|---|---|---|
| Airline (budget) | Exclusive fare, specific route | Volume-driven, flexible |
| Airline (full-service) | Co-branded campaign, ancillaries | Brand prestige, protect premium |
| Bus Operator | Inventory exclusivity + early-access deal | Low digital capability, need fill rate |
| Hotel Chain | Bundle with transport | Unsold inventory, last-minute flexibility |
| Experience Provider | Post-booking recommendation | Discovery + distribution |

**Dùng Claude Code:** `/partner`
</details>

<details>
<summary><b>📁 07 — AI Prompts</b> — Prompt AI viết riêng cho travel growth</summary>

**File chính:** [`07-ai-prompts/travel-growth-prompts.md`](./07-ai-prompts/travel-growth-prompts.md)

**Prompt categories:**

| Category | Available prompts |
|---|---|
| `segmentation` | classify-user, campaign-message-by-segment |
| `campaign` | build-brief, choose-mechanic, channel-plan |
| `retention` | retention-diagnosis, booking1-to-booking2, reactivation-plan |
| `partner` | evaluate-partnership, partner-campaign-brief |
| `seasonal` | monthly-strategy, peak-planning |

Mỗi prompt có cấu trúc fill-in (thay bracket bằng context cụ thể). Work trên Claude, ChatGPT, Gemini.

**Dùng Claude Code:** `/prompts`
</details>

## Claude Code Skills

Repo này có thể dùng trực tiếp trong Claude Code:

```bash
# Clone và mở trong Claude Code
git clone https://github.com/thaolst/travel-growth-playbook.git
cd travel-growth-playbook
claude
```

Sau đó dùng lệnh:

| Command | Skill |
|---|---|
| `/segment` | User segmentation |
| `/journey` | Journey map |
| `/promotion` | Promotion design |
| `/seasonal` | Seasonal calendar |
| `/retention` | Retention playbook |
| `/partner` | Partner co-marketing |
| `/prompts` | AI prompts library |

Hoặc copy prompt chain từ mỗi `SKILL.md` dùng trong Claude web / ChatGPT.

## Release & Versioning

Current: **v1.0.0** (see [CHANGELOG.md](./CHANGELOG.md))

Framework được cập nhật theo biến động thị trường travel. Release notes bao gồm:
- Framework updates (new mechanic, segment adjustment)
- Industry data updates (benchmark refresh)
- New AI prompts và tool integration
- Bug fixes và content clarifications

Theo dõi [releases](https://github.com/thaolst/travel-growth-playbook/releases) để biết cập nhật mới nhất.

## Tác giả

Growth Marketing Manager tại MoMo (Vietnam fintech). Trước đó build và scale travel platform tại Việt Nam, covering airline, bus, train, hotel, và experience verticals.

🔗 [LinkedIn](https://linkedin.com/in/thaolst) · [X](https://x.com/thaolst) · [GitHub](https://github.com/thaolst)

## Đóng góp

Làm trong travel marketing và có insight muốn thêm vào? Mở PR hoặc raise issue.

# Travel Growth Playbook

Travel growth has specific dynamics that e-commerce or SaaS frameworks don't cover.

Users book 2-4 times a year. No natural habit loop. High CAC. Retention mechanics need to be purpose-built. And the same trip means completely different things to different people — which affects everything from messaging to promotion design.

This repo is a collection of practical growth marketing frameworks for travel, covering airline, bus, train, and hotel verticals.

📖 [Benchmarks & Industry Data](./BENCHMARKS.md) · 📋 [Changelog](./CHANGELOG.md) · 🔗 [AI Tools](https://github.com/thaolst/travel-ai-tools)

## AI Tools — Try Them Now

The frameworks in this repo power two free AI tools. Use them immediately — no need to read through all the documentation.

| Tool | What it does |
|---|---|
| 🧭 [Campaign Brief Generator](https://thaolst.github.io/travel-ai-tools/campaign-brief-generator.html) | Select segment + vertical + season + goal → Full brief in 2 minutes |
| 🔬 [Retention Cohort Diagnose](https://thaolst.github.io/travel-ai-tools/retention-diagnose.html) | Describe a cohort → Risk level + root cause + 90-day playbook |

Requires an Anthropic API key. No data stored. Runs entirely in your browser. No API key? Use the prompt chain backup included in each tool.

## Benchmarks & Industry Data

See **[BENCHMARKS.md](./BENCHMARKS.md)** for retention rates, CAC estimates, promotion performance, seasonal demand index, and conversion funnel data.

Quick reference:

| Metric | Vietnam Travel (est.) | Global Travel |
|---|---|---|
| Repeat booking rate (6mo) | 15-25% | 20-30% |
| Single-booking user ratio | 55-70% | 50-60% |
| Drop-off booking 1 → 2 | 60-75% | 50-65% |
| Avg bookings/user/year | 2-3 | 2.5-4 |

> Use these as baselines for calibration, not absolute truth. Actual numbers depend on platform, segment, and market.

## Table of Contents & Module Previews

Each folder is a self-contained module. The table below links to the full content. Expand for previews of what's inside.

<details>
<summary><b>📁 01 — User Segmentation</b> — Segment travel users by motivation, not demographics</summary>

**File:** [`01-user-segmentation/travel-segment-framework.md`](./01-user-segmentation/travel-segment-framework.md)

**4 segments that actually matter in travel:**

| Segment | Motivation | Frustration | Retention lever |
|---|---|---|---|
| 🤝 Connection Seeker | Travel to bond with people | Complex UX, poor post-booking service | Social trigger, companion offer |
| 🌿 Relaxation Seeker | Travel to reset, plans carefully | Missing info, photos don't match reality | Upgrade mechanic, loyalty tier |
| 👨‍👩‍👧‍👦 Family Traveler | Travel for family memories | No child options, multi-app hassles | Bundle, referral, seasonal timing |
| 🗺️ Explorer | Travel for new experiences | Budget limit, no discovery feature | Gamification, exclusive inventory |

**Built-in AI prompt:** Classify user → recommend retention mechanic.

**Use with Claude Code:** `/segment`
</details>

<details>
<summary><b>📁 02 — Journey Map</b> — Multi-modal journey map — airline, bus, train, hotel</summary>

**File:** [`02-journey-map/multi-modal-journey-map.md`](./02-journey-map/multi-modal-journey-map.md)

**6-stage journey:**

| Stage | Key behavior | Growth opportunity |
|---|---|---|
| ✨ Inspire | Scroll social, hear from friends | Content matching emotional state per segment |
| 🔍 Search & Planning | Compare routes, prices, dates | SEO by route, show real final price |
| 🤔 Consideration | Narrow to 2-3 options | Trust signals, payment flex, cancel policy |
| ✅ Booking | Enter details, apply voucher | Payment friction is #1 drop-off |
| 📬 Post-booking | Wait for trip, seek add-ons | Cross-sell in 30min-24h after booking |
| 🌟 Post-trip | Share, rate, plan next | 48-72h post-trip is retention window |

**Cross-vertical opportunity:** Flight + Hotel bundle converts strongest. Cross-sell works best within 30 minutes to 24 hours after flight confirmation.

**Use with Claude Code:** `/journey`
</details>

<details>
<summary><b>📁 03 — Promotion</b> — ATL, BTL, partnership, gamification, loyalty</summary>

**File:** [`03-promotion/travel-promotion-framework.md`](./03-promotion/travel-promotion-framework.md)

**5 promotion types:**

| Type | Works when | Fails when |
|---|---|---|
| ATL (voucher, flash deal) | New user acquisition in peak season | Sent to loyal users who'd book anyway |
| BTL (behavioral trigger) | User just searched/abandoned — high intent | Trigger is generic / too late |
| Partnership | Offer is truly exclusive | Deal doesn't beat partner's direct channel |
| Gamification | Reactivate dormant users | Used as primary acquisition mechanic |
| Loyalty Program | Relaxation Seeker + Family Traveler | Reward too far (10+ bookings) |

**Budget allocation by user type:**
- New user (never booked): 70-75% budget → ATL
- Current user (booked within 6mo): 20% → BTL + loyalty
- Lapsed user (6-12+ months): 5-10% → strong reactivation offer

**Use with Claude Code:** `/promotion`
</details>

<details>
<summary><b>📁 04 — Seasonal Calendar</b> — Vietnam travel campaign calendar across 4 phases</summary>

**File:** [`04-seasonal/vietnam-campaign-calendar.md`](./04-seasonal/vietnam-campaign-calendar.md)

**4 phases:**

| Phase | Months | Demand | Campaign focus |
|---|---|---|---|
| 🧧 Tết | Dec-Jan | Peak — transport dominated | Acquisition, fixed-price deals |
| 📉 Post-Tết | Feb | Lowest — all verticals | Build (SEO, CRM, loyalty design) |
| 🌸 Recovery | Mar-Apr | Growing — 30/4 spike | Bundle testing, Explorer + Gen Z |
| ☀️ Summer | May-Aug | Peak — all verticals | Family, cross-sell, branding |
| 🍂 Post-Summer | Sep | Dropping | Retention of summer bookers |
| 🍃 Low | Oct | Lowest | SEO, data clean, loyalty build |
| 🎄 Year-end | Nov-Dec | Rising toward Tết | Early-bird Tết, loyalty redeem |

**Budget:** 35-40% of annual campaign budget in Q3 (Summer). October: don't spend on conversion — build SEO and loyalty program.

**Use with Claude Code:** `/seasonal`
</details>

<details>
<summary><b>📁 05 — Retention</b> — Keeping users from booking 1 to booking 2</summary>

**File:** [`05-retention/booking1-to-booking2-playbook.md`](./05-retention/booking1-to-booking2-playbook.md)

**90-day playbook:**

| Phase | Days | Action | Goal |
|---|---|---|---|
| 🌟 Capture | 1-3 | Review request, loyalty credit | Lock in positive memory |
| 🗺️ Inspire | 14-30 | Destination suggestion, seasonal content | Plant seed for next trip |
| 🎯 Convert | 30-60 | Personalized offer, 30-45 day validity | Convert booking 2 |
| 💫 Reactivate | 60-90 | Stronger offer, acknowledge gap | Win back before churn |

**Key insight:** Without deliberate mechanic within 60-90 days of first booking, most users won't return. Not because they're dissatisfied — but because they have no specific reason to choose your platform again.

**Segment-specific:**
- Connection Seeker → social trigger + companion offer
- Relaxation Seeker → quality assurance + upgrade mechanic
- Family Traveler → seasonal timing (school holidays)
- Explorer → gamification + exclusive inventory

**Use with Claude Code:** `/retention`
</details>

<details>
<summary><b>📁 06 — Partner Co-marketing</b> — Working with airlines, bus operators, hotels the right way</summary>

**File:** [`06-partner-comarketing/partner-comarketing-framework.md`](./06-partner-comarketing/partner-comarketing-framework.md)

**4-question framework before any partnership:**

1. **Is the offer truly exclusive?** — If users can find equivalent deals direct, there's no added value
2. **Can we track incrementality?** — Set up tracking before launch, not after
3. **Audience overlap?** — A business traveler partner doesn't help a young leisure platform
4. **Smallest viable version?** — 2 weeks on 1 route tells you more than a 6-month framework

**Best mechanics by partner type:**

| Partner | Best mechanic | Why it works |
|---|---|---|
| Budget airline | Exclusive fare, specific route | Volume-driven, flexible |
| Full-service airline | Co-branded campaign, ancillaries | Brand prestige, protect premium |
| Bus operator | Inventory exclusivity + early-access | Low digital capability, need fill rate |
| Hotel chain | Bundle with transport | Unsold inventory, last-minute flexibility |
| Experience provider | Post-booking recommendation | Discovery + distribution |

**Use with Claude Code:** `/partner`
</details>

<details>
<summary><b>📁 07 — AI Prompts</b> — AI prompts built specifically for travel growth</summary>

**File:** [`07-ai-prompts/travel-growth-prompts.md`](./07-ai-prompts/travel-growth-prompts.md)

**Prompt categories:**

| Category | Available prompts |
|---|---|
| `segmentation` | classify-user, campaign-message-by-segment |
| `campaign` | build-brief, choose-mechanic, channel-plan |
| `retention` | retention-diagnosis, booking1-to-booking2, reactivation-plan |
| `partner` | evaluate-partnership, partner-campaign-brief |
| `seasonal` | monthly-strategy, peak-planning |

Each prompt has fill-in structure (replace brackets with your context). Works on Claude, ChatGPT, Gemini.

**Use with Claude Code:** `/prompts`
</details>

## Claude Code Skills

This repo works directly in Claude Code:

```bash
git clone https://github.com/thaolst/travel-growth-playbook.git
cd travel-growth-playbook
claude
```

Available commands:

| Command | Skill |
|---|---|
| `/segment` | User segmentation |
| `/journey` | Journey map |
| `/promotion` | Promotion design |
| `/seasonal` | Seasonal calendar |
| `/retention` | Retention playbook |
| `/partner` | Partner co-marketing |
| `/prompts` | AI prompts library |

Or copy the prompt chain from each `SKILL.md` to use in Claude web / ChatGPT.

## Release & Versioning

Current: **v1.0.0** (see [CHANGELOG.md](./CHANGELOG.md))

Framework is updated as the travel market evolves. Release notes cover:
- Framework updates (new mechanics, segment adjustments)
- Industry data updates (benchmark refreshes)
- New AI prompts and tool integrations
- Bug fixes and content clarifications

Follow [releases](https://github.com/thaolst/travel-growth-playbook/releases) for the latest updates.

## Author

Growth Marketing Manager at MoMo (Vietnam fintech). Previously built and scaled a multi-modal travel platform in Vietnam, covering airline, bus, train, hotel, and experience verticals.

Other repos: [growth-mcp](https://github.com/thaolst/growth-mcp) (MCP server for growth marketing, on PyPI) · [ai-growth-prompts](https://github.com/thaolst/ai-growth-prompts) · [ai-growth-agents-for-marketers](https://github.com/thaolst/ai-growth-agents-for-marketers)

🔗 [LinkedIn](https://linkedin.com/in/thaolst) · [X](https://x.com/thaolst) · [GitHub](https://github.com/thaolst)

## Contributing

Work in travel marketing and have insights to add? Open a PR or raise an issue.
