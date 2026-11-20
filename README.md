# Ring Windows Notifier

**Windows desktop companion for Ring doorbells and cameras — public release preparation.**

> **Download status: NOT YET RELEASED.** There is currently no approved public Windows installer, portable executable, or in-app public update available. The Releases page is intentionally empty until the installer, security checks, and update path have passed acceptance. Do not treat GitHub's automatically generated “Source code (zip)” as an installable Windows update.

## What the application is intended to do

- Show motion and doorbell notifications on a selected Windows monitor and corner.
- Provide Ring camera Live View, camera audio, and press-to-talk when supported by the camera.
- Support multi-monitor setups and a Stream Deck-triggered manual Live View.
- Offer an Update Manager designed to verify new versions and preserve user settings.

Feature support and delivery reliability must still be verified against the released Windows build and actual Ring hardware. This is an independent, unofficial project and is **not affiliated with, endorsed by, or supported by Ring or Amazon**.

## Releases and updates

When an approved release is available, it will appear under [Releases](https://github.com/DanologyUK/Ring-Windows-Notifier/releases) with versioned Windows installer assets, file checksums, release notes, and installation requirements. The app's future public update checker will read published release metadata from this repository. The public channel is **not active yet**.

- A Windows installer or update **must not** be trusted solely because it is hosted on GitHub. It must pass the project's exact-file integrity, publisher/security, Windows install/upgrade, and recovery checks.
- Updates must require explicit consent and protect existing Ring sign-in state, camera preferences, monitor layout, and settings.
- Public release downloads will not require end users to log in to a GitHub account.
- Development source and test material remain private until separately reviewed for publication.

## Release-readiness requirements

Before a public beta can be published, the exact Windows build must pass malware/security review, source-to-binary provenance checks, installer and in-app upgrade/rollback testing, and real notification/Live View acceptance. Stable V1 additionally requires its final release criteria and explicit owner approval.

**Do not rely on Ring Windows Notifier as a guaranteed security alarm or emergency-monitoring service.** Device notifications and live video depend on third-party services, internet connectivity, authentication, and hardware.

## Support and security

Do not post Ring credentials, authentication tokens, raw diagnostics, camera footage, personal addresses, or private logs to public issues. A public support/security reporting route will be supplied when the first approved release is published.

Copyright and branding belong to their respective owners; this project makes no claim of ownership of the Ring or Amazon trademarks.
