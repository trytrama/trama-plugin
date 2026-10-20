---
name: cambios-masivos
description: "Use when the person asks Trama to change many opportunities at once, for example «pasá todas las de Marisa a Juan», «archivá las que no contestan hace un mes», «asigname todas las de Bariloche», «mové estas 15 a Perdido», «a todas las cotizadas de la semana dejales un seguimiento», «pausá todas las de Europa hasta marzo». It resolves the exact set first and shows it. It applies the change in batches, letting Trama's own confirmation be the only question when one is needed, and reports each item."
---

# Bulk changes, done safely

A bulk change done on the wrong set is the most expensive mistake available here: it is silent, and it touches many customers at once. The rule is to show the exact set first, then change exactly that set. Read [the working rules](references/working-rules.md) before starting, especially the confirmation section.

## 1. Resolve the set

- Translate their words into `list_opportunities` filters: `seller`, `stage`, `state`, `query`, `createdSince`, `inactiveForDays`. Page with `cursor` while `hasMore` is true, up to 100 opportunities.
- If part of the criterion is a judgment Trama cannot filter ("las que no contestan"), use the closest filter (`inactiveForDays`) and say which one you used.
- If they listed the opportunities themselves ("estas 15", names, references), resolve each one as the working rules describe, and report any that are ambiguous before changing anything.

## 2. Show the set and decide who asks

Show the count and the list, one line per opportunity (customer · demand · stage · seller). Show the first 20 if there are more, and say how many are left.

Then one question gets asked, at most:

- **Trama will confirm** when the change moves any opportunity to «Cotizado» or «Ganado», or touches more than 10 opportunities. In that case, send the call in the same turn you show the list. Trama's preview is the question; follow the confirmation steps in the working rules. Do not ask first.
- **Trama usually does not confirm** for 10 or fewer opportunities going to any other stage, or for field changes and follow-ups on 10 or fewer. If the person named the items, act. If you built the set from a filter, ask once ("¿Paso estas 8 a Perdido?"), then act on the yes.

"Usually", because Trama counts the opportunities written in the last 10 minutes, not only the ones in this call: after earlier changes, a set of 8 can still cross the line. If Trama asks after the person already said yes to you, show its preview, say in one line that it asks because of the changes made in the last few minutes, and ask that one question. Splitting a large change into several small calls does not avoid the confirmation either; the confirmation protects the person.

## 3. Apply it

- `move_opportunity` for stage, pause, archive and restore. `update_opportunity` for fields and for reassigning the seller. `add_opportunity_follow_up` for notes. Up to 100 items per call: send the whole set in one call.
- A confirmation covers exactly the call it came with: the same items, the same change. Repeating the call with anything different needs a new one. So send the whole set (up to 100) in one call: one preview, one question. Over 100, it goes in calls of up to 100 and each brings its own question; say that upfront.
- In a mixed call (some moves need confirmation, like «Cotizado» or «Ganado», and others don't), Trama writes the ones that don't right away and returns the others as waiting for confirmation. Tell the person which ones are done and which ones wait for their «sí»; after the «sí», repeat the same call with the token.
- Change only the set you showed. If the set moved in between (one changed stage, a new one appeared), leave those out and mention them.

## 4. Report

Summarize the counts, then the exceptions, one line each: "Pasé 14 a Perdido. 1 ya estaba ahí. 1 no la pude mover: es de Juan y no tenés permiso sobre las de otros." For a partial failure, retry only the failed items, after fixing the cause.

## Reassigning

Moving opportunities to another seller needs permission to manage other people's opportunities, and the receiving seller must accept manual assignment. If Trama refuses either, say which one and where it is set. Do not look for another way to do it.
