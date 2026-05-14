# Skill Registry

**Delegator use only.** Any agent that launches sub-agents reads this registry to resolve compact rules, then injects them directly into sub-agent prompts. Sub-agents do NOT read this registry or individual SKILL.md files.

See `_shared/skill-resolver.md` for the full resolution protocol.

## User Skills

| Trigger | Skill | Path |
|---------|-------|------|
| Creating a pull request, opening a PR, or preparing changes for review | branch-pr | C:\Users\Usuario\.gemini\skills\branch-pr\SKILL.md |
| Writing Go tests, using teatest, or adding test coverage | go-testing | C:\Users\Usuario\.gemini\skills\go-testing\SKILL.md |
| Creating a GitHub issue, reporting a bug, or requesting a feature | issue-creation | C:\Users\Usuario\.gemini\skills\issue-creation\SKILL.md |
| "judgment day", "judgment-day", "review adversarial", "dual review", "doble review", "juzgar", "que lo juzguen" | judgment-day | C:\Users\Usuario\.gemini\skills\judgment-day\SKILL.md |
| User asks to create a new skill, add agent instructions, or document patterns for AI | skill-creator | C:\Users\Usuario\.gemini\skills\skill-creator\SKILL.md |

## Compact Rules

### branch-pr
- Every PR MUST link an approved issue
- Every PR MUST have exactly one `type:*` label
- Automated checks must pass before merge is possible
- Branch naming: `^(feat|fix|chore|docs|style|refactor|perf|test|build|ci|revert)\/[a-z0-9._-]+$`
- Use conventional commits for all changes

### go-testing
- Use table-driven tests for multiple test cases
- Use `teatest` for Bubbletea TUI component testing
- Use golden file testing for complex output validation
- Keep tests in `_test.go` files alongside source
- Use `t.Parallel()` for independent tests

### issue-creation
- Blank issues are disabled — MUST use a template
- Every issue gets `status:needs-review` automatically
- A maintainer MUST add `status:approved` before any PR can be opened
- Questions go to Discussions, not issues

### judgment-day
- Launch TWO independent blind judge sub-agents in parallel
- Neither judge knows about the other
- Follow Skill Resolver Protocol before launching judges
- Synthesize verdicts, apply fixes, then re-judge
- Escalate after 2 iterations if judges still disagree

### skill-creator
- Create a skill when a pattern is used repeatedly
- Don't create a skill for trivial or one-off tasks
- Skill structure: `skills/{name}/SKILL.md` + optional `assets/` and `references/`
- Include frontmatter with name, description, trigger, license, metadata
- Keep compact rules 5-15 lines, actionable only

## Project Conventions

| File | Path | Notes |
|------|------|-------|
| None found | — | No agents.md, AGENTS.md, CLAUDE.md, .cursorrules, GEMINI.md, or copilot-instructions.md detected |
