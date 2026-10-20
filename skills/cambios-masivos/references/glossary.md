# Trama glossary

Trama is a CRM with AI agents for tourism businesses: travel agencies, tour operators, inbound operators, lodgings, wineries and other places that sell visits, school trip operators, and a few businesses outside tourism. The person you are helping works at one of those businesses: an owner, an admin, a seller or someone in back office. They are never the end customer.

Terms in «guillemets» are the words the person sees on screen in Spanish. Use them when you write in Spanish, and translate the idea, not the label, in other languages.

## People and roles

- **Organization**: the business. Everything in Trama belongs to one organization, and the person only sees their own.
- **Roles**: **owner** «Dueño», **admin** «Administrador» and **member** «Miembro». Owners and admins see the whole team. By default a member sees and changes only their own opportunities and the customers assigned to them, plus what nobody holds yet; the owner can open that to everything in the business's settings, so what a member sees depends on the business. **Operations** «Operaciones» is not a base role but an add-on to one: it opens the back-office screens (catalog, offers link, ads).
- **Seller** «Vendedor»: not a role, a badge on the members who take part in assigning opportunities (in the rotation, or chosen by hand). A member without it can still work opportunities.
- **Assigned seller**: the person who holds an opportunity. "Their" numbers and "the business's" numbers are different figures; always say which one you are giving.

## Opportunities

- **Opportunity** «oportunidad»: one sales case, for one customer, with a stage, an assigned seller and what the customer wants (the demand: a destination, a date, a course; see the verticals table). Sellers also say «consulta», «la tarjeta» or the customer's name; all mean the opportunity. In what you write, the word is «oportunidad», never "lead". The one exception is Meta Ads reporting, where "lead" is the Ads Manager term.
- **Short reference**: `#` followed by four characters, like `#H7KM`, meant to be read out loud. The characters are digits 2 to 9 and consonants (no vowels, no 0, 1, O, I or L, so it is never confused when dictated). It is unique within the business and identifies exactly one opportunity. Written without the `#` or in lowercase, it is the same reference.
- **Stage** «etapa», shown as a **column** on the board. The default columns are «Por atender» (new, nobody worked it yet), «En contacto» (contacted), «Cotizado» (quoted), «Ganado» (won) and «Perdido» (lost). Each business can rename them and add its own, so always use the name Trama returns.
- **Moving to «Cotizado» or «Ganado»** reports a conversion to Meta Ads, which trains the ads and cannot be withdrawn. «Ganado» also creates the sale record «ficha de venta» that back office completes. Every other move stays in the history and can be undone.
- **Off the board**: an opportunity can be **paused** «pausada» (the customer said "write me in October"; it keeps its stage, Trama stops reminding about it, and it can return on a date), **archived** «archivada» (deleted for good after 30 days; until then it can be restored) or **dormant** «dormida» (no activity for 30 days by default, a number each business can change; never deleted). **Inactive** «Sin actividad» is not a state: it is a filter on the board that shows the opportunities still there with no activity for a number of days (7 by default).
- **Temperature** «Caliente / Tibio / Frío»: a score the agent computes mostly from how complete the opportunity's data is (destination, dates, travellers, nights, departure city, a budget signal), adjusted by the customer's intent signals and how engaged they are in the conversation. A person on the team can override it by hand. A hot opportunity is ready to quote, not necessarily ready to buy.
- **Amounts**: an opportunity carries a quoted or won amount with its currency. Amounts are read from the record, never computed or converted.

## Follow-ups, reminders and pending work

- **Follow-up** «seguimiento»: a dated note in the opportunity's history about what happened with the customer and what comes next ("le mandé la propuesta, espera a la esposa"). The whole team reads it. Its author, an owner or an admin can edit or delete it in the app. From here a follow-up is not edited: a correction is a new follow-up.
- **Reminder** «recordatorio»: a task for one person, with a date and time ("recordame llamar a Ana el jueves a las 11"). If the person gives a day and no time, it goes at 09:00, and you tell them so they can change it. It may point to an opportunity but does not change it. It reaches the person by WhatsApp and email, and can be rescheduled, marked done or dismissed.
- The difference matters: "le escribí, espera respuesta" is a follow-up; "recordame escribirle el lunes" is a reminder. A sentence can carry both.
- **Pending work** «pendientes»: reminders that are due, follow-ups whose date passed or is today, and the action items Trama flags (a quote with no follow-up, an old quote, a high-value opportunity, a hot opportunity nobody took).
- **Mission Control**: the home screen, with three tabs. «Mi día» is the person's own to-do view. The **summary** «Resumen» is a stored snapshot, with its figures and their definitions: the day is split into three parts (morning until 12, midday until 18, evening), and the snapshot is taken the first time someone opens it in each part, then reused until the next one. It is a photo of that moment, not the live state, so it can differ from what Trama shows now. «Métricas» is the third tab, with the business's figures.

## Customers and conversations

- **Customer** «cliente»: the person or company that buys, with contacts (phones, emails), tags, a service status and a commercial summary. What the customer told the agent (preferences, constraints) is stored on the customer record and is the customer's own words.
- **Do not contact** «No quiere que lo contactemos»: the customer asked not to be written to. No follow-ups or campaigns go out to them.
- **Conversation** «conversación»: a thread with a customer in «Mensajes», the inbox for every channel.
- **Channels**: WhatsApp, Instagram, Messenger, TikTok direct messages and the web widget. A WhatsApp number is either **Direct** «Directo» (a number used only through Trama, where the AI agent answers) or **Assisted** «Asistido» (a number the business already uses in the WhatsApp Business app, connected to Trama without leaving the phone). An assisted number may be a seller's phone or a shared business line, and may have a member assigned or none. Whoever uses the phone keeps using it, and messages sent from it are theirs. It starts without an agent; the business decides whether one answers there. Sellers often call these numbers "los celulares de los vendedores".
- **Team took it** «Equipo»: someone from the team took over a conversation; the agent stays silent with that customer until it is handed back. If nobody hands it back, the agent takes it again when the customer writes after 14 days with the team in control, except on an assisted number that has a member assigned, where the team keeps it.

## The AI agents

- **The inbound agent** «el agente»: the AI that answers customers on the channels, asks what it needs, and offers the catalog.
- **Handoff** «derivar»: when the agent has the minimum data the business asked for, it passes the opportunity to a human seller. Assignment rules decide who gets it.
- **Agent question** «consulta del agente»: when one of the business's rules says to ask first, the agent pauses the customer conversation and asks a person on the team. The person's answer goes back to the customer through the agent, in the business's name.
- **The internal assistant**: the assistant the team talks to on WhatsApp and in the app, over this same data. Its default name is «Tramy», and the business can rename it, so use the name the person uses. Files (a quote PDF, a flyer, an itinerary) reach Trama through the app or by sending them to this assistant in its WhatsApp chat.

## Catalog, quotes and campaigns

- **Catalog** «Catálogo»: the products the business sells (packages, excursions, stays, courses; see the verticals table). A product is a **draft** «borrador», **active** or **paused**. The agent only offers active products. A product can also be shown or hidden on the **offers link** «Link de ofertas», the public page of the catalog; its design is edited in the app, not by chat.
- **Quote** «cotización»: a proposal published with a public link. Trama tracks whether and when the customer opened it. Recording that a quote was sent is moving the opportunity to «Cotizado» with the amount and leaving a follow-up.
- **Campaign** «campaña»: a mass WhatsApp send using a template Meta approved. Each message costs money and cannot be recalled. Campaigns are reviewed and sent by a person in «Campañas».

## Verticals

Each organization has one vertical, which changes the nouns. When the data does not say which one it is, use the neutral word ("cliente", "producto") instead of guessing.

| Vertical | The buyer | The business | What the demand is | What the catalog holds |
|---|---|---|---|---|
| Travel packages | pasajero | la agencia | destino, fechas, pasajeros | paquetes, excursiones, servicios |
| Travel insurance | pasajero | la agencia | destino, fechas, pasajeros | coberturas, asistencias |
| Wholesale travel | cliente (another agency) | la operadora | servicio, fechas, pasajeros | excursiones, traslados, hotelería, guías |
| Wholesale travel insurance | cliente (another agency) | la empresa | destino, fechas, pasajeros | coberturas, asistencias |
| Experiences | visitante | el establecimiento | fecha de visita, turno, personas | visitas, degustaciones, actividades |
| Lodging | huésped | el alojamiento | fechas, noches, huéspedes | estadías, unidades, programas |
| School groups | organizador | la operadora | colegio, grado, alumnos, fecha | programas, jornadas, viajes de egresados |
| Courses | interesado | la institución | curso, modalidad, inicio | cursos, programas, talleres |
| General and software sales | cliente | la organización | interés | productos, servicios |
