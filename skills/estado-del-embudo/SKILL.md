---
name: estado-del-embudo
description: "Use when an owner or admin asks where the sales pipeline is getting stuck, or what customers ask for that the business does not sell, in Trama. Examples are «estado del embudo», «dónde se traba el pipeline», «qué columna acumula», «de qué origen vienen las que no cierran», «cuántas se nos durmieron», «qué piden que no tenemos en el catálogo». It reads the board by stage, the period's figures by seller and source, and the dormant opportunities, and it cross-checks requested demand against the catalog. Read-only. It separates what the data shows from what you infer."
---

# Pipeline review

Two questions, both about the board as a whole: where opportunities get stuck, and what demand the catalog does not cover. Terms are in [the glossary](references/glossary.md). Figures and format follow [the working rules](references/working-rules.md).

Every claim in the answer comes with the number behind it. Label inferences ("probablemente…") and keep them apart from what the data shows.

## Where it gets stuck

1. Call these in parallel:
   - `list_opportunities` with `state: active` and a small `limit`, for `byStage` (how many sit in each column).
   - `query_opportunities` for the period (the last 30 days if they gave none), grouped by seller and by source, with counts and amounts.
   - `list_opportunities` with `state: dormant` and `createdSince` at the start of the period: the opportunities created in the period that are dormant now. Trama does not say when each one went dormant, so this is not "how many went dormant in the period".
2. Say concretely:
   - which column accumulates, and how many. Leave «Ganado» and «Perdido» out of this comparison (and whatever columns the business uses for won and lost): they are where opportunities end, so they always grow;
   - which seller is overloaded compared with the rest;
   - which source brings volume without conversion;
   - how many of the opportunities created in the period are dormant now, worded that way.
3. Give a recommendation only when a number supports it. If the period is too short to tell, say so.

`query_opportunities` is only available to owners and admins. A member who asks gets the board for the opportunities they can see, from `list_opportunities` (by default their own; the business may let members see all). Tell them that team figures are for owners and admins.

## What the catalog does not cover

1. Call these in parallel:
   - `list_catalog_products` with the active status, paging up to 100.
   - `list_opportunities` created in the last 90 days, paging up to 100, to read what customers asked for (each row's title carries the demand).
2. Group the requested demand: destinations, dates, types of trip, or the vertical's equivalent. Set each group against the products that would cover it.
3. Report the demand that repeats without a product, with how many opportunities back it and the stages they ended in.

With one or two opportunities behind a gap, say it is a single case, not a trend. If you read only a sample (there were more than 100), say how many you read out of the total.
