# Scoop bucket — agent guide

`AGENTS.md` is the sole project instruction file for all coding agents.

Windows package manifests for Beamo tools. Read [README.md](README.md) and the
relevant JSON manifest before editing. Application source lives in separate repos.

## CI, cost and documentation

- Prefer [Google Cloud Build](https://cloud.google.com/build/pricing) for
  eligible CI only when the billing account's verified free minutes cover the
  entire forecast run with headroom. Use [AWS CodeBuild](https://aws.amazon.com/codebuild/pricing/)
  likewise for qualifying small on demand builds. Check shared usage, machine
  eligibility, and logging, storage and network costs. If neither free
  allowance safely covers the run, use [Blacksmith](https://docs.blacksmith.sh/blacksmith-runners/overview)
  for supported GitHub Actions or the project's required native provider.
- Keep existing required checks until a replacement proves equivalent
  statuses for the exact commit, native coverage, security and release gates. Follow
  provider mandates in each project and avoid duplicate runs. For suitable
  optional compute, assess [Cloud Run](https://cloud.google.com/run/pricing)
  and [AWS Lambda](https://aws.amazon.com/lambda/pricing/) free usage with the
  same forecast for the complete run; never move a live service merely to use a free tier.
- Minimize total cost across CI, hosting, storage, network, APIs, AI and tooling.
  Choose the least costly option that meets the task's quality, security,
  reliability and performance requirements. Preserve mandated models and gates;
  never trade away correctness, coverage, accessibility or data safety for price.
- Use the fewest hosted CI runs that still cover changed paths, scheduled
  checks and required gates. Iterate locally, route jobs by scope, reuse valid
  caches, avoid duplicate runs and bound retries/concurrency. Cancel superseded
  verification when safe; review releases and migrations before cancellation.
  Preserve checks for the exact commit and native platforms. Measure usage,
  expire disposable artifacts and retire only verified idle resources within
  task authority.
- Keep Markdown focused: one canonical home per topic, short sections and useful
  links. Keep commands and safeguards near their use; move detailed history to
  dated evidence. Update stale guidance against code, preserve release records,
  and avoid duplicating this policy in every document.

## Package integrity

Keep versions, architecture mappings, dependencies, release URLs and SHA-256
digests aligned with verified upstream release bytes. Never guess a checksum.
Parse changed JSON and validate install/update behavior on Windows for package
changes; parsing alone does not prove a native installation.
Do not install tools into the user's environment merely to review documentation.
Publishing manifests affects installs; preserve approval and release boundaries.
Preserve unrelated work and stage only explicit owned paths.
