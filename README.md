# n8n Lead Intake Qualification System

AI-assisted inbound lead scoring with deterministic fallback, hot-lead alerts, CRM upserts, and owner notifications.

## Files
- `n8n/workflow.json` importable n8n workflow (AI Agent + deterministic fallback + native app nodes)

## Architecture
- Webhook intake -> payload normalization -> deterministic score
- AI Agent + OpenAI Chat Model -> parsed AI signal
- Signal merge -> final weighted score and priority decision
- Hot-lead branch to Slack + HubSpot + Notion + Gmail owner summary

## Runtime Requirements
- n8n (validated with containerized import on n8n latest)
- Configure credentials for:
  - `OpenAI` (for `AI Agent` model connection)
  - `Slack`
  - `Notion`
  - `Gmail`
  - `HubSpot` (where used)
- Replace placeholder channel/database IDs and recipient addresses before activation

## Import
1. Open n8n UI.
2. Go to `Workflows -> Import from File`.
3. Select `n8n/workflow.json`.
4. Configure credentials and placeholder IDs.
5. Run a manual execution test before enabling schedule/webhook traffic.

## Live Demo
- https://jefferyaddae.it.com/projects/ai-powered-lead-intake-qualification-system
