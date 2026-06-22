# Lead Capture & Auto-Response Automation

An n8n workflow that captures incoming leads, logs them to a structured database, and triggers an instant personalized auto-reply — removing the manual delay between lead submission and first response.

## What It Does

This workflow automates the first-touch process in a lead pipeline:

1. **Capture** — A new lead's details are received and validated.
2. **Store** — The lead record is written to Google Sheets, creating a running, queryable log of all incoming leads.
3. **Respond** — An automatic, personalized email reply is sent to the lead immediately — confirming receipt and setting expectations for next steps.

The result: zero-delay lead acknowledgment, with every lead centrally tracked instead of scattered across inboxes.

## Why This Matters

Manual lead handling has two recurring failure points: leads sit unacknowledged for hours, and records get lost across email threads. This workflow solves both — leads are logged consistently and the sender hears back within seconds, with no human in the loop until follow-up is needed.

## Workflow Breakdown

| Stage | Node Type | Function |
|---|---|---|
| Trigger | Manual Trigger | Initiates the workflow run |
| Storage | Google Sheets | Writes lead data to a structured, searchable record |
| Response | Email/SMTP Node | Sends a templated auto-reply to the lead |

*(Update the trigger row if you move this from manual to a live Webhook trigger for production use — see Roadmap below.)*

## Tech Stack

- **n8n** — workflow orchestration
- **Google Sheets** — lead data storage
- **SMTP/Email node** — automated response delivery

## Setup

1. Import `form-workflow.json` into your n8n instance: **Workflows → Import from File**.
2. Connect your Google Sheets credentials in the Storage node.
3. Connect your email/SMTP credentials in the Response node.
4. Update the email template with your own reply copy.
5. Run manually, or swap the trigger node for a Webhook to go live on a real form/landing page.

## Roadmap / Next Iteration

- Replace manual trigger with a **Webhook trigger** so it fires automatically from a live form submission.
- Add an **AI node** (Claude/OpenAI) to score or summarize incoming leads before they're logged — turning this from a pure automation into an AI-augmented pipeline.
- Add conditional routing (e.g., high-priority leads get a Slack alert in addition to the email).

## Screenshot

![Workflow Canvas](screenshots/workflow-diagram.png)

---

*Part of an ongoing portfolio of n8n automation workflows — see other repos for AI-integrated examples.*
