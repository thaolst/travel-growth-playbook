# Seasonal Calendar Skill — /seasonal

Get the Vietnam travel campaign calendar with demand patterns, budget allocation, and campaign focus by month.

## When to use

- You're planning the annual campaign calendar
- You need to know when to push acquisition vs retention
- You're allocating budget across months and quarters
- You want to align campaigns with Vietnam-specific travel demand patterns

## How to use

Run `/seasonal` with optional focus:

```
/seasonal
```

Or for a specific period:

```
/seasonal month=June vertical=hotel segment=Family Traveler
```

Or to plan a campaign:

```
/seasonal campaign goal=retention starting=March duration=8weeks
```

## Output

The skill outputs the current phase's demand context and recommendations:

| Phase | Months | Demand | Key Focus |
|---|---|---|---|
| 🧧 Tết | Dec-Jan | Highest — transport dominant | Acquisition, fixed-price deals |
| 📉 Post-Tết | Feb | Lowest — all verticals | Build (SEO, CRM, loyalty design) |
| 🌸 Recovery | Mar-Apr | Growing — 30/4 spike | Bundle testing, Explorer + Z targeting |
| ☀️ Summer | May-Aug | Peak — all verticals | Family, cross-sell, branding |
| 🍂 Post-Summer | Sep | Dropping | Retention of summer bookers |
| 🍃 Low | Oct | Lowest | SEO, data clean, loyalty build |
| 🎄 Year-end | Nov-Dec | Rising toward Tết | Early-bird Tết, loyalty redeem |

## Framework

See [vietnam-campaign-calendar.md](./vietnam-campaign-calendar.md) for the full calendar with budget allocation by month and vertical-specific timing.

## Prompt chain

```
System: You are a travel growth strategist with deep knowledge of Vietnam's travel demand calendar, including Tết seasonality, summer peaks, and regional travel patterns.

User: I need campaign planning guidance for this period.

Current month: [month]
Next campaign: [campaign type]
Target segment: [segment]
Vertical: [vertical]

Give me:
1. Demand outlook for the next 4-8 weeks (high/medium/low, by vertical)
2. Primary campaign focus for this period (acquisition / retention / brand / build)
3. 1 specific campaign idea optimized for this month + segment + vertical
4. What NOT to spend budget on this month
5. Budget allocation recommendation (always-on vs seasonal split)
6. 2 things to prepare this month that will pay off next quarter
```
