# Requirement: Legacy WIN32 system to be modernized. Web front end to be added. It is one monolith. It has GUI also inside.

## Vision

### Platform

- Target: Azure Cloud 
  - Azure VM's can host any kind of WIN legacy systems
  - Full complement of distribution and security features
  - Loggin, Backups, Monitoring -- all is in the Box
  

### Data Layer

- Target: Azure SQL (important: this is NOT Server)
  - fully managed 
  - Critical detail: what is the current DB? 

### Application Layer
  
- Target: Web Server in a container (.NET C#, because it can integrate with all win32 legacy in the back, it is fylly supported and is a native Cloud citizen)
  - Why container?
    - It is easy to deploy 
    - It  can be horizontaly scaled for resilience and scalability

### WEB UI: HTMX

  - much simpler than any other html front end
  - mature and proven
  - does not require specialized JavaScript/Type Script resources
  - Mobile interface is possible but nat native mobile gui

>**Important**
Native Mobile UI requirement will basically explode the complexity

# Application/System Architecture Concepts

Classic **Strangler Fig** pattern applies here. The web front end becomes the entry point; the Win32 monolith is progressively hollowed out from behind it.

**Key architectural decision:** Do NOT attempt to expose the Win32 GUI directly. Treat the existing monolith as a black box with a new service boundary cut in front of it.

---

**Phase 1 — Anti-Corruption Layer (ACL)**

Introduce a thin backend service (the ACL) that wraps the Win32 monolith:

```
Browser → Web Frontend → ACL (REST/JSON) → Win32 Monolith (COM/RPC/named pipes/CLI)
```

- ACL runs as a Windows Service or containerised .NET/Node process on the same host
- Communication to Win32 via whatever IPC the monolith already exposes — COM automation, named pipes, CLI invocation, or DB-level if nothing else
- ACL owns the HTTP API contract; the monolith sees no change

---

**Phase 2 — Strangler Fig extraction**

Once the ACL is in place, each functional domain can be extracted one at a time:

```
Browser → Web Frontend → API Gateway
                              ├─ New Service A (containerised)
                              ├─ New Service B (containerised)
                              └─ ACL → Win32 residual (shrinking)
```

Extract modules in order of: highest business value first, lowest coupling second.

---

**Constraints to validate before starting:**

| Question | Why it matters |
|---|---|
| Does the Win32 monolith have any existing IPC surface? | Determines ACL integration cost |
| Is state held in a DB or in-process? | In-process state = harder extraction |
| Is the GUI tightly coupled to business logic? | Likely yes — plan for logic duplication during transition |
| Who owns the Win32 source? | Rewrite risk vs. wrap risk |

---

**Recommended stack for ACL** (pragmatic, containerisable):

- .NET 8 minimal API — native Win32 interop, Dockerisable on Windows containers
- Or Node.js if the monolith exposes a DB or file interface only

**Web frontend** — decouple completely from day one. SPA (React/Vue) or server-rendered — that decision is independent of the modernisation path.

---

The guiding principle: **the monolith shrinks, it does not get rewritten in one shot.** The ACL protects the new system from the old system's semantics until extraction is complete.

**QUESTION**: What is the Win32 monolith's existing IPC surface, if any?

<!-- Standard Footer -->
<div style="clear: both;"></div>
<div style="float: center; margin: 1em; text-align: center;">
<img src="../../assets/icl_logo.png" width="64px" /><br/>
<a href="https://ironcodelabs.ai">&copy; Iron Code Labs Ltd</a>
</div>