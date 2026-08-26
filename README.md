# bohpts-launcher-bootstrap

Bootstrap channel for the game client launcher: a copy of the signed `mirrors.json` that the
launcher can reach when every distribution mirror is blocked.

**This repository is transport, not a trusted party.** Every file here carries an Ed25519 signature
made inside our vault; the launcher verifies it against a key compiled into the binary and rejects
anything that does not match. Whoever controls this repository can withhold updates or serve an
older signed copy — the launcher's monotonic `serial` and `not_after` checks are what make that
harmless — but cannot forge a document.

Design: `nx-infra/docs/specs/025-launcher-file-distribution.md` §7, launcher contract:
`nx-launcher/docs/specs/001-launcher-core.md` §5.

```
bohpts/mirrors.json   raw: https://raw.githubusercontent.com/n1rmataqq/bohpts-launcher-bootstrap/main/bohpts/mirrors.json
```

Published by `nx-infra/launcher/scripts/publish.py` — do not edit by hand.
