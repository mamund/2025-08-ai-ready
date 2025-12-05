# AI-Ready API Course – Full Multiple Choice Quizzes (Units 1–9)

## Unit 1: The New Challenge

1. Which best describes the shift in API consumers driving the need for new design approaches?
   A. From HTTP/1.1 to HTTP/2
   B. From human developers to AI agents and autonomous systems
   C. From mobile apps to desktop applications
   D. From private APIs to public APIs

2. Why do traditional human-centered API designs often fail for machines?
   A. Machines cannot authenticate
   B. Machines cannot parse JSON
   C. Machines lack intuition and rely on explicit affordances
   D. Machines require XML, not JSON

3. Which of the following is NOT one of the five key shifts in the AI-ready API framework?
   A. From interfaces to intentions
   B. Make context machine-readable
   C. Standardize interactions
   D. Replace HTTP with gRPC

4. Who is credited with the quote, “We must design for the way users behave, not for how we would wish them to behave”?
   A. Douglas Engelbart
   B. Donald Norman
   C. Roy Fielding
   D. Ted Nelson

5. Which kind of thinking is most important for designing APIs for machine consumers?
   A. UI-driven design
   B. Systems thinking
   C. Waterfall methodology
   D. Monolithic architecture

6. Which is an example of an affordance in an API response?
   A. <form name="submitReview">...</form>
   B. A database table schema
   C. An HTML <div> for styling
   D. A version number in the footer

7. What is a common risk of failing to adapt APIs for machines?
   A. Slower human onboarding
   B. Inability of machines to safely and successfully use the API
   C. Reduced code readability for developers
   D. Increased visual complexity in dashboards

8. Which of the following best represents an AI-ready API design mindset?
   A. Focus exclusively on JSON format
   B. Plan for machine autonomy and discovery
   C. Use unique naming for each endpoint to avoid repetition
   D. Prioritize aesthetics of documentation over content

9. Which emerging role does the course highlight as important for API readiness?
   A. UI designers
   B. MCP (Machine-Centric Protocol) architects
   C. Database administrators
   D. DevOps engineers

10. What’s the primary reason metadata is important for AI agents?
   A. It enables human users to read faster
   B. It allows machines to infer meaning and context
   C. It makes endpoints more colorful
   D. It improves JSON compression

11. Which of these is NOT a characteristic of AI agents as API consumers?
   A. They rely on explicit affordances
   B. They can adapt to changing contexts
   C. They can interpret human sarcasm
   D. They benefit from predictable patterns

12. Which field in OpenAPI is highlighted for reflecting intent in operations?
   A. operationId
   B. summary
   C. tags
   D. description

13. Who is associated with the concept of hypertext and the phrase “Everything is deeply intertwingled”?
   A. Ted Nelson
   B. Roy Fielding
   C. Donald Norman
   D. Douglas Engelbart

14. What is a likely outcome when APIs use inconsistent pagination, error handling, and retries?
   A. Machines adapt instantly without issue
   B. Increased cognitive load for machines and failed tasks
   C. Faster machine execution
   D. Smaller payloads

15. The ultimate goal of the five key shifts is to:
   A. Reduce API costs
   B. Make APIs consumable by both humans and intelligent agents
   C. Eliminate the need for documentation
   D. Replace REST entirely

**Answer Key – Unit 1:** 1-B, 2-C, 3-D, 4-B, 5-B, 6-A, 7-B, 8-B, 9-B, 10-B, 11-C, 12-A, 13-A, 14-B, 15-B

---

## Unit 2: Shift 1 — From Interfaces to Intentions

1. What does shifting from interfaces to intentions primarily involve?
   A. Focusing on HTTP verbs only
   B. Designing operations to reveal user or agent goals
   C. Minimizing the number of endpoints
   D. Replacing JSON with XML

2. Machines benefit most from APIs that:
   A. Describe how the system is implemented
   B. Expose possible actions and their purposes
   C. Hide available actions to reduce complexity
   D. Use long, obscure endpoint names

3. An example of intention-revealing design is:
   A. GET /users
   B. POST /transaction
   C. <form name="submitReview">...</form>
   D. PUT /v1/data

4. The OpenAPI property useful for expressing intent is:
   A. operationId
   B. parameters
   C. summary
   D. tags

5. Which design tool is NOT mentioned for modeling affordances?
   A. ALPS
   B. TypeSpec
   C. Smithy
   D. WSDL

6. Why are HTTP commands alone insufficient for AI agents?
   A. They lack syntactic clarity
   B. They convey 'how' but not 'why'
   C. They only support JSON
   D. They require authentication

7. Affordances help machines:
   A. Find meaning in messages
   B. Reduce payload size
   C. Cache data locally
   D. Enforce stricter authentication

8. A state-transition description might look like:
   A. POST /updateUser
   B. "Move from draft to submitted using submitApplication"
   C. GET /listItems
   D. 200 OK

9. Who is associated with the idea of designing for actual user behavior?
   A. Donald Norman
   B. Roy Fielding
   C. Ted Nelson
   D. Christopher Alexander

10. Why rename endpoints and operations for intent?
   A. To make code longer
   B. To improve machine understanding of purpose
   C. To comply with HTTP spec
   D. To reduce endpoint count

11. Intention-driven design is most similar to which concept?
   A. Task-oriented UI design
   B. Database normalization
   C. Load balancing
   D. CSS styling

12. Which is an example of low-level, non-intentional naming?
   A. submitInvoice
   B. createOrder
   C. GET /users
   D. approveLoan

13. In the shift to intentions, what matters most?
   A. HTTP status codes
   B. User/agent goals
   C. Response time
   D. Caching policies

14. Machines differ from humans in API use because they:
   A. Can interpret ambiguous cues
   B. Need explicit, machine-readable actions
   C. Prefer HTML pages
   D. Ignore endpoint naming

15. Affordance modeling focuses on:
   A. Database indexing
   B. Describing available actions in a given state
   C. Error logging
   D. Load testing

**Answer Key – Unit 2:** 1-B, 2-B, 3-C, 4-A, 5-D, 6-B, 7-A, 8-B, 9-A, 10-B, 11-A, 12-C, 13-B, 14-B, 15-B

---

## Unit 3: Shift 2 — Make Context Machine-Readable

1. Why is context important for autonomous decision-making?
   A. It improves human UI experience
   B. It helps machines understand purpose and constraints
   C. It reduces server costs
   D. It speeds up HTML rendering

2. A key recent leap for AI engines came from:
   A. Reducing dataset size
   B. Expanding contextual data processing
   C. Fewer API calls
   D. Removing metadata

3. Metadata should describe:
   A. Only endpoint URLs
   B. Ownership, versioning, constraints, and relationships
   C. Database schema only
   D. User interface themes

4. Which format is mentioned for capability statements?
   A. XML Schema
   B. HTTP headers only
   C. Machine-readable formats with method, mediatype, fields
   D. Image metadata

5. The APIs.json specification helps with:
   A. Defining REST verbs
   B. Declaring API capabilities and metadata
   C. Formatting JSON for UI
   D. Minifying payloads

6. Domain affiliations help agents:
   A. Reduce storage use
   B. Reason about API relevance
   C. Encrypt data
   D. Generate documentation

7. Metadata endpoints might include:
   A. System ownership and terms of use
   B. CSS stylesheets
   C. Marketing slogans
   D. User avatars

8. Without context, APIs can become:
   A. More secure
   B. Opaque to machines
   C. Easier to maintain
   D. Faster

9. Who is quoted as saying 'The better we get at getting better, the faster we will get better'?
   A. Donald Norman
   B. Douglas Engelbart
   C. Ted Nelson
   D. Roy Fielding

10. Adding machine-readable context is part of which broader shift?
   A. From interfaces to intentions
   B. Make context machine-readable
   C. Standardize interactions
   D. Enable discovery

11. Capability statements should include:
   A. Endpoint colors
   B. Field definitions, HTTP methods, actions
   C. UI screenshots
   D. Marketing videos

12. Why embed ownership metadata?
   A. For branding
   B. To aid compliance and trust for agents
   C. To improve SEO
   D. To speed up server responses

13. Without domain descriptions, agents may:
   A. Misclassify APIs
   B. Perform faster
   C. Reduce CPU load
   D. Display UI incorrectly

14. Versioning policies in metadata help agents:
   A. Cache more data
   B. Know change schedules
   C. Reduce payload size
   D. Encrypt responses

15. Which is NOT an example of machine-readable context?
   A. Capability statements
   B. Domain tags
   C. Ownership metadata
   D. Button color

**Answer Key – Unit 3:** 1-B, 2-B, 3-B, 4-C, 5-B, 6-B, 7-A, 8-B, 9-B, 10-B, 11-B, 12-B, 13-A, 14-B, 15-D

---

## Unit 4: Shift 4 — Enable Discovery Through Ecosystem Signals

1. Why is discovery critical for machine consumers?
   A. They can't browse portals like humans
   B. It improves SEO rankings
   C. It reduces JSON size
   D. It makes documentation prettier

2. Which is NOT a recommended discovery method?
   A. Register APIs in searchable catalogs
   B. Provide cross-linked documentation
   C. Use consistent hypermedia links
   D. Hide endpoints to prevent use

3. An example of a registry for API discovery is:
   A. Postman public API network
   B. JSON minifier
   C. CSS framework
   D. SSL certificate

4. Hypermedia affordances help machines by:
   A. Styling web pages
   B. Navigating and discovering capabilities
   C. Encrypting payloads
   D. Reducing server load

5. The phrase 'Everything is deeply intertwingled' is attributed to:
   A. Ted Nelson
   B. Roy Fielding
   C. Donald Norman
   D. Christopher Alexander

6. What is progressive disclosure in APIs?
   A. Revealing capabilities gradually through linked resources
   B. Hiding metadata permanently
   C. Providing all data in one payload
   D. Encrypting capabilities

7. Adding semantic tags to APIs supports:
   A. Machine classification
   B. Faster HTTP responses
   C. Reduced storage
   D. Code obfuscation

8. Which publication provides examples of hypermedia patterns?
   A. RESTful Web API Patterns and Practices Cookbook
   B. CSS Design Handbook
   C. JavaScript: The Good Parts
   D. The Art of SEO

9. Machines that cannot discover an API will:
   A. Guess the endpoints
   B. Fail to use it effectively
   C. Cache responses
   D. Switch to XML

10. Cross-linked documentation aids:
   A. Humans and machines in navigation
   B. Only SEO crawlers
   C. UI designers
   D. Load balancers

11. A self-describing endpoint provides:
   A. Schema and capabilities in its response
   B. User profile pictures
   C. HTML-only content
   D. Randomized URLs

12. Consistent hypermedia signals might include:
   A. Links to home, collection, and item resources
   B. Different link formats for each endpoint
   C. Color-coded HTML
   D. Encrypted URLs

13. Publishing description documents to shared registries helps:
   A. Only marketing teams
   B. Centralize and standardize access
   C. Reduce payload size
   D. Improve UI color schemes

14. Which is NOT an ecosystem signal?
   A. Domain tags
   B. Hypermedia links
   C. CSS stylesheets
   D. Registry listings

15. Discovery methods should be applied:
   A. Consistently across APIs
   B. Only on core endpoints
   C. Randomly to test adaptability
   D. Only when requested by clients

**Answer Key – Unit 4:** 1-A, 2-D, 3-A, 4-B, 5-A, 6-A, 7-A, 8-A, 9-B, 10-A, 11-A, 12-A, 13-B, 14-C, 15-A

---

## Unit 5: Shift 5 — Observe, Adapt, and Iterate

1. Why is adaptation important for APIs consumed by machines?
   A. Machine usage patterns evolve
   B. Humans demand it
   C. To reduce HTML size
   D. To change JSON to XML

2. A 'greedy algorithm' in AI agents means:
   A. They seek immediate local optimization
   B. They hoard data
   C. They refuse to release memory
   D. They encrypt payloads

3. Observing machine failures can:
   A. Reveal improvement opportunities
   B. Slow API performance
   C. Reduce server uptime
   D. Confuse developers

4. Telemetry should monitor:
   A. Agent and human developer usage
   B. Only UI clicks
   C. Only JSON responses
   D. CSS styling

5. Repeated errors and fallback usage are:
   A. Signals to adapt API design
   B. Unavoidable noise
   C. Signs to remove endpoints
   D. Normal and ignorable

6. Christopher Alexander is known for:
   A. A Pattern Language
   B. The HTTP spec
   C. Hypertext invention
   D. The TCP/IP stack

7. Why treat usage patterns as adaptation signals?
   A. APIs should evolve like living systems
   B. It helps SEO
   C. It reduces payload size
   D. It improves CSS design

8. Machine consumers differ from static scripts because they:
   A. Adapt and change over time
   B. Never change
   C. Ignore metadata
   D. Only run once

9. An API that ignores adaptation will:
   A. Fall out of sync with client needs
   B. Stay perfectly optimal
   C. Load faster
   D. Reduce server costs

10. Which is a practical step for adaptation?
   A. Implementing iterative improvements
   B. Locking API forever
   C. Removing telemetry
   D. Hiding errors

11. Fallback usage indicates:
   A. Agents are struggling
   B. The API is flawless
   C. Endpoints are unused
   D. UI is outdated

12. Greedy algorithms can cause agents to:
   A. Miss better long-term solutions
   B. Increase context awareness
   C. Store more metadata
   D. Improve SEO

13. Monitoring should focus on:
   A. Where agents succeed and fail
   B. CSS changes
   C. UI button placement
   D. Server wallpaper

14. Which tool category supports adaptation?
   A. Observability platforms
   B. Photo editors
   C. Word processors
   D. CSS preprocessors

15. Adaptation in APIs parallels:
   A. Evolution in nature
   B. Static code compilation
   C. Database indexing
   D. Sorting algorithms

**Answer Key – Unit 5:** 1-A, 2-A, 3-A, 4-A, 5-A, 6-A, 7-A, 8-A, 9-A, 10-A, 11-A, 12-A, 13-A, 14-A, 15-A

---

## Unit 6: Introduction to Machine-Centric Protocols (MCPs)

1. MCPs primarily serve as:
   A. Adapters for machine consumption
   B. UI styling guides
   C. Database schemas
   D. DNS resolvers

2. An MCP manifest should include:
   A. Intent names, descriptions, parameters
   B. HTML layout
   C. CSS color codes
   D. SEO tags

3. Legacy APIs can be made agent-friendly by:
   A. Building MCP wrappers
   B. Changing to XML
   C. Removing endpoints
   D. Hiding docs

4. MCPs translate:
   A. Intent and context into machine-consumable functions
   B. HTML into CSS
   C. Java into Python
   D. JSON into CSV

5. Which is NOT part of MCP design?
   A. Return schemas
   B. Parameter descriptions
   C. Marketing slogans
   D. Action names

6. MCPs help agents:
   A. Operationalize intent
   B. Improve page speed
   C. Change UI color
   D. Minify JSON

7. The benefit of MCPs is:
   A. Bridging human-focused APIs to machine needs
   B. Reducing disk space
   C. Improving font rendering
   D. Obfuscating code

8. MCP wrappers often require:
   A. No changes to legacy API logic
   B. Rewriting entire system
   C. CSS updates
   D. SEO audits

9. An MCP manifest is typically:
   A. Machine-readable
   B. Human-only readable
   C. Printed
   D. Encrypted

10. Which is a core element of MCP design?
   A. Intent mapping
   B. Image compression
   C. CSS classes
   D. HTML forms

11. MCPs align with which shift?
   A. From interfaces to intentions
   B. Enable discovery
   C. Observe and adapt
   D. Make context machine-readable

12. MCPs are important because:
   A. They make APIs accessible to autonomous agents
   B. They improve human UI
   C. They change DNS
   D. They increase CSS complexity

13. An MCP wrapper might include:
   A. Authentication flow
   B. UI stylesheet
   C. Marketing pitch
   D. Server wallpaper

14. Who benefits from MCP adoption?
   A. Machine agents and API providers
   B. Only web designers
   C. Only SEO teams
   D. Only database admins

15. Which type of API benefits most from MCP wrappers?
   A. Legacy APIs
   B. Static HTML pages
   C. CSS frameworks
   D. CDN endpoints

**Answer Key – Unit 6:** 1-A, 2-A, 3-A, 4-A, 5-C, 6-A, 7-A, 8-A, 9-A, 10-A, 11-A, 12-A, 13-A, 14-A, 15-A

---

