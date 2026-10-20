---
name: cargar-producto
description: "Use when the person wants to add, update, publish or pause a product in Trama's catalog from what they tell you or paste. Examples are «cargá esta excursión», «subí el paquete a Bariloche con estas salidas», «cambiá el precio del city tour», «quedan 3 lugares en la salida del 15», «publicalo», «sacalo del link de ofertas», or a pasted price list. It checks whether the product already exists, creates it as a draft, completes what publishing needs, edits prices, departures and stock, and publishes or pauses only when the person asks."
---

# Load and publish a catalog product

The sales agent offers customers only what is active in the catalog, with exactly the prices and dates loaded here. A wrong price reaches a customer as a promise. Terms are in [the glossary](references/glossary.md). [The working rules](references/working-rules.md) apply.

## A new product

1. Check that it does not exist yet: `list_catalog_products` with `query` set to the product's name or destination. If something similar exists, ask whether to update that one.
2. Call `create_catalog_product` with the common fields (`title`, `type`, `description`, `price`, `currency`, `departures`) and the rest in `attributes`. Trama validates `attributes` against the fields of that product type and says which field is wrong. Correct it and retry.
3. The product is always created as a draft. The result lists `missingForPublish`. Ask the person for those, in one message.
4. Publish only when they ask: `set_catalog_product_visibility` with `status: active`, and `showOnLink` if they want it on the offers link.

## An existing product

1. Find it with `list_catalog_products`, then read it whole with `get_catalog_product`.
2. Call `update_catalog_product` with only what changes. Stock of a departure or option goes in `variants` (`id` and `remaining`).
3. Fares and the calendar are replaced as a whole: if you send `fares` or `schedule`, send the complete list, including what does not change. Sending only the new item deletes the rest. Trama asks the person to confirm this kind of change; follow the confirmation steps in the working rules.

Pausing or hiding a product is `set_catalog_product_visibility`, up to 25 at a time.

## Keep in mind

- Prices, dates and conditions come from the person or from the material they pasted. Do not round, convert or fill in a price.
- Uploading a flyer, an itinerary file or a closing PDF is done in the app, or by sending the file to Tramy, Trama's assistant on WhatsApp (Tramy is the default name; the business may have renamed it, see the glossary). Files do not travel through this chat.
- Deleting a product is done in the app. Here, pausing it covers "sacalo".
- The offers link's design (colours, logo, texts) is edited in the app, under the offers link screen.
- Loading the catalog needs a role with catalog permission (owner, admin or operations). If the tools are not available to this person, say so.
