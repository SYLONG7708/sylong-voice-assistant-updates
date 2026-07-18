# Security policy

The update manifest must be signed offline with the dedicated update-signing
private key. The private key is never stored in this repository or in GitHub
Actions.

Do not merge an update when:

- the detached signature does not verify;
- a sequence number goes backwards or is reused for different content;
- an asset URL is not HTTPS or is outside the allowlisted GitHub hosts;
- size or SHA-256 does not match the release asset;
- a target path is not one of the explicitly supported data/model paths;
- the manifest tries to distribute APK, DEX, JAR, SO, scripts, or arbitrary
  executable content.

Report suspected manifest tampering or key exposure privately to the repository
owner. Do not place exploit details, credentials, customer data, or license
tokens in a public issue.
