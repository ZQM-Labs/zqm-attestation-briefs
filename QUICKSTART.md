# ZQM Attestation Quickstart

This brief explains how to consume a ZQM attestation bundle: read the report, verify hashes, and import JSON into review tools.

## Reading a report

- Open `attestation_report.json` in any JSON viewer.
- Compare `manifest.json` SHA256 values to the artifacts on disk.
- Treat any mismatch as a tamper indicator; stop and preserve artifacts for review.

## Verifying hashes

```powershell
(Get-FileHash .\attestation_report.json -Algorithm SHA256).Hash
```

Compare the result to `manifest.json`.

## importing JSON

- Splunk/JSON tools: import `attestation_report.json`.
- Excel: use `Data -> From JSON`.
- ELK: ingest via filebeat module or JSON decode.

## Recommended triage

1. Isolate host if any control is UNKNOWN due to failed access.
2. Export `manifest.json.p7s` and `seal_qseal.json.p7s` to your evidence store.
3. Escalate to IR if boot state changes between baselines.

### Integration checks

- SOC/MSP review uses `boot` and `services` fields first.
- Compliance review uses control-set hashes in `manifest.json`.
- Legal hold uses CMS signatures, not JSON alone.
