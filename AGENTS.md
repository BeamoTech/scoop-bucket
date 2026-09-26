# Scoop bucket — agent guide

`AGENTS.md` is the sole project instruction file for all coding agents.

Windows package manifests for Beamo tools. Read [README.md](README.md) and the
relevant JSON manifest before editing. Application source lives in separate repos.

## CI, cost and documentation

- Use **Blacksmith** runners for supported GitHub Actions CI. Check the current
  [runner documentation](https://docs.blacksmith.sh/blacksmith-runners/overview)
  and repository access before selecting labels. Preserve required checks and
  native platform coverage; retain an existing gate until its replacement proves
  equivalent coverage for the same source. Record any provider exception.
- Minimize total cost across CI, hosting, storage, network, APIs, AI and tooling.
  Choose the least costly option that meets the task's quality, security,
  reliability and performance requirements. Preserve mandated models and gates;
  never trade away correctness, coverage, accessibility or data safety for price.
- Measure usage, reuse valid caches, bound retries/concurrency, cancel superseded
  verification runs and expire disposable artifacts. Never cancel a release or
  data migration blindly. Use local fixtures for iteration, run required gates
  before delivery, and retire only verified idle resources within task authority.
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
