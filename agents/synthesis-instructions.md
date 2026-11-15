# Synthesis Instructions

Read by any agent or skill before performing memory or task actions.

**Rules and templates:** this public repo (`MRD-DE/second-brain-public`)  
**Data writes:** private repo (`MRD-DE/second-brain`) only.

## Default behavior (no extra arguments)
When invoked with no additional instructions (e.g. bare `/second-brain` or “log this”):
- Perform a **complete synthesis of the entire current chat**.
- Focus exclusively on information, decisions, constraints, facts, and preferences that originated from **the human’s inputs**.
- Do not store agent interpretations, paraphrases that drift from the human’s words, or assumed intent.
- Quote or closely preserve the human’s actual statements for decisions and constraints.
- Produce atomic nodes under the correct scope in the **private** data repo.
- If scope is unclear, create a conversation-scoped node and flag for later assignment; do not guess a project.

## Steps
1. Read this file plus `README.md`, `templates/`, and `agents/chief-of-staff.md` from **this public repo**.
2. Extract only human-originated durable content from the full chat.
3. Run memory action against the **private** repo (`MRD-DE/second-brain`) on a `memory/conv-...` branch:
   - One primary conversation node.
   - Additional atomic nodes for distinct decisions, constraints, or facts.
   - Use frontmatter and templates from this public repo.
   - `related: []` unless the human explicitly confirmed a link.
4. If the human stated clear next actions, run task action on a `task/...` branch that `depends_on` the new memory node IDs.
5. Open PRs on the private repo. Do not merge. Chief of Staff is the only merger to `main`.
6. Reply with the PR links and a one-line summary of what was captured (human words only).

## Hard rules
- Isolation by default.
- Never auto-link on surface similarity.
- All content nodes go through PRs on the private repo; only the Chief of Staff merges them.
- If the human’s input is ambiguous, capture the ambiguity rather than resolving it.
- No personal data is ever written to this public repo.
