# AI work: keeping recommendations separate from decisions

[Back to the portfolio](../README.md)

**A small evaluation case, with a follow-up still pending.** Reviewed on 2 November 2026 from recorded work in June 2026. No new model runs were performed for this note.

## Why I looked at this

Working with AI agents means regularly asking what has been done, what remains and what to do next. Those answers help me make decisions, so I care about how clearly they separate facts, suggestions and things I have actually approved.

This work is documented in Judgment Genesis. I direct the work and review what the findings support. AI agents prepared and graded the recorded evaluations. This is a practical investigation within my own workflow.

## The observation

A June run record describes five scenarios using fresh agent sessions from the same recorded model class and repository snapshot.

In one scenario, the user asked for unresolved blockers and the order in which to clear them. The agent suggested a sequence. It also explained that the first three items were independent and that its sequence was a recommendation.

That distinction matters. The agent was answering an explicit request for advice. The record does not show it carrying out an unapproved plan.

The concern was how the answer could be read: someone moving quickly might treat the suggested sequence as an agreed roadmap.

## What changed

The documentation was updated so that the decision table starts by saying that no order is implied. The related guidance also makes the difference between a status report and a recommended sequence explicit.

That is an observed concern followed by a wording change. A targeted comparison of the old and new wording is still pending. I cannot yet say that the change improved the agent's answers.

## What makes the evidence limited

The run record contains summaries of responses and AI-assigned grades, rather than a complete set of independently checked transcripts.

The ordering example received a qualified pass even though its stated failure condition was partly triggered. The evaluator gave weight to the independence disclaimer and the fact that the answer remained a recommendation. That judgement is worth examining; a headline pass count would hide it.

I accepted the record at its stated scope. The five scenarios do not establish general model reliability, and accepting a record does not remove its limitations.

## The next useful comparison

Before rerunning this scenario, I would define the distinction we want to assess:

- A useful recommendation can explain a suggested order, its assumptions and any genuine dependencies.
- A misleading answer presents a suggested order as already agreed or required when the evidence does not support that.

Then I would compare the old and new instructions using the same task, fresh sessions and repeated trials. The record should include the exact model and settings, the supplied context and the complete sanitised responses.

Reviewers should score usefulness and clarity about decisions separately, without knowing which instruction version produced each answer. Disagreements should stay in the results. The wording change only earns a stronger claim if that comparison supports it.

## What I take from this

The work has given me a concrete question to investigate in instructions and handovers: can the next person tell what is known, what is suggested and what has been decided?

This case shows why I changed the documentation and what I still need to check. It does not show that the change solved the problem.

## Source trail

Reviewed snapshot: `judgment-genesis@f5fe3c248cea09af1b26de9b0be7812f8cfa0c1d`.

The repository remains private. These are references for an authorised reviewer, not publicly reproducible evaluation data.

- `docs/evals/runs/0001-manual-trace-batch-2026-06-10.md`: five recorded scenarios, including S07.1 and the evaluator's explanation.
- `docs/method/review/0051-manual-trace-batch-0001-acceptance.md`: my acceptance at the recorded scope and attribution of AI preparation and grading.
- `STATE.md`: the revised introduction to the decision table.
- `docs/evals/LEDGER.md`: the targeted S07.1 retest remains pending. The later six-prompt batch is not a controlled old/new comparison.
