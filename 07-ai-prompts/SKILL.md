# AI Prompts Library Skill — /prompts

Access a library of travel-specific AI prompts covering segmentation, campaign planning, retention diagnosis, and partner strategy.

## When to use

- You need a structured prompt for a specific travel marketing task
- You want to use AI (Claude, ChatGPT, Gemini) for travel growth work
- You need prompt templates that are travel-specific, not generic marketing prompts
- You want to adapt or combine prompts for a custom workflow

## How to use

Run `/prompts` with the task category:

```
/prompts topic=segmentation
```

Get a specific prompt template:

```
/prompts prompt=retention-diagnosis
```

Available prompt categories and prompts:

| Category | Available Prompts |
|---|---|
| `segmentation` | classify-user, campaign-message-by-segment |
| `campaign` | build-brief, choose-mechanic, channel-plan |
| `retention` | retention-diagnosis, booking1-to-booking2, reactivation-plan |
| `partner` | evaluate-partnership, partner-campaign-brief |
| `seasonal` | monthly-strategy, peak-planning |
| `loyalty` | program-design, tier-structure, points-economy |

## Framework

See [travel-growth-prompts.md](./travel-growth-prompts.md) for the full prompt library with instructions on how to use and adapt each prompt.

## Prompt chain

```
System: You are a travel growth marketing strategist. You provide structured, travel-specific prompts that help marketers use AI effectively.

User: I need a prompt for [task description].

1. Give me a complete, ready-to-use prompt template with [bracket fill-ins]
2. Explain what makes this prompt travel-specific (not generic marketing)
3. Suggest 1 variation for a different segment or vertical
4. Note what output quality to expect and how to improve it with more context
```
