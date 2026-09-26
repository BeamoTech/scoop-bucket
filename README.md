# BeamoINT Scoop bucket

Install [Claudex](https://github.com/BeamoINT/Claudex) on Windows with:

```powershell
scoop bucket add beamoint https://github.com/BeamoINT/scoop-bucket
scoop install beamoint/claudex
claudex --login
```

Claudex's automatic first-run setup installs Codex and Claude Code when they
are missing. Scoop installs the Node.js and jq runtime dependencies used by
that setup.

## Beamo Flasher CLI

Install [Beamo Flasher](https://beamo.tech/flasher-download) on Windows with:

```powershell
scoop bucket add beamoint https://github.com/BeamoINT/scoop-bucket
scoop install beamoint/beamo-flasher
bflash --help
```

## Retired BrowserSSH agent CLI

BrowserSSH is a personal browser SSH service. The retained `bssh` manifest is a
historical package; BrowserSSH no longer provides its agent API or MCP integration.
AgentSSH is a separate local development archive with retired hosted infrastructure.
Do not treat either package as access to a live agent service. Use the current
[BrowserSSH website](https://browserssh.com) for browser terminal access.
