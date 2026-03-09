## Liquid Foundation Models (LFM): An Enterprise Architect's Perspective

> The source [Interview](www.mckinsey.com/capabilities/quantumblack/our-insights/the-case-for-liquid-foundation-models)
>
> Ramin Hasani, CEO and cofounder of Liquid AI, discusses his company’s journey and impact and how the company’s much smaller models are tailor-made for devices, enabling the physical AI world.

**Technical Foundation**

After 35 years in commercial IT, I might recognize proper engineering when I see it. Liquid AI's human brain-inspired approach - achieving autonomous driving with minimal neurons versus millions of parameters - demonstrates sound systems thinking. This is optimization based on understanding the problem domain, not brute-force scaling.

Their hardware-in-the-loop methodology enabling deployment across GPUs, CPUs, and NPUs aligns with containerized solutions I prefer. True portability means abstracting hardware while optimizing for it.

**Enterprise Architecture Perspective**

From an EA standpoint, LFMs address a genuine AI architectural problem: **the forced coupling between AI capabilities and massive infrastructure dependencies**. This coupling violates fundamental architecture principles.

When business declares a product requirement - intelligent in-car assistance, real-time financial decisions - technology must implement without artificial constraints. Cloud-dependent AI introduces precisely such constraints: latency, connectivity requirements, privacy exposure, security vulnerabilities.

LFMs properly decouple business capability from infrastructure dependency. This aligns with my principle: products should decouple business from technology, with EA maintaining alignment without forced coupling.

**Architecture Pattern Recognition**

Hasani's hybrid future fits my advocacy for starting with modular systems and evolving to fully distributed only when necessary. The IT landscape requires consolidation where possible, distribution where required.

Their model maps correctly:
- **Edge/Device**: LFMs for operational, latency-critical, privacy-sensitive tasks
- **Cloud**: Frontier models for discovery, complex analysis
- **Principle**: Deploy intelligence at appropriate architectural tiers based on actual requirements

This is not distributed architecture for its own sake - it's recognizing different problem domains have different optimal solutions.

**Critique**

Several concerns require addressing before architectural commitment:

**Claims vs. Reality**: The "1,000x smaller with same quality" assertion needs rigorous validation. In three decades of coding and architecture, I've learned marketing often precedes measurable reality. These claims require:
- Proof-of-concept in actual enterprise environments with business-specific workloads
- Benchmarking against stated business requirements, not synthetic tests
- Total cost of ownership including retraining, maintenance, integration overhead

**Model Specialization Trade-offs**: Their emphasis on "specialized applications" raises questions. How much specialization is required? What's the cost of maintaining multiple specialized models versus one general model? Enterprise architects need clarity on the specialization-generalization spectrum.

**Maturity and Ecosystem**: Liquid AI is young. The transformer ecosystem has extensive tooling, debugging capabilities, operational knowledge, and talent pool. LFMs lack this maturity. What's the hidden cost of early adoption? Where are the operational runbooks, monitoring tools, optimization patterns?

**"First Principles" Skepticism**: Every technology wave claims "first principles" redesign. Often it's incremental improvement marketed as revolution. Their neural network approach draws from decade-old research - evolutionary, not revolutionary. The physics and biology inspiration is interesting but doesn't automatically translate to superior deployment.

**Hybrid Complexity**: Their hybrid cloud-edge model sounds architecturally clean but introduces operational complexity. How do you manage model versioning across edge and cloud? How do you handle training data synchronization? What about edge device updates at scale? These are non-trivial system architecture challenges.

**Conclusion**

Liquid AI demonstrates sound engineering principles applied to a genuine architectural gap. Their approach to building from first principles rather than incrementally scaling existing patterns is methodologically correct.

For enterprise architects, LFMs represent one tool in the toolkit, not a replacement strategy. The relevant question isn't "cloud or edge?" but "which tier for which capability?" This is the hybrid architecture we should design.

My support is conditional on verified proof-of-concept and actual enterprise validation in production environments. The concept is architecturally sound. The claims require demonstration. The operational maturity needs development.

I'll monitor their progress with professional interest but architectural skepticism.

**[D.B.J.](mailto:dbj@dbj.org)**  

Enterprise Software Architect  
TOGAF Registered since 2011