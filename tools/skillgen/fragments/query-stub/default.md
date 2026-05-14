When `graphify-out/graph.json` already exists and the user asks a question about the corpus, answer from the graph rather than rebuilding it:

```bash
graphify query "<question>"
```

Before traversal, expand the question against the graph's own vocabulary so a wording mismatch does not collapse the answer to noise. If the `graphify query` CLI is unavailable, fall back to an inline NetworkX traversal of `graphify-out/graph.json`. Answer using only what the graph output contains, and quote `source_location` when citing a specific fact.

**CRITICAL: Preserving --global flag in follow-up queries:** If the initial query used `--global`, ALL subsequent or refined queries in the same conversation MUST also include `--global`. When you decide to search for more specific information or refine your query, always check if the original command had `--global` and preserve it. Example:
- Initial: `graphify query "TMS statistics" --global`
- Follow-up: `graphify query "TMS management API" --global` ← MUST include --global
- Wrong: `graphify query "TMS management API"` ← Missing --global will cause "graph file not found" error

For that vocab-expansion step, the BFS/DFS traversal modes, the `--budget` cap, the NetworkX fallback, `save-result` feedback, and the `/graphify path` and `/graphify explain` flows, see `references/query.md`.
