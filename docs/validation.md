# Validation and roadmap

Evidence snapshot: **2026-09-17**, alpha **0.3.0-alpha.1**. Results below refer to the private implementation and are summarized here; CI logs are not publicly accessible in this showcase.

| Area | Recorded evidence |
| --- | --- |
| Merge CI | Go, Web, Helm and Secret scan completed successfully |
| Backend | Format/vet, short tests, race checks and mandatory PostgreSQL integration |
| Integration guard | Unavailable mandatory database causes failure rather than a skipped check |
| Frontend | Frozen-lockfile dependency install and production build |
| Deployment | Helm lint/render scenarios and production authentication smoke |
| Offline package | linux/arm64 clean install, repeat install and dirty migration-state rejection |
| Recovery | PostgreSQL backup restored into a separate disposable database |
| Secrets | Tracked source and Git history scans; synthetic historical findings reviewed |
| Dependency scanning | No affected application call paths reported in the recorded govulncheck runs |
| Interface | Real local login/setup screenshots; additionally, 18 captures from actual application output using explicitly labeled synthetic laboratory data |

## Limits

- No recorded L3 live-device validation, production pilot acceptance or independent penetration-test report.
- Vendor coverage varies; 34 catalog entries do not mean 34 fully validated integrations.
- Linux/amd64 runtime testing has not been performed for this package.
- A frontend bundle-size warning and an unused OpenPGP module advisory remain recorded.
- JWT revocation is fail-open during Redis outages.
- Framework mappings do not establish certification or legal compliance.
- Load, long-running operation, high availability and disaster recovery at target production scale remain to be validated.

## Next milestones

1. Record live-device laboratory results for selected FortiGate, Cisco and Aruba workflows.
2. Expand target platform validation and measure performance at a declared workload.
3. Arrange an independent security assessment and address its findings.
4. Run a scoped pilot with explicit acceptance and recovery criteria.
5. Extend the recorded synthetic laboratory walkthrough with verified live-device evidence when available.

No dates, pilot customers or benchmark results are claimed before evidence exists.

## Visual laboratory capture — 2026-09-17

A separate isolated environment used four synthetic devices and six API-uploaded snapshots. Eighteen screenshots, a silent browser tour and a printable report demonstrate actual application output from private commit `6e087e1`. This development branch fixes bulk-read authorization/tenant checks and overview history queries; screenshots are not a claim that the original alpha archive already includes those fixes.

Auth race tests cover same-tenant read access for viewer/operator/admin, cross-tenant rejection, unauthenticated rejection and unknown POST denial. API compilation and frontend production build passed. The browser capture exercises the documented screens; the no-snapshot device intentionally produces a 409 static-audit response. See [visual tour](visual-tour.md).
