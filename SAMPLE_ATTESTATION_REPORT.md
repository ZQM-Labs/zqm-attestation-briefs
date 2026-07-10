# SAMPLE_ATTESTATION_REPORT.md
## Forensics Attestation Report — Synthetic Example

**Report ID:** ATTEST-2026-0000-EXAMPLE
**Generated:** 2026-07-10T00:00:00Z
**Host:** example-host.corp
**Signer:** Alex Zelenski, GISP
**Toolkit:** ZQM Attestation Toolkit v1.0.0

### Executive Summary

This is a synthetic attestation report used to demonstrate report format prior to authorizing a real attestation run. No data reflects an actual host.

### Control Coverage

| Control | Status | Evidence |
|---|---|---|
| BitLocker Volume Encryption | Compliant | VolumeStatus: Encrypted, XTS-AES 256, TPM+PIN protector |
| TPM Presence | Present | TPM 2.0, Manufacturer: XYZ Corp |
| Windows Defender Status | Active | Real-time protection on, ASR rules loaded |
| Secure Boot | Enabled | UEFI SecureBoot state: On |
| OS Integrity | Verified | SHA256 boot hash: a]b7...9f2 |
| Policy Compliance | Partial | 3/5 CIS controls enforced |

### Cryptographic Evidence

```powershell
Get-FileHash -Algorithm SHA256 .\evidence\disk_volume_hashes.json
# a7f3b2c4d5... = 19f2a1b3c4d5e6f7a8b9c0d1e2f3a4b5c6d7e8f9a0b1c2d3e4f5a6b7c8d9e0
CMS signature attached: attestation_report.p7s
```

### Attestation Chain

1. Evidence collected via `scripts/diag_all.ps1`
2. Hashes computed via `scripts/attest_suite.ps1`
3. Report signed via CMS detached signature
4. Sig validated via `scripts/verify_signature.ps1`

### Limitations

- This sample excludes real paths, real hashes, real hostnames
- For actual attestation, see `zqm-attestation-toolkit` deployment guide

### Terms

- Commercial use requires license: see COMMERCIAL.md upstream
- Sample output is CC-BY-4.0; upstream license governs delivered software
