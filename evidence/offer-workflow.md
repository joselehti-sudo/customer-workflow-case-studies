# Offer workflow: verification record

[Case study](../cases/human-reviewed-offers.md) · [Evidence index](../EVIDENCE.md)

## Fresh offline check — 2 November 2026

Source: private `joselehti-sudo/Autojerry-Offer-Agent`, commit
`a70c78c90909130a324c2553a4be20d91ff510f2`.

The AI assistant preparing this portfolio copied six source/test files into an isolated temporary workspace and ran the existing tests. Their Git blob identities matched the pinned source.

- Runtime: **Node v24.22.1**.
- Command: `node --test --test-reporter=tap tests/offer-review.test.cjs tests/send-block.test.cjs`.
- Result: **45 tests passed, 0 failed, 0 skipped; exit code 0**.
- No dependency installation, model call, customer data or live browser was required.
- The submit tests execute the actual submit module and CLI source in an isolated context with a stubbed browser adapter. They assert zero browser calls.

[Raw TAP output](offer-check-2026-11-02.tap) · [Source and result manifest](offer-check-2026-11-02.json)

## What those tests establish

| Area | Relevant existing test |
|---|---|
| Bounded corrections | `two-fact correction preserves all price, wording, hours and extras`; `two-fact correction cannot also change price` |
| Current approval | `material changes make prior approval stale`; `offer approval must identify exact case and revision` |
| Evidence attribution | `owner assertion cannot be relabelled independent source verification` |
| Blocking uncertainty | `initial unresolved technical facts block approval`; `unknown price stays unknown and blocks approval rather than inventing a number` |
| Translation limits | `same-number semantic mistranslation is explicitly not proven by numeric checks` |
| Separate permissions | `offer approval is not knowledge-change approval` |
| Submit block | Direct submit, CLI submit and CLI submit with `--confirm` reject before touching a browser |

The meaning test is intentionally modest: the renderer identifies that semantic equivalence is not proven and requires meaning review. It does not demonstrate that a model reliably detects every mistranslation.

## Documentation inspected

At the same source snapshot: `README.md`, `AGENTS.md`,
`docs/BAHA-REVIEW-WORKFLOW.md`, `TUNNETUT-RAJAUKSET.md`,
`docs/PAIVITYS-V03-2026-09-24.md`, and relevant helper/test source.

The September update notes report 84 tests and synthetic Claude/Codex handover runs at that earlier version. Their original local transcripts are not in the source repository and were not rechecked here. Those counts are not the result of the fresh run above.

## What this does not establish

This was a selected two-file test run, not the whole test suite, a complete CLI workflow run or a security audit. It does not test model instruction-following, real English/Finnish semantic accuracy, repair suitability, profitability, Desktop UI behaviour, operator adoption or live AutoJerry sending.

The blocked submit helper is not a system-wide permission barrier. Other tools remain outside its scope. The project is a local trial with commercial and technical questions explicitly retained in its known-limitations document.

Application source and business materials stay private; the public output supports the reported run but does not make the private project independently reproducible.
