# User Segmentation Skill — /segment

Classify travel users by **travel motivation** (not demographics) and recommend retention mechanics.

## When to use

- You have a user's booking history and need to understand their segment
- You're designing campaigns and need to know which segment to target
- You want to personalize offers, messaging, or channel strategy per segment

## How to use

Run `/segment` and describe the user or cohort:

```
/segment User has 2 bookings (both airline, domestic). 
Travels with partner on weekend trips. Books 3-6 weeks ahead. 
Mid-range budget. First trip was Da Lat, second was Da Nang.
```

Or provide structured data:

```
/segment segment profile:
- Booking count: 2
- Verticals: airline
- Travel party: couple
- Book-ahead: 3-6 weeks
- Budget: mid-range
- Destinations: domestic, scenic
```

## Output

The skill will classify the user into one of 4 segments and recommend:

| Segment | Motivation | Retention Lever |
|---|---|---|
| Connection Seeker | Travel to bond with people | Social triggers, companion offers |
| Relaxation Seeker | Travel to reset and unwind | Quality assurance, upgrade mechanic |
| Family Traveler | Travel for family memories | Bundles, referral, seasonal timing |
| Explorer | Travel for new experiences | Gamification, exclusive inventory |

## Framework

See [travel-segment-framework.md](./travel-segment-framework.md) for the full methodology.

## Prompt chain

```
System: You are a travel growth marketing strategist specializing in user segmentation for multi-modal travel platforms in Vietnam and Southeast Asia. You classify users by travel motivation, not demographics. You give specific, actionable retention recommendations.

User: Classify this travel user into one of 4 segments (Connection Seeker, Relaxation Seeker, Family Traveler, Explorer).

User profile: [describe booking history, verticals, destinations, travel party, booking timing, budget level]

For each segment considered, explain:
1. Why this segment fits or doesn't fit
2. The user's core travel motivation
3. Their biggest frustration with booking platforms
4. 1 specific retention mechanic that would work
5. What promotion type to avoid with this user
```
