# Release verification and availability

## macOS companion 2.12.0

The `native-v2.12.0-macos-r1` tag contains the signed/stapled macOS 13+ universal2
setup DMG and strict one-file gzip payload. Apple notarization submission
`7bf965a8-30a9-4358-8e3b-03af946dd487` was accepted with no issues. The real native
library verified the publisher signature, complete Mac artifact group, both
artifact digests and strict payload extraction before publication.

- Installer SHA-256: `6a039274041ec03237527fc84506c0e0f6c12ef2a1740e5431c4c93157272649`
- Payload SHA-256: `5c5e91d969982639bd80f273457584f8dc3b2ca88274990eb01bb0b0836ca8e2`
- Executable SHA-256: `d4e467f800621cf47824437ee8379bcd2b611770db1b195e872a1500d5b2af25`
- Catalog SHA-256: `9c1cd6dd57daf31bc55b0d63342097cfb506e3ec7735a38a77c9acbce17a0088`

`catalog.json` and its raw 64-byte detached `catalog.sig` are signed by the
independently compiled `publisher-2026` Ed25519 root. The detached
`provenance-macos-universal2` statement/signature use independent `builder-2026`.
The statement binds the exact executable/archive/catalog, base source commit,
native build-input fingerprint, recipe and Rust toolchain. This is a local
signed build with modified source inputs, not an asserted clean default-branch
or GitHub Actions build. Notices and input hashes accompany the package.

The extension identity is `nhliclifilepdkoolioacpjpijomfplj`, currently a store
draft. Installation does not pair a profile, select a chat, grant site access,
or activate browser control by itself. Windows/Linux and full live acceptance
remain incomplete.

## Release rules

A future release must identify its version, supported operating systems and
architectures, compatible extension/native versions, and exact artifact hashes.
Release assets will distinguish installers from payloads and provide the signed
catalog and independently signed build-provenance evidence required by the
companion. macOS releases additionally require verified Developer ID signatures
and Apple notarization of the final release bytes.

Checksums alone are not publisher authentication. A catalog cannot authorize
its own signing key: the installer independently pins approved public roots and
the expected extension origin. An uploaded file or a draft store identity does
not establish installed runtime readiness.

Only complete declared platform groups may be marked available. Missing
platforms remain unavailable, without substitute artifacts or unsigned
fallbacks. Prerelease candidates, if published, must be clearly labeled and
must not be presented as production installers.

Release publication must exclude private source archives, secrets, user data,
pairing state and unredacted machine logs. Public verification records should
contain only the release identity and evidence necessary to authenticate the
distributed bytes. This repository does not grant a source-code license;
applicable notices and redistribution terms must accompany each actual release.
