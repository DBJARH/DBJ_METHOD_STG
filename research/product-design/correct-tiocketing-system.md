
# Product Design

## Design Workflow

The correct classical order per Jacobson's OOSE is: use cases first, structural partitioning after. Use cases are purely behavioural — no structure, no domains, no subsystems inside the UC diagram.

#### Jacobson's OOSE methodology (1992)

Ivar Jacobson introduced use cases in *Object-Oriented Software Engineering* (1992). Key points:

- Use cases are **purely behavioural** — they describe interactions between actors and the system, with no structural implication
- The system boundary is a single rectangle; use cases sit inside it as a flat set — **no subsystems inside the UC diagram**
- Structural partitioning comes *after* use case analysis, in the design phase, using Jacobson's **Boundary / Control / Entity** object model
- **Domains as bounded contexts** are a DDD concept (Eric Evans, 2003) — a decade later. Jacobson had no "Domain Map" step

### Correct sequence of deliverables (strict Jacobson)

1. System-level Use Case diagram
2. Per-subsystem Use Case diagram (group by actor / functional area)
3. Per-use-case Robustness diagram (Boundary / Control / Entity objects)
4. Class/Entity model (derived from Entity objects in step 3)
5. Sequence Diagrams (derived from Control objects in step 3)

## Mockup Requirement: Simple Ticketing System

### Context

A small venue operator sells tickets to their own events (concerts, sports, shows). The system manages the full ticket lifecycle from creation to redemption. No third-party integration, no complex pricing — core CRUD only.

### Actors

- **Organizer** — creates and manages events and ticket inventory
- **Buyer** — browses events, purchases tickets
- **Staff** — scans / validates tickets at entry

### Constraints

- Single venue, single currency
- No partial refunds — cancel whole ticket only
- Ticket status: `available → reserved → sold → used / cancelled`
- No user authentication design required at this stage

---

# 1. System-level Use Case Diagram


```mermaid
---
title: Venue Ticketing Platform — System Use Cases Diagram
---
graph LR
    Organizer(("👤 Organizer"))
    Buyer(("👤 Buyer"))
    Staff(("👤 Staff"))

    subgraph VTP["Venue Ticketing Platform"]
        UC01(["UC-01: Create event"])
        UC02(["UC-02: Edit event details"])
        UC03(["UC-03: Cancel event"])
        UC04(["UC-04: Define ticket types & quantity"])
        UC05(["UC-05: Browse events"])
        UC06(["UC-06: Purchase ticket"])
        UC07(["UC-07: View my tickets"])
        UC08(["UC-08: Cancel ticket"])
        UC09(["UC-09: Validate ticket at entry"])
    end

    Organizer --- UC01
    Organizer --- UC02
    Organizer --- UC03
    Organizer --- UC04
    Buyer --- UC05
    Buyer --- UC06
    Buyer --- UC07
    Buyer --- UC08
    UC09 --- Staff
```

| ID | Actor | Use Case |
|----|-------|----------|
| UC-01 | Organizer | Create event |
| UC-02 | Organizer | Edit event details |
| UC-03 | Organizer | Cancel event |
| UC-04 | Organizer | Define ticket types and quantity |
| UC-05 | Buyer | Browse events |
| UC-06 | Buyer | Purchase ticket |
| UC-07 | Buyer | View my tickets |
| UC-08 | Buyer | Cancel ticket (refund request) |
| UC-09 | Staff | Validate ticket at entry |

---

# 2. Subsystems

Use cases grouped into subsystems by actor and functional area. Subsystems are structural units — not domains (DDD). This is the Jacobson design-phase partition that precedes the BCE robustness analysis.

```mermaid
---
title: Venue Ticketing Platform — Subsystems
---
graph TB
    VTP["Venue Ticketing Platform"]
    ES["EventsSubsystem"]
    TS["TicketsSubsystem"]

    VTP --> ES
    VTP --> TS
    ES -->|provides event & inventory data| TS
```

| Subsystem | Use Cases | Responsibility |
|-----------|-----------|----------------|
| EventsSubsystem | UC-01 – UC-05 | Event lifecycle and inventory management |
| TicketsSubsystem | UC-06 – UC-09 | Ticket purchase, ownership, and validation |

---

# 3. Use Case Diagrams per Sub System

## EventsSubsystem

```mermaid
graph LR
    Organizer(("👤 Organizer"))
    Buyer(("👤 Buyer"))

    subgraph EventsSubsystem
        UC01(["UC-01: Create event"])
        UC02(["UC-02: Edit event details"])
        UC03(["UC-03: Cancel event"])
        UC04(["UC-04: Define ticket types & quantity"])
        UC05(["UC-05: Browse events"])
    end

    Organizer --- UC01
    Organizer --- UC02
    Organizer --- UC03
    Organizer --- UC04
    Buyer --- UC05
```

## TicketsSubsystem

```mermaid
graph LR
    Buyer(("👤 Buyer"))
    Staff(("👤 Staff"))

    subgraph TicketsSubsystem
        UC06(["UC-06: Purchase ticket"])
        UC07(["UC-07: View my tickets"])
        UC08(["UC-08: Cancel ticket"])
        UC09(["UC-09: Validate ticket at entry"])
    end

    Buyer --- UC06
    Buyer --- UC07
    Buyer --- UC08
    UC09 --- Staff
```

---

# 4. Class / Entity Model per Subsystem

## Events Subsystem

```mermaid
classDiagram
  class Event {
    +id: UUID
    +name: string
    +date: DateTime
    +venue: string
    +status: EventStatus
    +create()
    +edit()
    +cancel()
  }
  class TicketType {
    +id: UUID
    +name: string
    +price: Money
    +totalQty: int
    +remainingQty: int
  }
  Event "1" --> "1..*" TicketType : defines
```

## Tickets Subsystem

```mermaid
classDiagram
  class Ticket {
    +id: UUID
    +ticketTypeId: UUID
    +buyerId: UUID
    +status: TicketStatus
    +purchasedAt: DateTime
    +purchase()
    +cancel()
    +validate()
  }
  class TicketStatus {
    <<enumeration>>
    AVAILABLE
    RESERVED
    SOLD
    USED
    CANCELLED
  }
  Ticket --> TicketStatus
```

---

# 5. Sequence Diagrams

## UC-06: Purchase Ticket

```mermaid
sequenceDiagram
  actor Buyer
  participant Catalogue
  participant Ticketing
  participant EventMgmt

  Buyer->>Catalogue: Browse events
  Catalogue->>EventMgmt: Get available events
  EventMgmt-->>Catalogue: Event list
  Catalogue-->>Buyer: Show events
  Buyer->>Ticketing: Select ticket type & purchase
  Ticketing->>EventMgmt: Reserve qty (decrement remainingQty)
  EventMgmt-->>Ticketing: Confirmed
  Ticketing-->>Buyer: Ticket issued (status: SOLD)
```

## UC-08: Cancel Ticket

```mermaid
sequenceDiagram
  actor Buyer
  participant Ticketing
  participant EventMgmt

  Buyer->>Ticketing: Cancel ticket
  Ticketing->>Ticketing: Set status = CANCELLED
  Ticketing->>EventMgmt: Restore qty (increment remainingQty)
  EventMgmt-->>Ticketing: Confirmed
  Ticketing-->>Buyer: Cancellation confirmed
```

## UC-09: Validate Ticket at Entry

```mermaid
sequenceDiagram
  actor Staff
  participant Ticketing

  Staff->>Ticketing: Scan ticket id
  Ticketing->>Ticketing: Check status == SOLD
  alt Valid
    Ticketing->>Ticketing: Set status = USED
    Ticketing-->>Staff: Entry granted
  else Invalid / already used
    Ticketing-->>Staff: Entry denied
  end
```

---

# 6. Physical Partitioning — Containers and Modules

One container, two processes, communicating over IPC. Each process owns its modules and its own persistence. The PlatformSubsystem modules are duplicated per process — no shared in-process state.

```mermaid
---
title: Venue Ticketing Platform — Physical Partitioning
---
graph TB
    subgraph VTP["«container» VenueTicketingPlatform"]

        subgraph EP["«process» EventsProcess"]
            EM["«module» EventManager"]
            TIM["«module» TicketTypeInventory"]
            EC["«module» EventCatalogue"]
            DB1["«module» Persistence"]
        end

        subgraph TP["«process» TicketsProcess"]
            TO["«module» TicketOrders"]
            TV["«module» TicketValidation"]
            NF["«module» Notifications"]
            DB2["«module» Persistence"]
        end

    end

    EP <-->|"IPC (inventory query / reservation)"| TP

    EM --> DB1
    TIM --> DB1
    EC --> DB1
    TO --> DB2
    TV --> DB2
    TO --> NF
```


- «executable» → «container» (the host — one machine or deployment unit)
- Two «process» nodes inside it — EventsProcess and TicketsProcess
- Each process has its own Persistence module — no shared DB access across the process boundary
- A single bidirectional IPC arrow between the two processes (inventory query when purchasing a ticket)
- Table organises by process

| Process | Module | Responsibility |
|---------|--------|----------------|
| EventsProcess | EventManager | Create, edit, cancel events |
| EventsProcess | TicketTypeInventory | Define ticket types, track remaining quantity |
| EventsProcess | EventCatalogue | Read-only event listing for buyers |
| EventsProcess | Persistence | EventsProcess data store |
| TicketsProcess | TicketOrders | Purchase and cancel tickets |
| TicketsProcess | TicketValidation | Validate and mark tickets used at entry |
| TicketsProcess | Notifications | Send confirmation / cancellation messages |
| TicketsProcess | Persistence | TicketsProcess data store |

> The two-process split is an internal implementation detail. From the outside — from any actor or external system — the container presents as a single unit with a single interface. The IPC boundary is invisible to callers.

## External View

```mermaid
---
title: Venue Ticketing Platform — External View
---
graph LR
    Organizer(("👤 Organizer"))
    Buyer(("👤 Buyer"))
    Staff(("👤 Staff"))

    VTP["«container»<br />VenueTicketingPlatform"]

    Organizer -->|manage events & inventory| VTP
    Buyer -->|browse, purchase, cancel tickets| VTP
    Staff -->|validate ticket at entry| VTP
```

## Frontend

The actors map directly to frontend pages. The frontend is a separate process (or static app) that calls the container's API — it is not part of the container.

```mermaid
---
title: Venue Ticketing Platform — Frontend to Container
---
graph LR
    Organizer(("👤 Organizer"))
    Buyer(("👤 Buyer"))
    Staff(("👤 Staff"))

    subgraph FE["«process» Frontend"]
        AP["Admin Pages\n(events & inventory)"]
        CP["Customer Pages\n(browse, purchase, cancel)"]
        SP["Scanning Page\n(entry validation)"]
    end

    VTP["«container»\nVenueTicketingPlatform"]

    Organizer --> AP
    Buyer --> CP
    Staff --> SP

    AP -->|API call| VTP
    CP -->|API call| VTP
    SP -->|API call| VTP
```
