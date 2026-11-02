# Vire: when the training plan does not fit everyday life

[Back to the portfolio](../README.md)

**Work in progress.** This case describes a product question in an unfinished coaching app. The source and existing tests were reviewed on 2 November 2026. No new tests or coach interviews were run for this note.

## The question

If someone repeatedly struggles to complete a training plan, what should a coach ask first?

One possibility is that the plan takes more time than the person has. I want Vire to help a coach notice that and start a useful conversation. A missed exercise on its own does not explain what happened.

My role is product direction, deciding scope and reviewing whether the experience makes sense. AI agents do much of the implementation and technical testing. The time-flexibility decision record names me as the product owner; that does not mean I wrote or independently verified every part of the implementation.

## What the current implementation does

The coach defines the permitted adjustments to a session. The app can then apply a shorter version within those limits.

A separate rule looks for repeated time pressure in completed sessions. It uses the time available, the planned duration and recorded reasons for skipped exercises. The signal is suppressed during the first 14 days. That is an implementation choice, not a validated claim about how long everyone needs to learn a programme.

When the signal appears, the coach-facing guidance suggests discussing a shorter version or a more realistic time allowance. The signal does not establish why the client struggled.

## What the review brought into focus

There is an important overlap in the data. When the app shortens a session, it can mark the removed exercises with the same time-pressure reason used by the signal.

That leaves two things to understand:

- The shorter session may have worked exactly as intended.
- Repeatedly needing a shorter session may still show that the original plan does not fit.

Simply removing all automatically shortened sessions from the signal could hide useful information. Treating them all as unsuccessful sessions could be misleading too.

The delivery record already leaves this as an open product decision. Reading the code supports investigating it; this review did not reproduce a live defect or establish what a coach actually sees across the full workflow.

## The next decision to test

I would start by making the origin of the information clear to the coach. These are proposed synthetic scenarios, not completed user tests:

| Scenario | What the coach needs to distinguish |
|---|---|
| The client chooses an allowed shorter session and completes it | The agreed adjustment worked today; repeated use may still be worth discussing |
| The client reports running out of time after starting the session | There was a gap between the plan and what happened; ask what caused it |
| A new client takes longer while learning the routine | Early experience needs context; avoid drawing a conclusion from duration alone |

The next step is to agree the intended interpretation, check the implementation against it and ask a coach to explain what each example would lead them to do. If the coach cannot tell an app-generated adjustment from a client-reported problem, the display needs more context.

## What this case supports

It shows a concrete product question, an existing implementation and a reason to examine how the data is interpreted. It does not show improved retention, better training outcomes or a validated coaching product.

The useful outcome of the next check would be a clearer decision about what information the coach needs. That decision should come before adding more alerts.

## Source trail

Reviewed snapshot: `vire-coaching-os@74b04dd9f551f5c02b35c0a8875691e3eb162aa5`.

The source repository remains private. These references are for an authorised reviewer; this public summary is not enough to reproduce the application.

- `docs/ADR-0005-aikajousto.md`: draft decision record, product ownership and coach-defined adjustments.
- `src/lib/data/trainingMisfit.ts` and its existing test file: signal rules and three test cases. Read, not rerun for this note.
- `src/components/client/WorkoutLogger.tsx`: automatic shortening can use the same time-pressure reason.
- `src/lib/engine/attention.ts`: coach-facing suggested action.
- Pull request #72: records the signal feedback question as a deferred product decision.
