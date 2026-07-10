# Control Coverage Overview

Brief control-coverage map for ZQM attestation outputs. This is a methodology reference, not a certified audit scope.

## Control categories

| Category | Example controls | Attestation signal |
|---|---|---|
| Boot/firmware | SecureBoot, TPM state | SecureBootEnabled, firmware hash |
| Endpoint protection | Antivirus, real-time protection | Antispyware enabled, signature age |
| Firewall | Windows Firewall, profile state | FirewallEnabled |
| Update hygiene | OS patch currency | Antispyware signature date |
| Evidence | Baseline JSON, CMS signature | manifest.json.p7s present |

## How to compare

- Map `Invoke-AttestationBaseline.ps1` controls to your control framework.
- Use `docs/ControlMapping.md` in `ZQM-Computing/zqm-public-tools` for generic CIS mappings.
- Map `manifest.json` hashes to your config-management DB.
