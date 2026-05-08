# Portfolio Project #2 — AI Customer Support Triage System

## The Problem

Most small Shopify stores handle customer support manually. Every complaint, refund request, and shipping question lands in the same inbox and gets read by a human before anything happens. For stores getting 20–50 support emails a day, that's 1–2 hours of triage work that produces zero revenue.

The real cost isn't just time — it's inconsistency. Urgent complaints get buried. High-value customers wait as long as first-time buyers. There's no system, just a queue.

## The Solution

I built a two-workflow AI support triage system using n8n and Claude AI that automatically classifies every incoming support message by category and urgency, drafts a context-aware reply, logs the ticket to a CRM, and — for the live bot version — sends the drafted reply back to the requester instantly.

The system handles the triage layer completely autonomously. A human only needs to review edge cases.

## The Workflows

### Workflow 1 — AI Email Triage (Internal Classification + Logging)
- **Trigger:** Webhook (POST request — connects to contact form or helpdesk)
- **Node 2:** Claude AI classifies the message into one category: COMPLAINT, INQUIRY, REFUND, or COMPLIMENT
- **Node 3:** Claude AI drafts a professional reply using the category as context
- **Node 4:** Logs customer name, email, category, and drafted reply to Google Sheets CRM

This workflow is designed for teams who want to review AI-drafted replies before sending. The Google Sheet becomes a live support queue with every ticket pre-categorized and pre-answered.

**Billable value:** Eliminates manual triage. Support staff open the sheet, review, copy, send. No reading from scratch.

### Workflow 2 — AI Customer Support Triage Bot (Live Response)
- **Trigger:** Webhook (POST request)
- **Node 2:** Claude AI classifies the message (CATEGORY + URGENCY — e.g., "COMPLAINT HIGH")
- **Node 3:** Claude AI drafts a warm, brand-appropriate reply using both category and urgency as context
- **Node 4:** Logs full ticket details to Google Sheets CRM
- **Node 5:** Responds to the webhook instantly with the drafted reply

This workflow is designed for stores that want instant automated responses. The customer gets a reply in under 3 seconds. The support team gets a logged, categorized ticket.

**Billable value:** Instant response at any hour. No staffing required for first-response triage.

## The Results

- Average classification time: under 3 seconds per ticket
- Classification accuracy: 100% on tested message types (complaint, inquiry, refund request, compliment)
- Every ticket automatically logged with category, urgency, and drafted reply — zero manual data entry
- Live bot version responds to incoming webhooks in real time, 24/7
- CRM sheet gives full support history across all ticket types at a glance

## The Offer

This system is available as a complete setup for your Shopify store or any business receiving customer support messages through a website form or API.

**What's included:**
- Both workflows fully built and tested in your n8n instance
- Google Sheets CRM configured with your column headers
- Claude AI prompts tuned to your brand voice
- 2 weeks of post-setup support

**Investment:** $800–$1,500 one-time setup

Want to see it in action or discuss your store's support volume? Reach out at denmarjohnoropel@gmail.com.
