<!-- BEGIN REGENT ROLLOUT REVIEW -->
## Code Review Rules

### Human and agent guidance drift

For every code review, read `.agents/skills/rollout-guidance-check/SKILL.md` and assess the diff's guidance
impact, even when no prose files changed. Trace affected behavior into public docs,
product/developer Skills, human-to-agent prompts, tooltips and other UI copy,
WebMCP/MCP schemas and descriptions, CLI help/errors/examples, OpenAPI, manifests
and generated or bundled copies. Shared behavior starts in ash-template and its
libraries; inspect affected consumers when available.

Report concrete mismatches introduced or made relevant by this change, with the
failing user/agent action and exact source locations. Distinguish source, packaged,
published and deployed versions; name missing cross-repository or live evidence.
Preserve dated history and avoid cosmetic findings. Do not inflate severity or
claim that no findings proves complete coverage. This is read-only review: never
sign, pay, activate earnings, publish or deploy to test an instruction.
<!-- END REGENT ROLLOUT REVIEW -->
