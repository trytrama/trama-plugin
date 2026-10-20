---
name: barrido-de-seguimiento
description: "Use when the person wants to catch up on customers who went QUIET, with nothing scheduled, or to plan the week's follow-ups in Trama, for example «barrido de seguimiento», «a quién tengo que escribir esta semana», «qué oportunidades tengo sin tocar», «las que no avanzan», «los que no me contestaron». It finds the person's active opportunities with no recent activity and nothing scheduled, proposes up to 10 to contact, each with a concrete reason taken from the data, and after the person approves, records the follow-ups, reminders and pauses they chose. For what is already due today (reminders, overdue follow-ups, flagged quotes), use trama:preparar-mi-dia instead."
---

# Weekly follow-up sweep

The aim is a short list of customers worth contacting now, each with a real reason to write. "¿Cómo va todo?" is not a reason. Read [the working rules](references/working-rules.md) before the first change. Terms are in [the glossary](references/glossary.md).

## 1. Find the quiet ones

Call these in parallel:

- `list_opportunities` with `seller: me`, `state: active`, `inactiveForDays: 7` (or the window they asked for), `sort: updatedAt` and `limit: 50`. Page with `cursor` while `hasMore` is true, up to 100. The order of `sort` is not guaranteed to be the one you need: order the rows yourself by `updatedAt`, oldest first, so the quietest come first.
- `list_pending_tasks` with `includeUpcomingDays: 7`, to know which of them already have a follow-up or reminder scheduled this week.

Leave out the ones that already have something scheduled. If more than 10 are left, keep the 10 with the most at stake: quoted first, then hot, then the quietest. A round is 10 at most; say how many were left for the next one ("quedan 14 más para otra ronda"). If you stopped at 100 with more to read, say so.

## 2. Read what you need

For the ones you keep, call `get_opportunity` in parallel. Look at the last follow-ups, the quotes (amount, and whether and when the customer opened them) and the dates of the trip.

Find a concrete reason for each one, from the data:

- "Abrió la cotización ayer dos veces y no respondió."
- "Dijo que decidía cuando cobrara el aguinaldo; ya es diciembre."
- "Viaja en tres semanas y no tiene seguro."

If nothing in the data gives a reason, say "sin novedad desde el 3/10" rather than inventing one.

## 3. Propose, then wait

Send a numbered list, one line per opportunity: customer · demand · stage, the last contact, the reason, and a suggested step (write today, a reminder on a date, pause until a date, or close as lost). Then ask one question: what to record.

Do not write anything before they answer. With several customers, do not draft messages. If they then pick one customer to write to, draft that one message as the working rules describe.

## 4. Record what they chose

- Follow-up notes: `add_opportunity_follow_up`, all in one call (up to 100 items).
- Reminders: `create_reminder`, one call each, in parallel. A day with no time goes at 09:00; say so, so they can change it.
- Pauses and closes: `move_opportunity` with `to: paused` and `pausedUntil`, or the lost stage with a `reason`.

With 10 opportunities per round, the writes stay under the line where Trama asks for a confirmation, so the person's approval of the list is the only question. If Trama still asks (earlier changes in the last few minutes count), follow the working rules. Then report one line per opportunity with what was recorded.
