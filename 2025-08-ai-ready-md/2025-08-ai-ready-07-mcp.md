# Introduction to Machine-Centric Protocols (MCPs)

* MCPs act as **adapters** between existing APIs and machine needs
* Bridge the gap: **intent + context → structured function calls**
* Make legacy APIs **agent-friendly without full redesign**

*Instructor note: frames Q1 (definition of MCPs)*

---

# Jon Postel on Implementations

> “Be conservative in what you send, be liberal in what you accept.”
> — Jon Postel

Why: Postel embodied pragmatic interoperability. His principle maps beautifully to MCPs as translation layers that help systems work together safely.

Framing: MCPs are pragmatic gateways, following Postel’s spirit: adapt to reality, smooth the rough edges, and keep things working.

# Why MCPs Matter

* Many APIs today are **not AI-ready**
* MCPs provide a **compatibility layer** for agents
* Let organizations adopt machine-driven use **incrementally**

*Instructor note: ties to Q2 (why MCPs are needed)*

---

# Core Idea of MCPs

* MCP describes **intentions** as functions
* Functions include **names, descriptions, parameters, return schemas**
* Agents can call MCP-wrapped APIs without prior documentation

*Instructor note: connects to Q3 (MCP function model)*

---

# Example: Wrapping a Legacy API

* Legacy endpoint: `POST /applications`
* MCP manifest: `submitApplication(name, email, docs)`
* Return schema: structured success/failure response
* Agents now see the **purpose**, not the plumbing

*Instructor note: supports Q4–Q5 (example of MCP wrapping)*

---

# MCPs and Intent Alignment

* MCPs encode **goal-oriented actions**
* Clarify what an API **enables** (e.g., “sendInvoice”)
* Reduce reliance on trial-and-error LLM interpretation

*Instructor note: links to Q6 (intent as part of MCP design)*

---

# MCPs and Context Integration

* Include **metadata**: ownership, constraints, versioning
* Help agents reason about **fit and relevance**
* Extend discoverability beyond raw endpoints

*Instructor note: ties to Q7–Q8 (context in MCPs)*

---

# Benefits of MCP Wrappers

* Faster agent onboarding
* Increased **discoverability and composability**
* Preserve investment in **existing APIs**

*Instructor note: connects to Q9–Q10 (benefits of MCPs)*

---

# Challenges of MCP Adoption

* Requires **upfront design effort** for manifests
* Potential drift between API and MCP descriptions
* Need for **governance** to ensure accuracy

*Instructor note: addresses Q11 (challenges and limitations)*

---

# MCPs in Practice

* Used by LLM frameworks to expose tools safely
* Gaining traction in **autonomous orchestration engines**
* Seen as a bridge to **future affordance-driven designs**

*Instructor note: ties to Q12–Q13 (current uses of MCPs)*

---

# Looking Ahead

* MCPs are a **stepping stone**, not the final destination
* Next: advanced models (ALPS, TypeSpec, Smithy)
* Unit 8 explores the **future of adaptive ecosystems**

*Instructor note: frames Q14–Q15 (forward-framing into next unit)*

