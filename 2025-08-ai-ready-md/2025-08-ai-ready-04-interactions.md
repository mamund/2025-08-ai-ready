# Standardize Interactions, Not Just Endpoints

* Predictability is the foundation of **autonomy**
* Machines struggle with inconsistent interaction models
* Standard patterns reduce cognitive load for agents

*Instructor note: frames Q1 (definition of the shift)*

---

# Roy Fielding on Architecture

> “A good architecture is not created in a vacuum.”
> — Roy Fielding, Co-author of HTTP & creator of REST

* Character anchor: highlights the need for **consistent conventions**
* Sets the stage for predictable machine–API interactions

*Instructor note: ties to Q2 (who inspired this shift & their perspective)*

---

# Why Consistency Matters

* Every inconsistency = new learning cost for agents
* Common operations (paging, retries, auth) need **uniform handling**
* Predictability allows **reuse of automation strategies**

*Instructor note: connects to Q3 (importance of predictability)*

---

# Examples of Inconsistency

* Different APIs paginate in different ways
* Error handling varies wildly (codes, formats)
* Authentication flows lack standard patterns

*Instructor note: addresses Q4 (examples of inconsistency)*

---

# Standard Error Handling

* Adopt **Problem Details for HTTP APIs (RFC 7807)**
* Provide clear **status codes, causes, remedies**
* Make errors predictable and machine-actionable

*Instructor note: links to Q5 (standardized error handling)*

---

# Retry and Fallback Patterns

* Define clear **timeouts and retry rules**
* Support **fallback strategies** for degraded performance
* Ensure machines know **when and how** to retry

*Instructor note: ties to Q6 (importance of retries and fallbacks)*

---

# Idempotence and Safety

* Use **PUT** for writes when possible
* Avoid overloading non-idempotent **POST**
* Idempotence = agents can retry without side effects

*Instructor note: supports Q7 (idempotence in design)*

---

# System-Wide Conventions

* Apply shared rules across **all APIs**
* Pagination, authentication, and state transitions should be uniform
* Don’t surprise agents with one-off solutions

*Instructor note: connects to Q8–Q9 (system-wide standards)*

---

# Benefits of Standardized Interactions

* Reduces friction for machine consumers
* Minimizes need for **custom workarounds**
* Makes large ecosystems more **composable and resilient**

*Instructor note: ties to Q10–Q12 (benefits of standardization)*

---

# Looking Ahead

* Standardization enables **trustworthy automation**
* Next: machines must also **discover** APIs effectively
* Unit 5 explores **ecosystem signals and discovery**

*Instructor note: frames Q13–Q15 (forward-framing into next shift)*
