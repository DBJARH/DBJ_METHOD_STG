<div style="float: right; margin: 1em; text-align: center;">
<img src="assets/icl_logo.png" width="64px" /><br/>
<a href="https://ironcodelabs.ai">&copy; Iron Code Labs Ltd</a>
</div>
<div style="clear: both;"></div>

# Async & Large Payload Handling

```mermaid
sequenceDiagram
    participant NS as New System
    participant AG as Agent
    participant MQ as Message Queue
    participant MCP as MCP Server
    participant DB as Legacy Store

    NS->>AG: submit job (async)
    AG->>MQ: enqueue task
    AG-->>NS: job_id (immediate return)
    MQ->>MCP: dequeue & dispatch
    MCP->>DB: query / fetch
    DB-->>MCP: large result set
    MCP->>MQ: publish result ref (cursor / presigned URL)
    NS->>AG: poll job_id OR receive webhook
    AG-->>NS: result reference
    NS->>DB: fetch paginated / stream direct
```

Large datasets are never passed through the Agent layer. MCP Server returns a **result reference** — cursor token or presigned URL. The consumer fetches directly and paginates.

---

<div style="float: right; margin: 1em; text-align: center;">
<img src="assets/icl_logo.png" width="64px" /><br/>
<a href="https://ironcodelabs.ai">&copy; Iron Code Labs Ltd</a>
</div>
<div style="clear: both;"></div>
