# Journey Map Skill — /journey

Map a multi-modal travel user journey across 6 stages and identify growth opportunities at each touchpoint.

## When to use

- You're designing a new product or feature for a travel platform
- You want to find conversion drop-off points in the current funnel
- You need to prioritize cross-vertical integration (e.g., flight + hotel, bus + hotel)
- You're planning post-booking communication sequences

## How to use

Run `/journey` with context about your platform and target segment:

```
/journey platform OTA, targeting Explorer + Connection Seeker, 
verticals airline + hotel. Current drop-off: 40% after search.
```

Or for a specific stage analysis:

```
/journey stage=post-booking segment=Relaxation Seeker 
vertical=hotel
```

## Output

The skill analyzes the 6-stage journey and identifies:

| Stage | Key Behavior | Growth Opportunity |
|---|---|---|
| 1. Inspire | Scrolling social, hearing from friends | Content matching emotional state per segment |
| 2. Search & Plan | Comparing routes, prices, dates | SEO by route, show real final price |
| 3. Consider | Narrowing to 2-3 options | Trust signals, payment flex, cancel policy |
| 4. Book | Entering details, applying voucher | UX friction kills intent at payment |
| 5. Post-book | Waiting for trip, seeking add-ons | Cross-sell in 30min-24h after booking |
| 6. Post-trip | Sharing, rating, planning next | 48-72h window for retention trigger |

## Framework

See [multi-modal-journey-map.md](./multi-modal-journey-map.md) for the full methodology.

## Prompt chain

```
System: You are a travel growth strategist specializing in multi-modal user journeys. You analyze travel platforms across airline, bus, train, and hotel verticals in Southeast Asia.

User: Analyze this travel user journey and identify growth opportunities.

Platform: [OTA / airline / bus / hotel chain]
Target segment: [segment name]
Verticals available: [list]
Known drop-off points: [describe]

Map the journey across 6 stages and for each:
1. What the user is doing and feeling
2. Where current platforms drop the ball
3. 1 specific growth opportunity (with rationale)
4. What NOT to do at this stage

Cross-vertical opportunity: identify the single highest-value integration between verticals for this platform and this segment.
```
