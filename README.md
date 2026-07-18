# SYLONG Voice Assistant secure update channel

This public repository is the distribution channel for non-secret, signed
configuration and redistributable speech model assets used by the commercial
SYLONG Voice Assistant.

It intentionally does **not** contain:

- proprietary Android source code;
- commercial APK files;
- APK, update, or license private keys;
- customer license tokens or customer information;
- backend credentials.

The Android client embeds only the public update certificate. It verifies the
detached RSA signature before parsing `channel/stable/manifest.json`, rejects
rollback, and verifies the exact size and SHA-256 of every downloaded asset.
Remote configuration is data-only and cannot load executable Android code.

Large model files are attached to GitHub Releases instead of regular Git
history. The stable release contains SenseVoice INT8 plus the existing English
and Vietnamese Vosk offline models. This follows GitHub's documented 100 MiB
repository object limit while keeping the repository small.

Repository release immutability is enabled. Stable assets are uploaded to a
draft and only then published, so GitHub locks the release assets and associated
tag and emits a release attestation.

## Stable channel

- Manifest: `channel/stable/manifest.json`
- Detached signature: `channel/stable/manifest.json.sig`
- Public certificate: `certificates/update-signing-cert.der`
- Immutable asset release: `speech-assets-2026-07-18-r2`

The SenseVoice and Vosk projects retain their own upstream licenses. See
`THIRD_PARTY_NOTICES.txt`.
