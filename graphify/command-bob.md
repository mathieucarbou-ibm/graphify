---
description: Build or query a graphify knowledge graph
---

Invoke the `graphify` skill immediately and let it handle the entire task.

Pass the full `/graphify` argument string through unchanged.
If no arguments were supplied, treat the target path as `.`.

Examples:
- `/graphify`
- `/graphify src --update`
- `/graphify query "what connects auth to billing?"`

Do not answer from raw files before handing off to the `graphify` skill.

**CRITICAL:** After invoking the skill with `use_skill`, do NOT use `attempt_completion`. The skill will handle the entire workflow and complete when done. Your only job is to invoke the skill and pass control to it.