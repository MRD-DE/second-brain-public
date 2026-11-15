---
name: second-brain
description: "Synthesize the current chat into the private second-brain repo by reading instructions from the public template repo. Use on /second-brain, 'log this', 'remember this', or 'synthesize this conversation'. Default is a complete synthesis focused on the human's inputs and decisions."
type: workflow
lifecycle: active
---

# Second Brain

Portable entry point. All detailed rules live in the public repo so the same skill works across platforms. Personal data stays in the private repo.

## Workflow

1. Read the current instructions from the **public** repo (do this every time):
   - `agents/synthesis-instructions.md` (primary)
   - `README.md`
   - `templates/`
   - `agents/chief-of-staff.md`

   Owner: `MRD-DE`, repo: `second-brain-public`, ref: `main`.

2. Follow those instructions exactly.
   - Default: complete synthesis of the entire current chat.
   - Focus on the human’s actual inputs and decisions. Preserve their wording.
   - Write nodes only to the **private** data repo (`MRD-DE/second-brain`) on branches and open PRs.
   - Never merge. Never write personal data to the public repo.

3. Return the PR link(s) and a one-line summary (human words only).

## Notes
- Public repo = rules + templates + this skill.
- Private repo = all actual memories, tasks, projects, preferences.
- If instructions diverge, the public repo’s synthesis-instructions.md wins for process; private repo wins for data location.
