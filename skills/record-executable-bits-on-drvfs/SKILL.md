---
name: record-executable-bits-on-drvfs
description: Use when committing executable scripts from a WSL checkout on a Windows drvfs mount (/mnt/c) and the executable bit must reach git
metadata:
  mneme-type: skill
  mneme-source: mneme-build@plans-01-07
  mneme-captured: 2026-08-12
  mneme-last-verified: 2026-08-12
---
# record-executable-bits-on-drvfs

## Procedure

1. chmod +x the file as usual (harmless, but insufficient on drvfs).
2. Record the bit directly in the index: `git update-index --add --chmod=+x <file>`.
3. Verify with `git ls-files --stage <file>` — expect mode 100755 before committing.

## Failure pattern

chmod alone silently does nothing on drvfs mounts: the file commits as 100644, and launchers fail with 'Permission denied' only for users cloning to real POSIX filesystems — the author never sees the breakage.
