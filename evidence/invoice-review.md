# Verification notes

Prepared on **2 November 2026**. This page summarises selected records from the private application repository. Public readers can inspect the screenshots and this explanation; the underlying code, reviews and CI logs are not publicly accessible.

## Source versions

| Record | Reference |
| --- | --- |
| Requirement | Issue #1394: show this visit's odometer in invoice review |
| Implementation | PR #1454 |
| Reviewed PR version | `619a1c3094038242ebd6b2c3b12ee5f54f147fee` |
| Merge | `237c1b6a6b5b883704c1cb56773dcd3fedb8760c`, 27 October 2026 |
| Main branch inspected for this case study | `7c5066f7953a10a4ec73397f903d66b27b8d32a5`, 2 November 2026 |
| Recorded GitHub Actions run | `40568391954`, 27 October 2026 |

## What the evidence supports

**Implementation and test definitions inspected on 2 November.** The current invoice preview conditionally displays the prepared visit reading for invoices. It distinguishes zero from an absent value and uses the document's publication language. The component tests cover Finnish and English formatting, zero, null and absent readings, no substitution of an older value, and the unchanged work-report view.

**Recorded focused checks on 27 October.** The implementation report and separate AI review report record 32 passing tests across the preview, invoice PDF and odometer API test files, plus four passing focused browser runs. The browser test checks both document languages, 1440 px and 390 px layouts, the issued invoice's stored value and text extracted from the downloaded PDF.

**CI result read from GitHub on 2 November.** All 18 jobs returned for the recorded run completed successfully. They include format, lint, type checking, Docker, test inventory, four unit/integration test shards, eight browser-test shards and the aggregate test job. This confirms the recorded delivery run; it is not a new test run of the current main branch.

**Visual evidence.** The two published images are the existing before/after screenshots from the local synthetic-data test run. They show the same example visit reading, language and layout. They are not screenshots of real customer data or of a live workshop session.

## Attribution

The original gap was raised during an earlier AI-assisted review. Jose defined and approved the bounded user outcome and authorised delivery. AI agents performed implementation, technical testing and a separate review session. Multiple agent sessions used the project owner's GitHub account; this should not be read as a team of separate human developers or reviewers.

## Limits

- Tests were not rerun to prepare this public write-up.
- No measured reduction in errors, processing time or support work is claimed.
- These records do not establish deployment verification or validation with real workshop users.
- This case concerns one invoice-review change, not the production readiness of the whole application.


[Back to the case](../cases/invoice-review.md) · [Evidence index](../EVIDENCE.md)
