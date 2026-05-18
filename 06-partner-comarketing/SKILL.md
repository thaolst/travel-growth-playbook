# Partner Co-marketing Skill — /partner

Design and evaluate co-marketing partnerships with airlines, bus operators, hotel chains, and experience providers.

## When to use

- You're approaching or being approached by a potential travel partner
- You need to evaluate whether a partnership deal is worth pursuing
- You want to design a co-marketing campaign with an existing partner
- You need to negotiate terms with a specific partner type

## How to use

Run `/partner` with partner context:

```
/partner evaluate partner=airline scale=large 
goal=exclusive-fare route=HCMC-DaNang duration=2weeks
```

Or for a specific partner type:

```
/partner partner=hotel segment=Explorer mechanic=bundle
```

## Output

The skill evaluates the partnership against 4 criteria and recommends specific mechanics:

| Partner Type | Your Leverage | Their Motivation | Best Mechanic |
|---|---|---|---|
| Airline | Distribution, payment flex, user data | Volume, awareness, ancillaries | Exclusive fare, co-branded launch |
| Bus Operator | Digital capability, demand prediction | Fill rate, cancellation handling | Inventory exclusivity on popular routes |
| Hotel Chain | Cross-sell from transport, payment | Unsold inventory, reach | Bundle pricing, last-minute deals |
| Experience Provider | Transport + accommodation hooks | Discovery, distribution | Post-booking recommendation |

## Framework

See [partner-comarketing-framework.md](./partner-comarketing-framework.md) for the full methodology including the 4-question partnership evaluation framework.

## Prompt chain

```
System: You are a partnership strategist specializing in travel co-marketing in Vietnam and Southeast Asia. You know how airlines, bus operators, hotel chains, and experience providers think, and what mechanics actually drive incremental value.

User: Evaluate this potential co-marketing partnership.

Partner type: [airline / bus operator / hotel chain / experience provider]
Partner scale: [national / regional / local]
Partner goal: [volume / awareness / fill rate / new segment]
What they offer: [inventory / brand / audience / budget]
What we offer: [distribution / payment / data / campaign budget]
Proposed mechanic: [brief description]

Evaluate using the 4-question framework:
1. Is this offer truly exclusive?
2. Can we track incrementality?
3. Does our audience overlap?
4. What's the smallest viable version?

Then recommend:
1. Go / No-go / Test-small recommendation
2. Specific mechanic design (offer, timing, targeting)
3. Success metrics and tracking approach
4. 2 risks to mitigate before launch
5. What to negotiate for in the first conversation
```
