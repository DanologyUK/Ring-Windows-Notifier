# Public Windows beta release gate

**Status: HOLD — no Windows binary has been approved or published.** This document is a release checklist, not a release announcement. It provides the acceptance contract for the first public beta and subsequent in-app updates.

## Publication contract

Use the exact tag `vVERSION` and matching file names, with a version such as `1.0.0-beta.12`:

- `Ring-Windows-Notifier-Setup-VERSION-x64.exe` — a **real Windows-built NSIS Setup EXE**, not copied Program Files contents and not a source ZIP.
- `RELEASE-MANIFEST-vVERSION.json` — exact version, application identity, installer size, SHA-256 and signing policy.
- `RELEASE-MANIFEST-vVERSION.json.sig` — detached Ed25519 signature over those exact manifest bytes, made using the owner-controlled **private key kept off GitHub**.

The owner public verification key must be independently approved and compiled into the released app before it can authenticate updates. GitHub release metadata, checksums alone, a same-host signature attachment, or synthetic test keys do not establish trust. The Ed25519 manifest signature is **not** Windows Authenticode signing; unsigned installers may trigger Windows SmartScreen.

Additional assets are not approved automatically. The first public beta is an **installer-only** release profile until the exact release builder and verifier approve another profile. Do not upload internal diagnostic archives, logs, credentials, private keys, or unreviewed source snapshots.

## Required independent evidence before publishing

- [ ] Exact source commit/tag, clean working tree and build provenance recorded; no secrets, credentials or private camera data in the release.
- [ ] The Windows x64 NSIS installer is built from that exact candidate, then identified by full SHA-256 and file length.
- [ ] Fixed all-users installation in `C:\Program Files\Ring Windows Notifier` works on a clean Windows machine; program settings remain under AppData as intended.
- [ ] Genuine Installed Apps registration, Start menu entries and **real NSIS uninstall** work. A copied portable/backup-restored app plus a manually created registry entry does **not** satisfy this check.
- [ ] Migration from any older or backup-restored installation is supervised, prevents duplicate uninstall registrations, preserves user settings and supports rollback.
- [ ] A previously cancelled or ambiguous installer handoff is independently reconciled; no deleting an update receipt merely to make a gate pass.
- [ ] The same three release assets pass the app's independent offline Ed25519 bundle verification; verify the *exact uploaded bytes* once staged.
- [ ] The Windows security/publisher review, file-integrity checks, and installed-app readiness checks pass with the actual binary.
- [ ] End-to-end Windows test demonstrates motion and doorbell events, Live View, camera audio, push-to-talk where supported, tray interactions and monitor selection after install.
- [ ] First user-approved in-app GitHub update verifies consent, exact download hash, idle/backup handoff, restart, settings preservation and recovery. Repeat with a **second sequential version**.
- [ ] Release notes contain real known issues, Windows requirements, checksum and publisher guidance.
- [ ] Owner explicitly approves publication of these exact binary and manifest SHA-256 values. No automated push, scheduled job or draft PR implies approval.

## How to stage a release

1. Keep the Windows installer and manifest **private** until all checks above pass. Draft GitHub Releases are not a substitute for verification.
2. Record the exact planned tag and three asset names and compare them against the source-bound contract.
3. Review, approve and publish to the [official Releases page](https://github.com/DanologyUK/Ring-Windows-Notifier/releases) only after the owner signs off.
4. Independently inspect the published asset bytes and GitHub URLs before marking the public updater operational.

**Current limitations:** The existing beta.11 backup-restored client is not evidence of a genuine NSIS installation. The newer beta.12 source has a fail-closed legacy-registration guard, but there is no approved migration or native Windows acceptance yet. The public install path is intentionally disabled until those gates pass.

Ring Windows Notifier is unofficial, unaffiliated with Ring/Amazon, and not suitable as a guaranteed security alarm.
