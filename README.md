# Agent Zero browser companion downloads

Public distribution repository for signed browser-companion packages and
release-verification metadata maintained by
[TerminallyLazy](https://github.com/TerminallyLazy).

## Current availability

The macOS installer is temporarily unavailable while a corrected signed release
is prepared. The original `native-v2.12.0-macos-r1` package stops at a signature
metadata parser check before installation; do not use it for a fresh install.
Its published bytes remain immutable for auditability. A replacement will be
linked only after installation and installed-state verification succeed.

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
