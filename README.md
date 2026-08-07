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

## Browser SSH CLI

Install [bssh](https://browserssh.com) on Windows with:

```powershell
scoop bucket add beamoint https://github.com/BeamoINT/scoop-bucket
scoop install beamoint/bssh
bssh --help
```

`bssh` is the first-party CLI for the Browser SSH agent API and MCP install glue.
Scoop installs the Node.js runtime dependency; the CLI is a self-contained bundle
shipped as a GitHub Release asset (not published to npm).
