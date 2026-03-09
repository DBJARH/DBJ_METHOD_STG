<div style="float: right; margin: 1em; text-align: center;">
<img src="assets/icl_logo.png" width="64px" /><br/>
<a href="https://ironcodelabs.ai">&copy; Iron Code Labs Ltd</a>
</div>
<div style="clear: both;"></div>

# Stateless Agent & State Externalisation

```mermaid
graph LR
    AG1[Agent instance 1]
    AG2[Agent instance 2]
    AG3[Agent instance 3]
    SS[(Session Store<br/>Redis)]
    ES[(Event / Saga Store)]
    LB[Load Balancer]

    LB --> AG1
    LB --> AG2
    LB --> AG3
    AG1 --- SS
    AG2 --- SS
    AG3 --- SS
    AG1 --- ES
    AG2 --- ES
    AG3 --- ES
```

Agent instances are stateless. All workflow state, session context, and saga checkpoints are externalised. Any instance can handle any request. Scale horizontally without constraint.

---

<div style="float: right; margin: 1em; text-align: center;">
<img src="assets/icl_logo.png" width="64px" /><br/>
<a href="https://ironcodelabs.ai">&copy; Iron Code Labs Ltd</a>
</div>
<div style="clear: both;"></div>
