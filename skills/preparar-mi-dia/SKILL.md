---
name: preparar-mi-dia
description: "Use when someone who works at a business on Trama wants to know what is due TODAY or to plan their shift, for example «¿qué tengo hoy?», «armame el día», «qué tengo pendiente para hoy», «qué entró nuevo», «repasá mi día». Also use it when they ask about the Mission Control summary («el resumen») they have open, or about one of its figures. It builds one prioritized list from what Trama already has scheduled or flagged (due reminders, overdue follow-ups, flagged quotes, hot opportunities nobody took) and the opportunities that came in since yesterday. It explains how the stored summary differs from the live state. Read-only. For customers who went quiet and have nothing scheduled, or planning the week's follow-ups, use trama:barrido-de-seguimiento instead."
---

# Prepare my day

The goal is one list the person can work from top to bottom, with the reason each item is there. For the terms (pending work, temperature, Mission Control summary), see [the glossary](references/glossary.md). For how to write the answer, see [the working rules](references/working-rules.md).

## Today's work

1. Call these in parallel:
   - `list_pending_tasks` for the person. It returns three sections: `reminders`, `followUps` and `actionItems`. An owner or admin asking about one seller passes `sellerMemberId`. A member always gets their own.
   - `list_opportunities` with `seller: me`, `createdSince` set to the start of yesterday and `sort: createdAt`: what came in since yesterday.
2. Open an opportunity with `get_opportunity` only when you cannot rank it without the detail, for example an overdue follow-up whose note does not say what was agreed. Open at most five. The list should be quick to get, not exhaustive.
3. Build one list in this order:
   1. Overdue: reminders and follow-ups whose date has passed, oldest first.
   2. Due today, by time.
   3. What Trama flagged: a quote with no follow-up, an old quote, a high-value opportunity, a hot opportunity nobody took.
   4. New since yesterday and still in «Por atender».

   When the same opportunity appears in more than one section, it gets one line with all its reasons.
4. Each line says what it is (customer · demand · stage, short reference), why it is on the list, and the next concrete step ("llamar: abrió la cotización ayer", not "hacer seguimiento").

"Hot" means the opportunity is ready to quote: its data is mostly complete and the customer shows interest. It does not mean the customer is about to buy; say it that way. A person may have set the temperature by hand.

## The Mission Control summary

When they talk about "el resumen", the summary they have open, or a figure from it:

1. Call `get_mission_control_summary`. Without `bucket` it returns the latest snapshot, which is what they are looking at.
2. When they ask about a figure, start with its definition and the time window it covers, as the snapshot states them. Give your view after that.
3. When you list what to act on, name the seller who holds each row.
4. If they want the current state, call `list_pending_tasks` and explain any difference by when the snapshot was taken: the part of the day it belongs to (morning, midday or evening), as the result states it. The summary is a photo of that moment. Do not call it wrong. If the result does not say when it was taken, say that, instead of guessing the hour.
5. If a total comes without its rows, say so instead of reconstructing them.

## The answer

At most ten lines of list. If there are more, say how many and which ones you left out ("y 6 más de días anteriores"). Close with one offer: record follow-ups, create or move reminders for what they decide. If they accept, record them as trama:registrar-novedad describes, with `add_opportunity_follow_up`, `create_reminder` and `update_reminder`.

This skill only reads. Write nothing until the person says what to record.
