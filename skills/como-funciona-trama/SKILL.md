---
name: como-funciona-trama
description: "Use when someone asks how Trama works or where something is done in it, for example «¿dónde vinculo WhatsApp?», «cómo funciona la temperatura», «por qué el agente no contesta en este número», «cómo pauso una oportunidad», «qué es un número Asistido», «cómo cargo el catálogo», «cómo invito a un vendedor». It answers from Trama's public help center, with a link to the page, instead of from memory. Use it before describing any screen, menu or setting of Trama."
---

# How Trama works

Trama changes often, and a wrong menu path sends the person looking for a button that does not exist. Answer from the help center, not from what seems likely. Terms are in [the glossary](references/glossary.md).

## Steps

1. Call `search_help` with the question in the person's words and `language` set to theirs (`es`, `en` or `pt`).
2. Read the excerpts. If the best one does not answer the question, search again once with other words (the screen's name, the feature's name in the glossary).
3. Answer in two to five lines: what to do, where, and in what order, using the screen and button names from the excerpt. Add the link to the page.

## When the question is about their own data

"¿Por qué no me llegó esta consulta?" or "¿por qué esta oportunidad está pausada?" combines how Trama works with a specific record. Explain the mechanism from the help center, then look at the record (for example with `get_opportunity` or `get_conversation`) and say which case applies.

## When the help does not cover it

Say that the help center does not cover it, give the closest page, and suggest contacting Trama's support from the app. Do not fill the gap with a guess about how the screen probably works.

Plans, billing and upgrades are not answered here. If asked, say they are handled in the app.
