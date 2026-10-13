# CVE Research Reports

English research reports by **Wentao He (Bob-wentao)**, consolidated from the original research repositories.

This **private** collection contains the ten CVE identifiers listed in my CV. Each directory explains the affected operation, attacker prerequisites, source-level root cause, demonstrated impact, reproduction procedure, evidence limits, and remediation. Existing proof-of-concept files are included where available.

## Report Index

| CVE | Product | Research report | Record / allocation status |
| --- | --- | --- | --- |
| [CVE-2026-74763](reports/2026/CVE-2026-74763/README.md) | Apache Shiro | Guice superclass authorization annotations bypassed during interceptor binding | Owner-confirmed allocation; public record unavailable |
| [CVE-2026-88019](reports/2026/CVE-2026-88019/README.md) | Apache Shiro | Form-resubmission allowlist challenge relay exposes session cookies and cached form data | Owner-confirmed allocation; public record unavailable |
| [CVE-2026-88041](reports/2026/CVE-2026-88041/README.md) | Apache Tomcat | Stale HTTP/2 HeaderEmitter writes trailers into a recycled request | Owner-confirmed allocation; public record unavailable |
| [CVE-2026-104972](reports/2026/CVE-2026-104972/README.md) | vLLM | Request-selected Molmo2 video backend ignores num_frames and materializes every source frame | Owner-confirmed allocation; public record unavailable |
| [CVE-2026-102806](reports/2026/CVE-2026-102806/README.md) | OpenClaw | Media root allowlist crosses sandbox session filesystem boundaries | Published CVE record |
| [CVE-2026-102807](reports/2026/CVE-2026-102807/README.md) | OpenClaw | Read-scoped MCP App tickets permit write-scoped tool calls | Published CVE record |
| [CVE-2026-108800](reports/2026/CVE-2026-108800/README.md) | RuoYi | State-changing GET delete routes bypass CSRF token validation | Published CVE record |
| [CVE-2026-108802](reports/2026/CVE-2026-108802/README.md) | RuoYi | Stored XSS in dictionary drawer preview through cssClass | Published CVE record |
| [CVE-2026-108803](reports/2026/CVE-2026-108803/README.md) | RuoYi | Existing authenticated sessions survive account disable | Published CVE record |
| [CVE-2026-108825](reports/2026/CVE-2026-108825/README.md) | RuoYi | Comma-delimited roleKey injects the Shiro admin role | Published CVE record |

## Reading the Reports

- Open an individual CVE directory for its English report and reproduction material. Run PoCs only against disposable, authorized local targets; several can delete lab data, leak lab cookies, or exhaust resources.
- A CVE identifier does not by itself mean a report is public. Keep this repository private until the responsible disclosure process permits publication.
- Published records were retrieved from the CVE Program API on **2026-10-13**. Four records could not be publicly retrieved; their mappings are based on allocation correspondence and report identifications provided by the repository owner. An unavailable record is not evidence that an identifier is invalid, reserved, or rejected.
- **CVE-2026-74763** and **CVE-2026-88019** combine related reports by multiple researchers according to the allocation correspondence. These reports describe my contribution, not the full scope or sole authorship of the combined CVEs.
- The Tomcat cross-connection test is related evidence for the same stale-HeaderEmitter root cause, not an eleventh CVE.
- Affected/fixed versions from public records are distinguished from versions inspected or tested in the original research. The RuoYi dictionary XSS report explicitly records a discrepancy between the CNA's version range and the research's drawer-introduction evidence.
- Prior runtime results belong to the original research. This collection reviews sources and existing artifacts; it does **not** claim that every exploit was executed again during consolidation.
- Two original test revisions could not be retrieved from upstream: the Shiro form-resubmission report and RuoYi account-disable report. The owner accepted archival consolidation with explicit limits. Separately inspected release/parent code is not presented as the unavailable tested checkout.

## Repository Layout

```text
README.md                  Research index and disclosure notes
catalog.json               Machine-readable CVE-to-source mapping and provenance
reports/2026/CVE-.../
  README.md                English technical report
  poc/                     Existing reproduction artifacts, when available
  evidence/                Selected portable evidence, when included
```

## Sources and Provenance

The [catalog](catalog.json) records immutable original-report links, repository snapshot commits, SHA-256 hashes, mapping evidence, and verification scope. Individual reports link to the upstream source and the applicable public record where available. Original repositories are not modified or deleted.

Distributed text is UTF-8 with LF line endings. Original-report hashes refer to Git blob bytes, not platform-converted checkout bytes. [SHA256SUMS](SHA256SUMS) covers the final collection files; evidence redactions and portability edits are documented in the relevant report.

Only material relevant to the ten CVEs is included. Unassigned findings, unrelated Jenkins reports, vLLM embedding/SageMaker findings, OpenClaw desktop-observer findings, working prompts, the CV itself, and private email bodies are excluded.

## Attribution and Disclosure

Researcher: **Wentao He**. GitHub: [Bob-wentao](https://github.com/Bob-wentao).

Upstream code excerpts and existing PoCs retain their original notices where present. No new blanket license is applied to third-party material. Fix status and disclosure dates can change; consult the linked vendor advisory before using a report to assess a current deployment.
