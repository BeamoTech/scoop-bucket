# Scoop bucket — agent guide

`AGENTS.md` is the sole guide for all agents.

Windows package manifests for Beamo tools. Read [README.md](README.md) and the
relevant JSON manifest before editing. Application source lives in separate repos.

## CI, cost and documentation

Read `~/dev/AGENTS.md` for shared checkout, cost, documentation and storage rules.

- Iterate locally; run the applicable full local gate before release. Hosted
  CI is only for necessary final public/customer production verification,
  never routine work, draft PRs, previews or unshipped instruction/doc maintenance. Local
  scripts named `ci` remain local; do not push merely to trigger CI.
- Run the fewest required hosted jobs. Reuse only evidence for the exact final
  SHA, artifacts and config; revalidate after changes. Fix every candidate/gate
  failure and material warning, then rerun until all applicable checks pass.
  Pending, canceled, blocked, timed out and unexpected skips are not passes;
  path skips require workflow evidence. Never weaken tests/coverage or retry blindly.
- Check automatic triggers and gate publication on successful verification.
  Preserve required statuses, branch protection, scheduled security/ops checks,
  native acceptance and approvals; record proof and verify after deployment.
  No hosted CI means retain local/manual gates. Changes to automation or
  publication need task authority. Avoid duplicate providers/runs.

**Project gate:** Parse manifests locally during development. Before public install/update
changes, verify upstream bytes and final native Windows behavior; use the
manual `verify-claudex.yml` only when the Claudex release needs that gate,
including upgrade coverage when applicable. Guide edits do not need hosted
Windows jobs or installation into the user's environment.

## Package integrity

Keep versions, architecture mappings, dependencies, release URLs and SHA-256
digests aligned with verified upstream release bytes. Never guess a checksum.
Parse changed JSON and validate install/update behavior on Windows for package
changes; parsing alone does not prove a native installation.
Do not install tools into the user's environment merely to review documentation.
Publishing manifests affects installs; preserve approval and release boundaries.
Preserve unrelated work and stage only explicit owned paths.

<!-- BEGIN BEAMO UNFINISHED WORK -->
## Unfinished work

- Read the project's unfinished work record at task start. Use its existing
  canonical backlog, or `.ai/memory/unfinished-work.md` if none exists; link
  the record from `.ai/memory/MEMORY.md` when creating it. Chat is not storage.
- Always save every incomplete requested item, deferred issue, blocked check
  and pending merge/release step as they arise and before ending, pausing,
  handing off or changing tasks. Checkpoint after meaningful progress.
- Each item needs an ID/status, remaining acceptance criteria, exact next
  action, blockers/required approval, date/author, repo/branch/commit/worktree
  and relevant files or links. Separate completed checks and their evidence
  from failed, skipped and unrun checks; distinguish local, pushed and deployed
  state. Preserve partial source work without staging another agent's changes.
- Resume from the record, recheck current source and evidence, and update or
  mark items done only when their acceptance criteria pass. Record reasons for
  canceled/superseded items. Preserve useful history and others' entries; reread
  before editing and append separate items when concurrent work would overwrite
  them.
- Never store credentials or raw personal/customer records. Notes do not grant
  approval or prove deployment. If project writing is blocked, save a durable
  workspace handoff with the exact project/ref, record the blocker, and report
  its location before stopping; do not silently lose unfinished work.
<!-- END BEAMO UNFINISHED WORK -->

## Greptile review rules

Greptile reviews pull requests in this repo. Its feedback is part of the work, not decoration.

### The loop (required before merge)
1. After opening a PR, wait for the Greptile review and read **every** Greptile comment on the PR — inline comments and the summary review.
2. Fix every valid point in code. If you believe a point is wrong, reply to that comment on the PR explaining why — never silently ignore it.
3. Push the fixes and let Greptile re-review. Repeat until the review is clean or every remaining comment has an on-PR rebuttal.
4. Do not merge a PR with unaddressed Greptile comments.

### Credit discipline (hard cap — no overage exists)
- Each author gets **50 included review credits per billing period**. Flex/overage billing is capped at **$0** at the account level: when the credits run out, Greptile simply stops reviewing until the next period. There is no paid overflow and nobody may re-enable it.
- Every push to a PR can trigger a re-review and burn credits. Batch related fixes into fewer, larger pushes instead of drip-pushing commit-by-commit.
- Don't open throwaway or duplicate PRs against reviewed branches; close superseded PRs promptly.
- If reviews stop mid-cycle, assume the allowance is exhausted — finish the loop by reading the last Greptile comments you already have, and note it in the PR.

### Reporting
- When you finish a PR, state in your summary: Greptile comments received, how many you fixed, how many you rebutted and why.
