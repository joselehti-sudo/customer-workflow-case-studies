# From working behaviour to evidence of usefulness

[Portfolio](README.md)

**Proposed next work, not completed research.** No users have been recruited and no measurements below have been collected for this portfolio.

The cases already have implementation evidence. The next uncertainty is whether the intended users can complete the work correctly and whether the workflow earns its place in their day.

## 1. Office workflow: moderated task check

Use a local synthetic environment with an office operator. Record the software version, screen size and whether the participant has seen it before. Give the goal, not a list of buttons.

| Task | Scenario | Successful outcome | Observe |
|---|---|---|---|
| Send the intended proposal | Original work approved; older empty draft; newer front/rear brake proposal | User opens the newer proposal and identifies its scope and €280 total without changing the original approval | Wrong turns, assistance, completion, active time |
| Remove the accidental draft | Keep the brake work; remove the empty draft | User understands what deletion removes and confirms the correct target; it stays removed after reload | Confusion between Discard and Delete; hesitation |
| Recover from another person's edit | A second synthetic session changes quantity while confirmation is open | Old deletion is refused; user notices the change and can make a fresh decision | Error comprehension, recovery, lost context |
| Explain approval state | A proposal link exists but the customer has not decided | User correctly distinguishes prepared, shared and approved states | Any belief that copying a link means approval |
| Check the invoice | This visit has an odometer reading different from the vehicle's older history | User checks this visit's value before issuing the synthetic invoice | Whether the field is found and understood |

Record unaided completion separately from completion after a hint. Stop a scenario if it changes the wrong approval or deletes unintended history; a faster time cannot compensate.

If a before/after comparison is useful, use the same synthetic task on the previous and current local versions. Vary the order across participants to reduce learning effects. Do not roll back a live shop to collect a baseline. A small sample gives directional observations, not a general usability claim.

## 2. Offer workflow: quality before speed

Start with an agreed synthetic evaluation set reviewed by the workshop operator. The following five scenario types cover different failure modes:

| Scenario | Required judgement |
|---|---|
| A complete request with agreed work and price | Full English review and Finnish promise describe the same offer |
| Two corrected technical facts | Only the requested facts and necessary disclosed dependencies change |
| Missing fact that changes the repair scope | Uncertainty stays visible and finalisation remains blocked |
| Material change after approval | The old approval is rejected |
| Reversed inclusion/exclusion in Finnish | A meaning error is identified even if every number matches |

The operator defines the expected work, price and terms before seeing the generated answer. Score each dimension separately: scope, main price, extras, exclusions, evidence and approval state. Preserve disagreements instead of counting a polished answer as correct.

Mechanical checks and human review get separate results. Count operator corrections, restarts, review time and whether the operator can explain what was approved. Use the existing manual sending boundary; this plan does not propose automated customer sending.

## 3. Small operational pilot

Only after the above tasks are understood, propose a limited pilot with the operator. Start with **10 consecutive eligible cases** rather than choosing the easiest successes. Ten is a planning choice for a first learning cycle, not a statistical adequacy claim.

Before beginning, agree eligible work types, stop conditions and who reviews each offer. Compare with the current manual process where practical; record case complexity and external waiting separately.

| Measure | Definition | How to report it |
|---|---|---|
| Unaided completion | Intended task completed without a hint or workaround | Successful tasks / attempted tasks |
| Review effort | Active minutes reviewing and correcting | Individual values and median; keep waiting time separate |
| Material correction rate | Scope, price, exclusion or approval needed correction | Cases with at least one material correction / reviewed cases |
| Reliability | Wrong version, lost draft or unintended action | Count and describe each event, including blocked attempts |
| Operator preference | Choice after using both workflows, with reasons | Attributed feedback with permission; no invented testimonial |

A wrong customer promise, unintended approval or lost history pauses the pilot for investigation. Failing safely can protect the customer while still revealing a usability problem.

## 4. What changes in the portfolio afterwards

Add the observation date, version, participant roles, task count and exact denominator. Explain what changed because of the feedback. Keep unsuccessful cases visible.

Only report savings, adoption or commercial outcomes if measured. Do not convert synthetic acceptance tests into customer outcomes or a few operator sessions into broad market validation.
