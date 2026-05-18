# Promotion Mechanics Skill — /promotion

Design travel-specific promotion mechanics: ATL, BTL, partnership, gamification, loyalty. Covers which mechanic works for which segment, vertical, and season.

## When to use

- You're planning a campaign and need to choose the right promotion type
- You want to move beyond generic discounting
- You need to allocate promo budget across segments and verticals
- You're designing a loyalty program for a low-frequency travel platform

## How to use

Run `/promotion` with campaign context:

```
/promotion segment=Explorer vertical=airline+hotel 
season=Summer goal=retention budget=medium
```

Or for a specific mechanic deep-dive:

```
/promotion loyalty
```

## Output

The skill recommends specific promotion mechanics with rationale:

| Mechanic | Best For | Works When | Avoid When |
|---|---|---|---|
| ATL (flash deal, voucher) | New users, peak season | High volume needed | Sending to loyal users who'd book anyway |
| BTL (behavioral trigger) | Current users, post-booking | User shows intent (search, abandon) | Trigger is too late or message is generic |
| Partnership | Trust-building, cross-vertical | Exclusive offer possible | Deal isn't better than partner's direct channel |
| Gamification | Engagement, Explorer segment | Off-peak, low purchase intent | Used as primary acquisition mechanic |
| Loyalty program | Retention, high-value segments | Reward is travel-relevant | Reward takes too many bookings to reach |

## Framework

See [travel-promotion-framework.md](./travel-promotion-framework.md) for the full methodology including budget allocation by user type and vertical-specific mechanics.

## Prompt chain

```
System: You are a travel growth strategist specializing in promotion mechanics for multi-modal travel platforms in Vietnam. You know which promotion type works for which segment, vertical, and season.

User: Design a promotion strategy for this travel campaign.

Platform: [OTA / airline / bus / hotel]
Target segment: [Connection Seeker / Relaxation Seeker / Family Traveler / Explorer]
Vertical(s): [airline / bus / train / hotel]
Season: [Tết / 30/4 / Summer / Year-end / Off-peak]
Goal: [acquisition / retention / reactivation]
Budget level: [large / medium / small]

Recommend:
1. Primary mechanic (from: ATL, BTL, partnership, gamification, loyalty)
2. Why this mechanic fits this segment and season
3. Specific offer design (discount %, expiry, targeting logic)
4. Channel priority for this mechanic
5. What NOT to do with this segment
6. Budget split recommendation if running multiple mechanics
```
