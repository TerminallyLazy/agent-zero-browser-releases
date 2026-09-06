# Agent Zero browser companion downloads

Public distribution repository for signed browser-companion packages and
release-verification metadata maintained by
[TerminallyLazy](https://github.com/TerminallyLazy).

## Current availability

The **macOS 13+ companion 2.12.2** is available for Intel and
Apple Silicon:
[Download Mac setup](https://raw.githubusercontent.com/TerminallyLazy/agent-zero-browser-releases/native-v2.12.2-macos/v2.12.2/a0-browser-bridge-2.12.2-macos-universal2.dmg).
Open the disk image, open Agent Zero Browser Setup, then choose Install.
No administrator password is needed. Pair the production extension once afterward.

Version 2.12.2 adds bounded handling of valid message bursts so a briefly full
receive queue does not immediately disconnect control. It retains the 2.12.1
fix for decoding successful browser-operation results, preventing
a completed Chrome action from losing its reply. Both architecture slices are
signed and notarized. Actual update, installed status and doctor returned
`INSTALL_VERIFIED` on Apple Silicon, preserving pairing and one Chrome
registration; Chrome launched the installed 2.12.2 companion.
The latest live check is blocked during Core connection reconciliation, before
any browser action is sent. Installation is verified, but end-to-end browser
operation acceptance is not yet complete.
Intel installation remains separately unverified. Earlier incomplete or broken
distributions are not fallbacks.

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
