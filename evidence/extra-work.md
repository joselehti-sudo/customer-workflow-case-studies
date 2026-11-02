# Extra-work case: verification record

[Case study](../cases/extra-work-approval.md) · [Evidence index](../EVIDENCE.md)

Reviewed **2 November 2026**. Source application: private `joselehti-sudo/autokorjaamo-saas`. Links below require access.

## Source identities

| Record | Identity |
|---|---|
| Problem and scope | [Issue #645](https://github.com/joselehti-sudo/autokorjaamo-saas/issues/645), specifically A–B |
| Owner-approved workday example | [24 October decision](https://github.com/joselehti-sudo/autokorjaamo-saas/issues/645#issuecomment-6383420403) |
| Delivery | [PR #1414](https://github.com/joselehti-sudo/autokorjaamo-saas/pull/1414), merged 25 October 2026 |
| Delivered head | `c367d5ff24a5a92dd34a613673b215addeb25f69` |
| Merge commit | `92b1e1422ebe5b264ee9ac9ff544fa2ba2b10962` |
| Current main used for source inspection | `7c5066f7953a10a4ec73397f903d66b27b8d32a5` |

## Directly inspected now

- The GitHub PR metadata records the merge and delivered head above.
- Current `packages/domain-core/src/extra-work-draft-deletion.ts` rejects non-extra-work drafts, cancelled work orders, non-Draft versions, prior versions/lines/approval requests and links to findings.
- Current `packages/db/src/modules/proposals/work-scope-draft.ts`, `scopeRevision`, includes quantity, unit and pricing type in the version input.
- [Actions run 40153593499](https://github.com/joselehti-sudo/autokorjaamo-saas/actions/runs/40153593499), **attempt 2**, completed successfully on the delivered head. All **18 returned jobs** were successful: format, lint, typecheck, docker, test aggregate, inventory, four Vitest shards and eight browser shards. This is an inspection of recorded CI, not a newly started run.
- The matching before/after screenshots and mobile confirmation were visually inspected before publication.

## The failure and correction

[Review 5640666485](https://github.com/joselehti-sudo/autokorjaamo-saas/pull/1414#pullrequestreview-5640666485) blocked an intermediate head after reproducing deletion of a draft whose line quantity had changed.

The [correction record](https://github.com/joselehti-sudo/autokorjaamo-saas/pull/1414#issuecomment-6391568012) describes the expanded version check, three field-specific API cases, a two-session browser scenario, and a negative control failing on the earlier code.

[Review 5641100351](https://github.com/joselehti-sudo/autokorjaamo-saas/pull/1414#pullrequestreview-5641100351) accepted the corrected head. These were AI review sessions. The portfolio does not attribute their defect discovery or implementation to Jose.

The PR also records tests for publication/deletion races, access boundaries, reload persistence, original approval preservation and keyboard focus. Those checks were **not rerun** in this portfolio work.

The first CI attempt was not successful; the delivery notes associate its rerun with a Helsinki daylight-saving-time test issue (#1425). The reported successful result here explicitly refers to attempt 2.

## Screenshot provenance

Original screenshot branch: `screenshots/claude/addon-draft-send-delete-645-20261024`.

| Public asset | Original file |
|---|---|
| [Before](../assets/extra-work-before.png) | `01-uudemman-lahetys-ennen-1440.png` |
| [After](../assets/extra-work-after.png) | `01-uudemman-lahetys-jalkeen-1440.png` |
| [Mobile confirmation](../assets/extra-work-delete-mobile.png) | `05-poiston-kysymys-jalkeen-390.png` |

They show a local synthetic workshop/customer fixture. Names, vehicles and amounts belong to the test scenario. Existing red annotations were retained; images were not generated or altered for this portfolio.

The visual capture predates the final stale-data correction. It demonstrates the interaction change, not that later server-side safeguard. The correction has separate source and test evidence.

## Boundaries

Issue #645 remains broader than this delivered slice: replacement versions and parts of the approval/share flow are separate work. A media-read feedback issue (#1418) remained a follow-up at delivery. The portfolio did not determine its current resolution.

No live workshop session, deployment check, customer interview or business measurement was performed here. Merge and successful CI do not establish those outcomes.
