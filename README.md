# confluence-external-search

**Confluence Data Center plugin for including search results from an external (unrelated) Confluence instance.**

Links from the external instance appear in the local search results. Clicking them leads to the external page (with natural login redirect if the user is not authenticated). Results can be restricted to specific user groups.

Developed and maintained via the **Agentic Loop** based on [agentic_loop_template](https://github.com/unhexx/agentic_loop_template).

## Features

- Server-side proxy to external Confluence `/rest/api/search` using a Personal Access Token (PAT).
- Admin settings page (in Confluence admin panel) for:
  - External base URL
  - PAT (stored securely on server)
  - Allowed user groups
  - Connection test
- Group-based visibility: only members of configured groups see external results.
- Injection of results into native Confluence search UI.
- Fully server-side enforcement (no client-side token exposure).

## Architecture

See [DESIGN.md](DESIGN.md) for detailed design.

See [ROADMAP.md](ROADMAP.md) for development roadmap tailored for local agents.

## Agentic Loop Setup

This repository is structured for self-improving multi-role agent development (Orchestrator → Coder → Tester → Debugger → Reviewer).

To bootstrap:

```bash
git clone https://github.com/unhexx/confluence-external-search.git
cd confluence-external-search
bash Agent-Init.sh   # or Agent-Init.ps1 on Windows
```

Then follow the prompts in `prompts/` or `AGENTIC_LOOP_README.md` (copied from template).

**Key files for agents:**
- `PROJECT_CONTEXT.md` — current project state and decisions
- `SPRINTPLAN.md` — current sprint tasks
- `DESIGN.md` / `ROADMAP.md` — specifications
- `.agent/` — loop state, playbooks, handoffs

## License

MIT — see LICENSE. Based on agentic_loop_template by exception.expert / Evgeniy Chistyakov.
