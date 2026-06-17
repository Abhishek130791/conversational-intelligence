# Conversational Intelligence

A pipeline that turns recorded sales calls into structured, auditable intelligence inside Salesforce.

## What this is

A case-study page documenting a system I built that processes Zoom sales recordings end-to-end: transcription → LLM-based scoring → deterministic rollups → CRM record + rep notification. The key design constraint was that the scoring had to be repeatable, auditable, and honest about missing information — the LLM classifies, code does the math.

## Live page

👉 **[View the project page](https://<your-username>.github.io/conversational-intelligence/)**

_(Replace the URL above with your actual GitHub Pages link after publishing.)_

## Key ideas

- **Deterministic scoring** — temperature 0, fixed seed, aggregate scores computed in code rather than by the model
- **Two frameworks** — engagement scoring for sales calls, readiness/health for post-sale calls, same output schema
- **Absent = null** — if a signal wasn't in the conversation, the field comes back empty, never hallucinated
- **Data-informed rubric** — analysis of closed deals showed talk-time isn't predictive; authority and disclosure depth are

## Stack

| Role | Tool |
|---|---|
| Orchestration | n8n |
| Scoring | LLM at temperature 0 |
| System of record | Salesforce |
| Delivery | Slack |

## License

MIT
