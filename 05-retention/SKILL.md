# Retention Playbook Skill — /retention

Design a 90-day retention playbook for the critical window between booking 1 and booking 2 in travel.

## When to use

- A user just completed their first booking — you need a retention plan
- You want to design the post-booking communication sequence
- You're seeing high drop-off between first and second booking
- You need segment-specific retention mechanics

## How to use

Run `/retention` with user or cohort profile:

```
/retention user segment=Connection Seeker vertical=airline 
first booking=12 days ago location=domestic
```

Or for a full playbook:

```
/retention playbook segment=Family Traveler vertical=bus+hotel
```

## Output

The skill outputs a timed playbook aligned with the 60-90 day retention window:

| Phase | Days | Action | Goal |
|---|---|---|---|
| Capture | 1-3 | Review request, loyalty credit, social share prompt | Lock in positive memory |
| Inspire | 14-30 | Destination suggestion based on past trip, seasonal content | Plant seed for next trip |
| Convert | 30-60 | Personalized offer with 30-45 day validity, right-size discount | Convert booking 2 |
| Reactivate | 60-90 | Stronger offer, acknowledge gap, flash deal aligned with profile | Win back before churn |

## Framework

See [booking1-to-booking2-playbook.md](./booking1-to-booking2-playbook.md) for the full methodology including segment-specific approaches and AI prompts.

## Prompt chain

```
System: You are a retention strategist specializing in travel platforms in Vietnam and Southeast Asia. You know that travel has low natural frequency (2-4 bookings/year) and that the 60-90 day window after first booking is the most critical retention moment.

User: Design a 90-day retention playbook for this travel user.

User profile:
- Segment: [Connection Seeker / Relaxation Seeker / Family Traveler / Explorer]
- Vertical(s): [airline / bus / train / hotel]
- First booking: [X days ago]
- Booking value: [low / medium / high]
- What we know about them: [anything from CRM]

Output a playbook with 4 phases:

Phase 1 (Days 1-3): Capture the moment
- What to send
- What NOT to send (critical mistake to avoid)

Phase 2 (Days 14-30): Inspire
- Message type and content
- Personalization logic

Phase 3 (Days 30-60): Convert
- Specific offer recommendation (amount, expiry, delivery channel)
- Why this offer for this segment

Phase 4 (Days 60-90): Reactivate
- Offer escalation if no response
- Last-touch strategy before moving to win-back

Also include: 1 metric to track per phase, and a fallback plan if the user doesn't respond by day 90.
```
