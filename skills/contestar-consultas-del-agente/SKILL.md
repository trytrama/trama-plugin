---
name: contestar-consultas-del-agente
description: "Use when the person wants to see or answer the questions Trama's AI sales agent left waiting for them, for example «qué me preguntó el agente», «tengo consultas del agente pendientes», «decile que sí, que hay lugar el 15», «contestale a la de Mendoza que el precio incluye traslados». It lists the agent's open questions for this person. It passes their answer to the agent, which writes to the customer in the business's name, after Trama shows exactly what will go out and the person says yes. This is the only flow in the plugin that reaches a customer."
---

# Answer the agent's questions

When one of the business's rules says "ask first", Trama's sales agent pauses the customer conversation and asks someone on the team. The customer is waiting on the other side. Terms are in [the glossary](references/glossary.md). Confirmation follows [the working rules](references/working-rules.md).

## Steps

1. Call `list_agent_questions`. It returns only the questions addressed to this person: customer, question, when it was asked, and the opportunity.
2. Show them, oldest first, one line each: customer · what the agent asks · how long ago. If there are none, say so in one line.
3. When the person answers one, call `answer_agent_question` with `agentQuestionId` and `answer`. The answer is the person's answer in their own words. Fix typos at most. Do not add facts, prices, greetings or promises they did not give: the agent will tell the customer, in the business's name, exactly what this says.
4. Trama always asks the person to confirm this one, because a message to a customer cannot be undone. Show the preview it returns and send the confirmation only on a yes. Do not ask beforehand.
5. The result says whether Trama accepted the answer. The agent writes to the customer right after that. Say "el agente se lo va a contestar al cliente", not "enviado".

## Keep in mind

- If their answer is unclear or does not answer the question, ask them before calling. A vague answer reaches the customer as a vague answer.
- If the question was already answered (by someone else, or in the app), Trama says so. Tell the person and move on.
- This flow answers the agent's question and nothing else. To write something else to a customer, draft a WhatsApp message for the seller to send, as the working rules describe.
- If they need context before answering, read the opportunity or the conversation first, as trama:repasar-antes-de-llamar does.
