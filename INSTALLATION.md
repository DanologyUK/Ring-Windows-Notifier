# Installation and update verification

> **Not released.** Ring Windows Notifier has no approved public installer or downloadable update at present. These steps apply only after a release is explicitly published and verified.

## When a release becomes available

1. Open the official [GitHub Releases page](https://github.com/DanologyUK/Ring-Windows-Notifier/releases) and select an explicitly published Windows x64 release.
2. Download its version-matched `Ring-Windows-Notifier-Setup-VERSION-x64.exe`, `RELEASE-MANIFEST-vVERSION.json`, and `SHA256-Windows.txt` assets. Actual filenames and signing status will be stated in that release.
3. On Windows PowerShell, run `Get-FileHash -Algorithm SHA256 -LiteralPath "PATH-TO-SETUP.exe"` and compare the full digest with the matching entry in both release checksum records. **Stop if the values differ.**
4. If a release claims a signed installer, verify its Windows Authenticode signature against the publisher information documented for that exact release. A matching hash alone does not establish publisher identity.
5. Read its known issues and installation requirements; only then choose whether to run Setup.

Never disable antivirus or Windows protections to force an installer to run. Do not accept installers posted in GitHub comments, issue attachments, unverified mirrors, or private GitHub Actions artifacts.

**GitHub's automatically offered “Source code (zip)” is not a Windows installer or an in-app update ZIP.**

## Updates

The planned in-app public updater will check published GitHub releases without requiring an end user's GitHub sign-in. The updater is not active on the public channel yet. Downloading and installing must be separately consented to, with settings backup and integrity checks before handoff. Existing private test ZIPs are not public releases.

This app is unofficial and is not a guaranteed alarm or emergency monitoring service.
