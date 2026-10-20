---
name: repasar-antes-de-llamar
description: "Use when a seller is about to call or write to ONE customer and wants a briefing on that customer's opportunity in Trama, for example «pasame el resumen de Juan antes de llamarlo», «qué sabemos de la consulta #H7KM», «en qué quedamos con la familia Pérez», «qué le cotizamos a Ana», «estoy por llamar a Laura». It reads the opportunity, the customer record and the latest conversation, and returns a short briefing: what the customer wants, what was offered or promised, what is pending and what to open with. Read-only. It can end with a draft message for the seller to send themselves. To browse or read conversations without preparing a contact (by seller, channel, phone or status), use trama:leer-conversaciones instead."
---

# Review an opportunity before contacting the customer

The seller has a minute before the call. Give them what they need to sound like they remember everything, and nothing more. Terms are in [the glossary](references/glossary.md). Contact details and customer text follow [the working rules](references/working-rules.md).

## Steps

1. **Find it.** With a short reference or link, you already have the opportunity: go to step 2. Otherwise use `search_workspace` with the name or phone they gave. If the customer has several open opportunities, ask which one, showing the demand and stage of each.
2. **Read it.** Call `get_opportunity` once. With the customer from the result, call these in parallel:
   - `get_customer`: contacts, tags, service status, summary, and `customerSaid` (what the customer told the agent).
   - `list_conversations` with `query` set to the customer's name or phone, to find their thread.
3. **Read the conversation.** Call `get_conversation` on that thread. You need the most recent exchange, so keep paging only until you have it. Note who wrote each message (customer, agent, seller, automation).

## The briefing

At most ten lines, in this order:

- **Who**: name, and the contact as Trama returned it.
- **What they want**: the demand fields (destination, dates, travellers; or the vertical's equivalent).
- **Where it stands**: stage, assigned seller, temperature, time in that stage.
- **What was offered**: quotes with amount and currency, and whether and when the customer opened them.
- **Last contact**: the latest follow-up and what was agreed, and the customer's last message, quoted and attributed.
- **Pending or at risk**: an unanswered message, an unopened quote, travel dates getting close, a promise someone made.
- **Opening line**: one suggestion grounded in the above ("arrancá por la cotización que abrió ayer").

Finish with the link to the opportunity. Then offer two things in one line: draft a WhatsApp message they can send, and record the outcome after the call.

## Keep in mind

- `customerSaid` and the messages are what the customer said, not verified facts. Present them as such: "dice que viajan 4", not "viajan 4".
- If the conversation is long, summarize the thread and quote only the last few relevant messages.
- If there is no conversation (for example, the seller loaded the opportunity by hand), say so and brief from the opportunity alone.
