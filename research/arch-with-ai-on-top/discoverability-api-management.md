<div style="float: right; margin: 1em; text-align: center;">
<img src="assets/icl_logo.png" width="64px" /><br/>
<a href="https://ironcodelabs.ai">&copy; Iron Code Labs Ltd</a>
</div>
<div style="clear: both;"></div>

# Discoverability & API Management

```mermaid
graph TD
    DEV[Developer / Consumer]
    APIM[API Manager<br/>rate limit · auth · versioning]
    REG[MCP Tool Registry<br/>service catalogue]
    AG[Agent]
    MCP1[MCP Server A]
    MCP2[MCP Server B]
    MCP3[MCP Server C]

    DEV --> APIM
    APIM --> AG
    AG --> REG
    REG --> MCP1
    REG --> MCP2
    REG --> MCP3
```

The MCP Tool Registry is your existing service catalogue (Consul, AWS Service Discovery, Azure APIM) — MCP protocol does not replace API management infrastructure. Rate limiting, auth, throttling, and versioning are enforced at the API Manager boundary, not inside Agents.

---

<div style="float: right; margin: 1em; text-align: center;">
<img src="assets/icl_logo.png" width="64px" /><br/>
<a href="https://ironcodelabs.ai">&copy; Iron Code Labs Ltd</a>
</div>
<div style="clear: both;"></div>
