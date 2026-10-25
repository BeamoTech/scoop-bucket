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

### Review before merge
1. Read every Greptile summary and inline comment for the PR, including earlier review rounds.
2. Fix each valid finding in the affected source. Reply to each disputed finding on the PR with evidence; never silently discard a finding.
3. Batch related fixes into one push where practical, then inspect the review for the final head. Repeat as needed and account for every finding.
4. Do not merge with unaddressed findings, failed required checks, or unresolved safety or release gates.

### When automated review is unavailable
- A missing first review or stopped review is not proof of exhausted credits. Check available installation permissions, repository settings, review triggers, service status and quota evidence; record the confirmed cause or say it remains unknown.
- Preserve and address all earlier findings. If automated review cannot complete, require an explicit independent review of the final diff against current main, with reviewer identity, exact head SHA, scope, evidence, findings and remaining limits recorded on the PR. If that review or a required check is unavailable, keep the PR blocked.

### Cost and reporting
- Do not assert numerical credit allowances, reset dates or account billing settings without current evidence. Do not enable paid overflow, buy credits or expand access to obtain a review.
- Avoid redundant review requests and duplicate PRs. Batch pushes without reducing verification.
- Report Greptile findings received, fixed and disputed with reasons, plus review availability, final head, checks performed and outstanding blockers.
- Preserve repository specific instructions, mirrored guides, formatting rules, production freezes and authorization boundaries. Review approval does not authorize deployment, live trading, sending messages or other external effects.
