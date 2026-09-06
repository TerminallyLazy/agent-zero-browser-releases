# Release verification and availability

There are currently no production releases in this repository.

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
