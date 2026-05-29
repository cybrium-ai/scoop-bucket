# Cybrium — Scoop Bucket

[Scoop](https://scoop.sh) bucket for Cybrium's signed Windows binaries.

## Install

```powershell
scoop bucket add cybrium https://github.com/cybrium-ai/scoop-bucket
```

## Tools

| Tool | Description |
|---|---|
| `cyweb` | Web vulnerability scanner |
| `cysense` | Network sensor (requires Npcap on Windows) |
| `cywave` | Wireless / RF posture scanner |
| `cyprobe` | OT / IoT discovery scanner |

## Install a tool

```powershell
scoop install cyweb
scoop install cysense
scoop install cywave
scoop install cyprobe
```

## Signing

Every binary is Authenticode-signed by **Cybrium Inc** via Azure Trusted Signing.
Verify with:

```powershell
Get-AuthenticodeSignature (Get-Command cyweb).Source
```

Expected: `Status = Valid`, `SignerCertificate.Subject = CN=Cybrium Inc, ...`.

## Update

```powershell
scoop update
```

The `checkver` + `autoupdate` blocks in each manifest let Scoop pull the latest
GitHub release automatically.

## License

Manifests: MIT. Each tool is licensed per its own repository.
