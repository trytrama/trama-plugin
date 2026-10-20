---
name: borrador-de-campana
description: "Use when an owner or admin wants ideas or a draft for a WhatsApp campaign in Trama, for example «armame una campaña», «a quién le escribo este mes», «redactá el mensaje para los que cotizaron Brasil y no compraron», «qué plantillas tengo aprobadas», or a pasted promo they want turned into a campaign. It suggests audiences from the business's own data, fills an approved WhatsApp template, and shows the final message with how many people it would reach. Draft only. Sending is done by a person in Trama's Campaigns screen. This skill never sends, schedules or promises a send."
---

# Prepare a campaign draft

A campaign is the most expensive mistake available: each message costs money in Meta and cannot be recalled. Your part is to help choose the audience and get the text right. A person reviews and sends it in the app. Terms are in [the glossary](references/glossary.md). [The working rules](references/working-rules.md) apply.

## Steps

1. **Ideas and templates.** Call `suggest_campaigns`. It returns `proposals` (an audience Trama suggests from the data, for example customers who got a quote for a destination and did not buy, with its size) and `templates` (the WhatsApp templates Meta approved, with the variables each one still needs).
2. **Choose with the person.** Offer the two or three proposals that fit what they asked, with sizes, and the templates that fit. If they brought their own promo text, explain that a campaign goes out on an approved template. Show which template is closest, and which of their content fits into its variables.
3. **Draft it.** Call `draft_campaign_message` with `proposalKey`, `templateKey`, `language` and `values`. It saves and sends nothing. It returns the final `text`, `audienceCount` and `sampleRecipients` (first names only).
4. **Fix and retry.** If Trama rejects the copy, it says what to change: a price that does not come from the data, a promise made to each recipient, the template's language, the length. Adjust the values and draft again.

## The answer

- The final message between two lines holding only `---`, exactly as it would arrive.
- How many people it reaches, and a few of the sample first names.
- One closing line: to send it, open «Campañas» in Trama, where it is reviewed and approved.

## Keep in mind

- Values come from the person or from Trama's data. Do not add prices, dates or availability yourself.
- Never say the campaign is sent, scheduled or "lista para salir". Say it is a draft.
- Campaigns are for owners and admins. If the tools are not available to this person, say that campaigns are handled by the business's owner or an admin.
- Writing to one customer is not a campaign. For that, draft one WhatsApp message for the seller to send from their own phone, as the working rules describe.
