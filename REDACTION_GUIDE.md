# Redaction Guide

Before sharing an externally signed attestation report, remove or replace:

- Hostname, domain, internal DNS suffixes
- IP addresses, MAC addresses, UUIDs
- Volume mount paths that expose organizational naming
- User names or corporate-issued usernames
- Asset tags tied to internal inventory systems
- Cryptographic tags that tie to internal CA trust anchors

Recommended scrub pattern

```powershell
$patterns = @(
  'CORP\\',
  'corp.local',
  '192\.168\.',
  '10\.',
  '172\.(1[6-9]|2[0-9]|3[01])\.'
)
```

Replace each with `REDACTED` for public use. Retain:

- Algorithm names
- Control names
- Pass/fail status
- Signer identity
- Toolkit version
- Timestamp

Failure to redact host-attribution data creates false attribution risk and may violate privacy commitments.
