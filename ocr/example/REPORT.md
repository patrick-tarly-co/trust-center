# Tarly Cowork - Example Ongoing Certification Report

FedRAMP package ID: FR2628650874

Report period: 2026-05-27 through 2026-08-24

## Certification data changes

- Initial example report generated from the current certification package; no previous OCR exists.

## Planned certification data changes

Planning horizon through: 2026-11-24

- No certification-data changes are currently planned during this horizon.

## Accepted vulnerabilities

2 provider risk-acceptance decision(s) covering 2 vulnerability record(s) are in force, each with a named approving role, an approval timestamp, and controlled approval evidence retained outside this report.

### Accepted decision 1 of 2: approved by FedRAMP Program Owner on 2026-08-17

- **Accepted:**
  - Azure Backup should be enabled for virtual machines (defender-group-ad0290184eef11353984fe46, PAIN rating N2)
- **Next review:** no later than 2027-02-25
- **Rationale:** No Recovery Services vault exists and no virtual machine has point-in-time restore. Every VM in the boundary is an Azure Pipelines runner whose state is reproducible or disposable: two have no data disk, and the other two attach only a Docker layer cache that is rebuilt on demand. All four are provisioned from IaC with cloud-init, so the supported recovery action is redeploy rather than restore, and backing them up would preserve build caches the pipeline reconstructs anyway.
- **Residual risk:** Losing a runner costs a redeploy and cache rewarm, and any state left on a runner outside the pipeline working directories is unrecoverable. Customer and certification data are covered separately by PostgreSQL backups and the locked 400-day compliance-evidence archive.

### Accepted decision 2 of 2: approved by FedRAMP Program Owner on 2026-08-17

- **Accepted:**
  - Virtual networks should be protected by Azure Firewall (defender-group-6557fc98debafa727527876d, PAIN rating N2)
- **Next review:** no later than 2027-02-25
- **Rationale:** No Azure Firewall is deployed, so outbound traffic from the Cowork virtual networks is not filtered, FQDN-restricted, or IDPS-inspected. Azure Firewall Standard exceeds the total infrastructure spend of the offering for controls substantially duplicated by the existing design: inbound traffic reaches only Front Door with managed WAF rules, the Container Apps environments are private, and Storage, Key Vault, PostgreSQL, and ACR are reachable only through private endpoints with public access denied.
- **Residual risk:** A compromised workload could reach an arbitrary internet endpoint, and detection of that would depend on platform and application telemetry rather than network-layer inspection.

### Population reconciliation

- Grouped vulnerability record(s) reconciled: 13
- Under active remediation with a recorded owner and target date: 9
- Carrying a final disposition: 2
- Under provider risk acceptance: 2
- Risk-acceptance decisions pending a controlled approval: 0

Separately, 0 KSI implementation gap(s) remain under remediation and independent review.

## Transformative changes

- No transformative changes occurred during this report period.

## Updated recommendations and best practices

- Follow the current Tarly Cowork Secure Configuration Guide at https://gov.tarly.co/trust/secure-configuration-guide.html.

## Agencies directly using the product

- No federal agencies directly used the product during this report period.

## FedRAMP Reportable Incidents

- Tarly attests that no FedRAMP Reportable Incidents occurred during this report period.

## Incident lessons learned and resulting changes

- Not applicable because no FedRAMP Reportable Incidents occurred during this report period.
