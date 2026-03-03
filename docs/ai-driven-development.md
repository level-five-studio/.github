# AI-Driven Development

AI is a first-class citizen of our workflow — not a novelty, but a core part of how we design, build, review, and ship.

---

## What "AI-Driven" Means for Us

- AI tools are always available and actively used at every stage of the development lifecycle.
- We maintain **AI instructions and agent configurations** in the repo so the entire team is working with the same shared context.
- We continuously refine our prompts, agent configs, and AI workflows the same way we refine code.

---

## Where AI Shows Up

| Stage | How We Use AI |
|---|---|
| **Planning** | Drafting specs, breaking down issues, sizing work |
| **Coding** | Inline completions, refactors, boilerplate generation |
| **Code Review** | AI-assisted review before human review |
| **Testing** | Generating test cases, spotting edge cases |
| **Documentation** | Drafting and maintaining docs alongside code |
| **CI/CD** | AI-powered failure analysis in pipeline logs |
| **Debugging** | Root-cause analysis with AI assistance |

---

## Agent Configurations

AI agent configs and instruction files live inside the relevant repository (e.g. `.github/agents/`, `.cursor/rules`, or tool-specific config files).  
When you clone a repo, you automatically inherit the shared AI context.  

Keep agent configs up to date — they are as important as the code.

---

## Skills We Expect

Every team member should be comfortable:

- Writing clear, context-rich prompts
- Iterating on AI output rather than accepting it blindly
- Maintaining and improving AI instruction files
- Recognising the limits of AI-generated code (always review, always test)

---

## Tools We Use

We are tool-agnostic at the agent level — the goal is the best outcome, not loyalty to a single vendor.  
Current primary tools include GitHub Copilot, Cursor, and Claude, among others.

---

> Next: [Communication & Planning →](communication-and-planning.md)
