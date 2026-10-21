## Summarizing test failures

**Situation:** a CI test run produces pages of output.

You need a short report containing failing test names, exact errors, and the command used. You are not investigating fixes yet.

The full logs would crowd the main conversation.

**Your choice: is a subagent enough, or would an agent team help?**

*What would you delegate, and what should come back?*

## Test failures: a subagent is enough

**Why:** this is a bounded task with a clear report to return.

1. Give one worker the test command and log location
2. Have it extract failures and return names, errors, and reproduction steps
3. The caller checks the summary and chooses the next investigation

**Example request:** “Summarize the login-test failures. Return evidence and the command used. Do not edit files.”

*Adapted from [high-volume operations](https://code.claude.com/docs/en/sub-agents#isolate-high-volume-operations).*

## An unstable login session

**Situation:** login succeeds, then the session disappears.

The cookie configuration, token refresh, and server-side session storage all look plausible. Evidence in one area could change what another investigator should test.

You need a root-cause hypothesis and a test that could disprove it.

**Your choice: are subagents enough, or would an agent team help?**

*How should the investigators compare their evidence?*

## Login investigation: an agent team

**Why:** findings change the next step for other investigators.

| Teammate | First investigation |
|---|---|
| Cookie investigator | Cookie attributes and request headers |
| Token investigator | Expiry and refresh behavior |
| Storage investigator | Session lookups and server logs |

Teammates challenge explanations with evidence. The lead selects a decisive test and checks the result.

*Suggested approach, adapted from [competing hypotheses](https://code.claude.com/docs/en/agent-teams#investigate-with-competing-hypotheses).*

## A feature across modules

**Situation:** add “sign out all devices.”

The work spans a backend revocation API, a frontend control, and integration tests. Each area has a separate owner.

API decisions may change as implementation reveals constraints. The owners need to update each other while they work.

**Your choice: are subagents enough, or would an agent team help?**

*What needs agreement before parallel edits begin?*

## Cross-module feature: an agent team

**Why:** ongoing API decisions affect several workstreams.

1. Agree on the request, response, and revocation behavior
2. Assign backend, frontend, and test files to separate teammates
3. Share contract changes, then have the lead integrate and run an end-to-end check

**Expected result:** one feature that works across all layers.

With a stable contract and independent assignments, subagents could also be sufficient.

*Application of [cross-layer coordination](https://code.claude.com/docs/en/agent-teams#when-to-use-agent-teams).*

## Researching independent modules

**Situation:** map how authentication, database storage, and API responses handle sessions.

Each investigation can finish independently. You need file locations, relevant behavior, and open questions from each area.

The main session will compare the reports after all workers finish.

**Your choice: are subagents enough, or would an agent team help?**

*Who needs to combine the findings?*

## Module research: subagents are enough

**Why:** the investigations can return separate reports.

| Worker | Assignment |
|---|---|
| Authentication | Map session creation and expiry |
| Database | Locate session persistence and deletion |
| API | Identify responses that clear a session |

Run the workers in parallel. Each returns locations and evidence. The caller connects the findings and identifies gaps.

*Adapted from [parallel research](https://code.claude.com/docs/en/sub-agents#run-parallel-research).*

## Reviewing a pull request

**Situation:** review a PR for security, performance, and test coverage.

You want independent reports from each perspective. Reviewers do not need to edit files or discuss findings while they work.

The main session will deduplicate and prioritize their reports.

**Your choice: are subagents enough, or would an agent team help?**

*Does having several perspectives require a team?*

## Independent PR review: subagents are enough

**Why:** multiple perspectives can still be bounded assignments.

1. Assign one reviewer to each review criterion
2. Require file locations, severity, and supporting evidence
3. Have the caller combine the reports and check important findings

**What would change the choice?** A team helps if reviewers need to discuss interacting findings and revise the review together.

*Variation on [parallel code review](https://code.claude.com/docs/en/agent-teams#run-a-parallel-code-review). The coordination requirement determines the choice.*

## A reusable subagent in Claude Code

Project file: `.claude/agents/login-reviewer.md`

```yaml
---
name: login-reviewer
description: Reviews login defects
tools: Read, Grep, Glob
---
Inspect login code. Return locations,
evidence, and suggested checks.
```

Invoke: **“Use login-reviewer to inspect src/auth/.”**

The description guides delegation. Tools restrict capability. [Subagent files](https://code.claude.com/docs/en/sub-agents#write-subagent-files).

## Starting a team in Claude Code

Agent teams are **experimental**. Start an interactive session with:

```sh
CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1 claude
```

Then ask: “Create an agent team to investigate the login regression. Assign cookie, token, and storage investigators. Have them compare evidence and propose a decisive test.”

Teammates receive project context and their assignment, not the lead's conversation history. Resuming the lead does not restore in-process teammates.

[Team setup and limitations](https://code.claude.com/docs/en/agent-teams).

