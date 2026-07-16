# ZQM Attestation Briefs — FAQ

### Is this a commercial product page?
No. This repo is a public methodology reference. Commercial terms are in `ZQM-Labs/zqm-attestation-toolkit`.

### Does this repo contain licensed source code?
No. Docs only. Code lives in `zqm-attestation-toolkit`.

### Can I redistribute these docs?
Yes, under CC-BY-4.0 for operational docs and MIT for templates. Attribution: "ZQM Computing".

### What is CMS signing?
Cryptographic message syntax signature, like a PDF signature. It binds the report to a public key without requiring online validation.

### How do I verify a report bundle?
Use `manifest.json` to compare file hashes, then verify `*.p7s` with `openssl cms -verify`.

### What about Windows version compatibility?
Attestation scripts target PowerShell 5.1+ on Windows 10/11.

### Where do I report issues?
Open a GitHub issue in this repo. Do not upload secrets or host-identifying data.
