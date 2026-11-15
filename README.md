# Second Brain — Public Templates & Skill

Public templates, skill definition, and synthesis instructions for the second-brain system.

**No personal data lives here.**  
Actual projects, memories, tasks, and preferences stay in the private repo: `MRD-DE/second-brain`.

## Contents
- `skill/SKILL.md` — thin portable skill (reads instructions from this public repo)
- `agents/synthesis-instructions.md` — default behavior and rules
- `templates/` — node templates (project, task, intersection)
- `agents/chief-of-staff.md` — supervisory agent definition

## Usage
Any agent or platform can:
1. Read `agents/synthesis-instructions.md` from this repo.
2. Follow it to synthesize a conversation.
3. Write the resulting nodes to the **private** data repo (`MRD-DE/second-brain`) on a branch and open a PR.

Default behavior (bare invocation): complete synthesis of the entire current chat, focused on the human’s actual inputs and decisions.

## Principles (summary)
- Isolation by default
- Memory action before task action
- All content writes on branches; only Chief of Staff merges to `main` of the data repo
- Never auto-link on surface similarity
- Preserve the human’s wording
