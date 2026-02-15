# n8n Lead Intake Qualification System

AI-assisted inbound lead scoring with deterministic fallback, hot-lead alerts, CRM upserts, and owner notifications.

## Files
- `n8n/workflow.json` importable n8n workflow (AI-assisted + deterministic fallback)

## Architecture
- Webhook intake -> payload normalization -> deterministic score
- AI qualification via OpenRouter -> parsed score signal
- Signal merge -> final weighted score and priority decision
- Hot-lead branch to sales alert + all-leads CRM upsert + owner notification

## Runtime Requirements
- n8n (validated with containerized import on n8n latest)
- Set `OPENROUTER_API_KEY` in your n8n environment for AI nodes
- Replace placeholder webhook/API endpoints and credentials before activation

## Import
1. Open n8n UI.
2. Go to `Workflows -> Import from File`.
3. Select `n8n/workflow.json`.
4. Configure credentials and endpoint placeholders.
5. Run a manual execution test before enabling schedule/webhook traffic.

## Live Demo
- https://jeffery-addae-portfolio-web.vercel.app/projects/ai-powered-lead-intake-qualification-system
