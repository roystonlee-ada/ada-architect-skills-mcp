# Ada Architect Skills for MCP

Skills that design, build, change and diagnose an Ada AI Agent using only the
Ada MCP server. No command line needed. The skills follow the open Agent
Skills standard (`SKILL.md`), so one folder serves Claude, ChatGPT and Codex.

## Skills

| Skill | Use it to |
|---|---|
| `setup-ada-mcp` | Connect your assistant to your Ada instance and check it works |
| `design-conversation` | Design a new use case as sample conversations you approve before anything is built |
| `author-playbook` | Build the approved design into a playbook, save its scenarios as test cases, run them |
| `revise-playbook` | Change an existing use case, with today's flow shown beside the proposed one |
| `diagnose-conversation` | Find which part of the agent owns a bad conversation, with evidence |
| `review-handoffs` | Count handoffs by the reason Ada recorded, with samples |

## Install

| Assistant | Command or steps |
|---|---|
| Claude Code | `claude plugin marketplace add roystonlee-ada/ada-architect-skills-mcp` then `claude plugin install ada-architect-skills-mcp@ada-architect-mcp` |
| Codex | `codex plugin marketplace add roystonlee-ada/ada-architect-skills-mcp` then `codex plugin add ada-architect-skills-mcp@ada-architect-mcp`. Start a new session afterwards |
| ChatGPT | Upload the plugin folder under Personal plugins, or ask a workspace admin to publish it. See OpenAI's plugin docs |
| Any other assistant that reads Agent Skills | Copy `plugins/ada-architect-skills-mcp/skills/` into that assistant's skills folder |

Then ask your assistant to "set up the Ada MCP". It connects to your instance
and checks the connection.

## Before you start

- What you can do depends on your Ada user's permissions. Edits land on a
  changeset that is not live. You approve every test run and every promote.
- Test runs use a daily quota that Ada sets. The skills check it first.
- The ChatGPT and Codex steps follow those products' docs. They have not been
  tried against a live Ada instance yet.

## Update

Claude Code: `claude plugin marketplace update ada-architect-mcp`, then
`claude plugin update ada-architect-skills-mcp@ada-architect-mcp`.
Codex: `codex plugin marketplace upgrade ada-architect-mcp`.

## Maintainers

Built from Ada's internal Architect skills by `local/build_mcp_plugin.py`. The
build fails if a customer name, an id, an email or a command-line reference is
left in a skill. A sibling plugin, `ada-architect-skills`, covers the adacli
route.
