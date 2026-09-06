# Agent Zero browser companion downloads

Public distribution repository for signed browser-companion packages and
release-verification metadata maintained by
[TerminallyLazy](https://github.com/TerminallyLazy).

## Current availability

The corrected **macOS 13+ companion 2.12.0 (r2)** is available for Intel and
Apple Silicon:
[Download Mac setup](https://raw.githubusercontent.com/TerminallyLazy/agent-zero-browser-releases/native-v2.12.0-macos-r2/v2.12.0/a0-browser-bridge-2.12.0-macos-universal2.dmg).
Open the disk image, open Agent Zero Browser Setup, then choose Install.
No administrator password is needed. Pair the production extension once afterward.

The real native installation, independent status and doctor checks returned
`INSTALL_VERIFIED` with one Chrome registration on Apple Silicon. The Intel
slice is signed/notarized but has not received a separate Intel installation
acceptance run. These installation results do not establish live browser
control. The earlier r1 parser defect fails before installation; use r2 instead.

The Chrome Web Store item is still a draft. Windows and Linux packages are not
yet available; they remain required work, not implied support. This Mac package
does not mark the cross-platform overhaul or full live browser acceptance complete.
Existing development pairing is separate and is not silently migrated.

Downloads require no GitHub account. Exact version paths use an update/delete-
protected tag. The installer authenticates its catalog and payload and requires
independent build provenance plus Apple's signing/notarization checks before
registering the companion. See [release verification](RELEASES.md).

The native companion belongs on the computer running Chrome, including when
Agent Zero runs in Docker. Do not install it inside the Agent Zero container.

## Setup and support

- [Setup guide](https://github.com/TerminallyLazy/agent-zero-browser-support/blob/main/SETUP.md)
- [Troubleshooting](https://github.com/TerminallyLazy/agent-zero-browser-support/blob/main/TROUBLESHOOTING.md)
- [Privacy policy](https://github.com/TerminallyLazy/agent-zero-browser-support/blob/main/PRIVACY.md)
- [Support](https://github.com/TerminallyLazy/agent-zero-browser-support/issues)
- [Release verification](RELEASES.md)

This repository is for public release artifacts and metadata, not private
source, credentials, pairing records, browser profiles, chat data or build logs.
Never upload those to a public issue or release. This is a community-maintained
integration, not a product from OpenAI or Google.
