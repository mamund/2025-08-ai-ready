# From Interfaces to Intentions

* Machines don’t need UI — they need meaning
* Shift from **mechanics** (GET, POST) to **intentions** (what can be done)
* Clarifying “what” and “why” makes APIs consumable by agents
  *Instructor note: frames Q1 (definition of the shift)*

---

# Donald Norman on Design

> “We must design for the way users behave, not for how we would wish them to behave.”
> — Donald Norman, NN/g Board Member

* Character anchor: emphasizes designing for real behavior, not idealized models
* Sets the stage for **intent-driven API design**
  *Instructor note: ties to Q2 (who inspired the shift & their perspective)*

---

# Why Interfaces Fall Short

* HTTP verbs describe **how**, not **why**
* Endpoint names often expose implementation, not goals
* Machines can’t infer meaning from mechanics alone
  *Instructor note: ties to Q3 (limits of low-level verbs)*

---

# The Role of Affordances

* Affordances = cues that signal **possible actions**
* Humans see affordances visually (buttons, menus)
* Machines need **explicit affordances** in APIs (forms, links, labels)
  *Instructor note: connects to Q4 (what affordances mean for APIs)*

---

# Example: Human vs Machine View

* Human developer: reads docs, experiments with endpoints
* Machine agent: requires **embedded cues** in responses
* Example: `POST /review` (mechanics) vs `<form name="submitReview">` (intent)
  *Instructor note: supports Q5 (example of intent-based design)*

---

# Designing for Intent

* Use **operationId** fields that reveal purpose (e.g., `submitApplication`)
* Provide **state transitions** (“draft → submitted”) in docs/metadata
* Label actions by **goal**, not by internal implementation
  *Instructor note: links to Q6–7 (design strategies for intent)*

---

# Tools for Intent Modeling

* ALPS: capture states & transitions
* TypeSpec and Smithy: model affordances in specs
* Help machines know **what’s possible at each state**
  *Instructor note: ties to Q8 (tools for modeling intentions)*

---

# Why This Matters for Machines

* Intent cues reduce **trial-and-error failures**
* Agents can **plan next steps** more effectively
* Enables **autonomous orchestration** across APIs
  *Instructor note: supports Q9 (importance of intent for autonomy)*

---

# Pitfalls to Avoid

* Overloading `POST` for all actions
* Exposing back-end tables as endpoints
* Depending only on external docs instead of in-response metadata
  *Instructor note: connects to Q10 (common mistakes to avoid)*

---

# Looking Ahead

* Intention-driven design is the **foundation** of AI-ready APIs
* Next: machines also need **context**, not just intent
* Unit 3 explores how to make that context machine-readable
  *Instructor note: frames Q11–15 (forward-framing into next shift)*
