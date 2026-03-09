<div style="float: right; margin: 1em; text-align: center;">
<img src="assets/icl_logo.png" width="64px" /><br/>
<a href="https://ironcodelabs.ai">&copy; Iron Code Labs Ltd</a>
</div>
<div style="clear: both;"></div>

# Long-Running Workflows

AI Agents are distributed systems actors. The same patterns that govern long-running workflows in service-oriented architecture apply without modification — Agents just happen to be the orchestrators.

## Saga Pattern

```mermaid
sequenceDiagram
    participant AG as Agent (orchestrator)
    participant ES as Event / Saga Store
    participant MCP1 as MCP Server A
    participant MCP2 as MCP Server B

    AG->>ES: begin saga, checkpoint step 0
    AG->>MCP1: call tool A
    MCP1-->>AG: result A
    AG->>ES: checkpoint step 1
    AG->>MCP2: call tool B
    MCP2-->>AG: result B
    AG->>ES: checkpoint step 2 — saga complete

    note over AG,ES: On failure at any step,<br/>Agent replays from last checkpoint
```

Long-running Agent workflows use the saga pattern — exactly as in any distributed system. Checkpoints are written to the event store after each successful step. Failure triggers compensating transactions or replay from checkpoint.

---

## Correlation ID Pattern

```mermaid
sequenceDiagram
    participant C as Caller
    participant AG as Agent (orchestrator)
    participant ES as Event / Saga Store
    participant MCP1 as MCP Server A
    participant MCP2 as MCP Server B

    C->>AG: start workflow [correlationId: x1f4]
    AG->>ES: begin saga [correlationId: x1f4]
    AG->>MCP1: call tool A [correlationId: x1f4]
    MCP1-->>AG: result A [correlationId: x1f4]
    AG->>ES: checkpoint step 1 [correlationId: x1f4]
    AG->>MCP2: call tool B [correlationId: x1f4]
    MCP2-->>AG: result B [correlationId: x1f4]
    AG->>ES: saga complete [correlationId: x1f4]
    AG-->>C: done [correlationId: x1f4]
```

Every saga instance carries a **correlation ID** minted at creation and propagated unchanged through every step, every tool call, and every checkpoint. MCP servers forward it opaquely. The Agent and the event store are the only components that assign meaning to it — enabling full observability, targeted replay, and a reconstructable audit trail from a single query.

---

<div style="float: right; margin: 1em; text-align: center;">
<img src="assets/icl_logo.png" width="64px" /><br/>
<a href="https://ironcodelabs.ai">&copy; Iron Code Labs Ltd</a>
</div>
<div style="clear: both;"></div>
