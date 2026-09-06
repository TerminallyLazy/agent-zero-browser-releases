# Release verification and availability

## macOS companion 2.12.3

`native-v2.12.3-macos` fixes the opposite-direction result/event queue overflow.
The queue stays at eight slots with one retained producer packet and at most
one second of FIFO backpressure. Worker state, transport deadlines, cancellation
and clean native EOF remain enforced. Ten focused queue/framing tests passed.
Apple submission `937428ac-4ecb-40b3-bc4f-3e8d39d8deff` was accepted, and the
Developer ID signed universal2 setup DMG was stapled and verified.

- Installer SHA-256: `dffe50049328a667869349a418502eab2175fefb5da4386f82933e167eda7438`
- Payload SHA-256: `ea3291999470a548b90bdcd1f82b90707364fa18e3f08938e6564b7457e2b127`
- Executable SHA-256: `803a24e87f2568c5fbb1c9f5de400bd3b8aab60a16a6ac70f3814be4494f482b`
- Catalog SHA-256: `a40176dcd2048e692996b3ba4f5bf5218fe5ab98fca085f85eaa6cbe9a9ebd29`
- Source commit: `30fa11aaa1649c7347dba971d0adbd4259b12e7a`

Publisher and independent builder signatures verified. This repairs a
reproduced defect, not a proven explanation for every live disconnect.
Installation and live browser acceptance are recorded separately.

## macOS companion 2.12.2

`native-v2.12.2-macos` replaces immediate valid-message queue overflow failure
with bounded backpressure. FIFO, fixed capacity, cancellation and current
heartbeat/renewal deadlines remain enforced. Fixed-code stderr diagnostics
contain no payloads or credentials. Two focused transport regressions passed.
Both Mac slices are Developer ID signed; Apple submission
`12261607-3ecd-48ca-a516-b9fa514d324d` was accepted and the setup DMG stapled.

- Installer SHA-256: `2b33f34ef3e13f520a391977369ec449e4762b9e9c2b0208f7ed257ac5c33577`
- Payload SHA-256: `2681377a297d9943a069b245587a40cdb727c8d8119a733116df3c3eecf6088c`
- Executable SHA-256: `8cb84de1e66bbd52771b534cb1bfc83d69eb94ebc87b3f7669547bff68359080`
- Catalog SHA-256: `f403678be1077192cc10930f3f1a2a43a55abfdaf0d8ba0615f2780153f046ab`
- Source commit: `c6d54842e2b9ffd467a029a7f68b10902b04af7f`

Publisher catalog and independent builder provenance verification passed.
This fixes a reproduced transport defect, but does not prove the cause of every
historical disconnect. Installation and end-to-end browser acceptance remain
separate from package verification.

## macOS companion 2.12.1

`native-v2.12.1-macos-r2` fixes canonical successful-operation decoding, including
the required bounded `completed_at_ms` field. The signed universal2 executable,
stapled setup DMG, strict payload, publisher catalog and independent build
provenance were verified. Apple submission
`b905819f-512b-4182-9fe3-46e1c9631fa2` was accepted without issues.

- Installer SHA-256: `6573605ec3f198082fd5f9a2eb63bb3cb952a2f2258a7ae023b6362bdd3cbcf2`
- Payload SHA-256: `5dc1db234c820ecf03119c36f637c6042de33ceee5df88adf8bfb6d037fef4f5`
- Executable SHA-256: `26e2bd4ca821b5b2ca7cde5336f1348d682f47855fee705cf43aafd992205890`
- Catalog SHA-256: `3dcde8e12a571a98d8fe9dfd2c4086469d68e03da9129ee18a63505c834c82b3`
- Source commit: `d6c661451a6db72c5334e06d98389ec779b555cd` in the companion integration PR branch.

The security floor remains 2.12.0. Older immutable releases are retained;
installing this update preserves the existing native identity and pairing.
Package verification alone does not establish live control acceptance.

The earlier `native-v2.12.1-macos` tag accidentally omitted its payload and
installer. It cannot install and is retained unchanged, not used as a fallback.
The complete r2 publication uses a new immutable tag and matching compiled URLs.

## macOS companion 2.12.0

### Corrected r2 distribution

`native-v2.12.0-macos-r2` contains the corrected CodeDirectory parser, signed
universal2 executable, stapled setup DMG and strict one-file payload. Apple
submission `46ed0eb5-eb57-471a-a07b-c4d607729f71` was accepted without issues.
The publisher and independent builder signatures, both artifact hashes, strict
payload extraction and the executable's explicit notarization requirement
passed before publication. Installation acceptance is recorded separately on
the default-branch README after actual installed-state verification.

- Installer SHA-256: `a69805cf50befaac0aaab9504dc07fc17135a1af078fae78a5df22817f635d58`
- Payload SHA-256: `f9ca468982794f3a767cdfe2d06f1fc308202d27c7c7d8f383e4a3e108d25482`
- Executable SHA-256: `8f8125212bcafa3ead9e8f44c3dc8bc7213ee9f44570dd63638a242f3b067b6f`
- Catalog SHA-256: `9758f715d7648ee2246c82dc3e9a3574dfc55c07cad24d629166e0cd40ef35e4`
- Source commit: `b6b985f848c2f0c6ccd55b61333ed3f95ead40f1` in the companion integration PR branch.

### Historical r1 distribution

**r1 installation defect:** actual installation subsequently exposed a
CodeDirectory flags parser issue. It fails closed before registration or state
mutation. The earlier publication checks below did not establish installation
acceptance. Do not use r1 for a fresh install; its tag is retained unchanged.
A corrected distribution is being prepared under a new immutable revision.

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
