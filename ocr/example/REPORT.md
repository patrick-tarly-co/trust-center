# Tarly Cowork - Example Ongoing Certification Report

FedRAMP package ID: FR2628650874

Report period: 2026-07-11 through 2026-10-08

## Certification data changes

- Initial example report generated from the current certification package; no previous OCR exists.

## Planned certification data changes

Planning horizon through: 2027-01-08

- KSI-MLA-ALA: Medium-risk implementation gap; remediation detail is retained in controlled certification data.
- KSI-MLA-OSM: High-risk implementation gap; remediation detail is retained in controlled certification data.
- KSI-MLA-RVL: Medium-risk implementation gap; remediation detail is retained in controlled certification data.
- KSI-PIY-RES: Medium-risk implementation gap; remediation detail is retained in controlled certification data.
- KSI-PIY-RIS: Medium-risk implementation gap; remediation detail is retained in controlled certification data.
- KSI-RPL-ABO: High-risk implementation gap; remediation detail is retained in controlled certification data.
- KSI-SVC-ACM: High-risk implementation gap; remediation detail is retained in controlled certification data.
- KSI-SVC-RUD: High-risk implementation gap; remediation detail is retained in controlled certification data.

## Accepted vulnerabilities

1 provider risk-acceptance decision(s) covering 1 vulnerability record(s) are in force, each with a named approving role, an approval timestamp, and controlled approval evidence retained outside this report.

### Accepted decision 1 of 1: approved by FedRAMP Program Owner on 2026-09-21

- **Accepted:**
  - Virtual networks should be protected by Azure Firewall (defender-group-6557fc98debafa727527876d, PAIN rating N2)
- **Next review:** no later than 2027-04-01
- **Rationale:** No Azure Firewall is deployed, so outbound traffic from the Cowork virtual networks is not filtered, FQDN-restricted, or IDPS-inspected. Azure Firewall Standard exceeds the total infrastructure spend of the offering for controls substantially duplicated by the existing design: inbound traffic reaches only Front Door with managed WAF rules, the Container Apps environments are private, and the main customer storage account, Key Vault, PostgreSQL and ACR restrict public network access. The separate logging accounts use default-deny public endpoints with an Azure trusted-service writer bypass; private Blob reader endpoints are being added and verified separately.
- **Residual risk:** A compromised workload could reach an arbitrary internet endpoint, and detection of that would depend on platform and application telemetry rather than network-layer inspection.

### Population reconciliation

- Grouped vulnerability record(s) reconciled: 14
- Under active remediation with a recorded owner and target date: 9
- Carrying a final disposition: 4
- Under provider risk acceptance: 1
- Risk-acceptance decisions pending a controlled approval: 0

Separately, 8 KSI implementation gap(s) remain under remediation and independent review.

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
