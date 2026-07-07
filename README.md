# Tarly Trust Center — FedRAMP 20x

Public, machine-readable FedRAMP 20x certification data for **Tarly Cowork**
(Pincus Technologies Inc, dba Tarly).

Human-facing trust center: **<https://gov.tarly.co/trust/>**

## Contents

| File | What it is | Updated |
| --- | --- | --- |
| [fedramp.json](fedramp.json) | FedRAMP certification package overview ([schema](https://fedramp.gov/schemas/fedramp-certification-package-overview-schema-2026-06-24.json)) | on change |
| [ksi-results.json](ksi-results.json) | Machine-readable Key Security Indicator (KSI) evaluation results | nightly |
| [KSI-STATUS.md](KSI-STATUS.md) | Human-readable KSI status table | nightly |

## How this data is produced

KSI evaluations are generated automatically by Tarly's compliance pipeline,
which runs nightly against production infrastructure (Terraform state, Azure
resource probes, log-analytics queries, TLS scans, identity-provider
configuration) plus attested manual facts. Statuses are published here
unmodified — including KSIs we do not yet meet and their remediation target
dates. Detailed evidence bundles are retained in immutable storage and shared
with agencies and our third-party assessor on request; the
`evidence-manifest-sha256` on each KSI is the integrity anchor for that
evidence.

The git history of this repository is the public record of how our posture
has changed over time.

## Catalog

Evaluated against the [FedRAMP Consolidated Rules](https://github.com/FedRAMP/rules)
2026 KSI catalog (46 KSIs).

## Contact

Security: patrick@tarly.co · Sales: cary@tarly.co
