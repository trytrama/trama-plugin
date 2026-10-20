---
name: como-viene-el-equipo
description: "Use when an owner or admin asks how the sales team or one seller is doing in Trama, for example «cómo viene el equipo», «quién está respondiendo lento», «rendimiento de Marisa este mes», «quién vendió más», «están atendiendo bien las consultas». It compares what each seller worked and closed with how fast they really answer customers on the channels they operate, and points out where the board and the conversations tell different stories. Read-only. A seller who asks gets their own figures and the team average."
---

# Team and seller report

The interesting part is the gap: where the board says one thing and the conversations say another. A seller can move cards on time and still leave customers waiting hours on their phone. Terms are in [the glossary](references/glossary.md). Format and figures follow [the working rules](references/working-rules.md).

## Steps

1. **Period.** Use the one they asked for. If they gave none, use the last 30 days and say so in the answer.
2. **One seller?** If they name a person, resolve the name to a team member with `get_team` (or `search_workspace` with `kinds: member`) and pass `sellerMemberId`.
3. Call `get_team_performance` with the period. It returns, per seller, what they worked and closed and their real response time on the channels they operate, plus `teamAverage`.
4. If they ask about amounts or results by stage, also call `query_opportunities` for the same period, grouped by seller. It is only available to owners and admins.

## The answer

- One line per seller: what they took, moved and closed, and their real response time. Next to it, the board's version where they differ.
- Then the two or three gaps worth acting on, each with the figures behind it.
- Name people only as Trama returns them. If someone has no attention data (for example, they operate no channel), say so instead of assuming they answer well or badly.
- With fewer than five opportunities behind a figure, give the count ("3 de 4"), not a percentage. A rate over one or two cases says nothing.
- Compare figures only within the same period.

## Who sees what

Trama decides visibility. Per-seller performance is for owners and admins. Response time by name is for the owner. Everyone else sees their own figures and the team average. If a member asks about a colleague, explain that Trama shows them only their own row; do not estimate the colleague's figures from other data.
