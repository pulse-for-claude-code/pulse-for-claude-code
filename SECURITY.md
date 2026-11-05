# Security

Please don't report security problems in public issues.

Use **Report a vulnerability** on the repository's [Security tab](../../security/advisories/new). It reaches the maintainers privately. We aim to reply within a week.

Worth knowing when you look:
- Each player is locked by its owner's key. The server compares keys in constant time and can store only a SHA-256 fingerprint (`PULSE_KEY_SHA256`).
- The plugin sends only event types, tool names and the project folder name.
- Share links carry the rhythm only: event codes, lanes and timing.
- Pulse Disc loads only its own files, through a private `pulse://` scheme, in a sandboxed page.
