## Epistemic Design Framework (v4.1)

## Part 1: Designer's Guide

Human-facing. For designing context schemas, memory architecture, and system prompts. Terse by design—these are working principles to carry in your head, not an exhaustive spec.

## The Pillars

* **Keep the data. Kill the narrative.** Context is a structured state ledger, not a dialogue script.
* **Authority follows lineage, not volume.** A claim's weight comes from where it came from—never from how often, how confidently, or how eloquently it appears.

## The Moves

* **Know what you know.** Keep observation, report, measurement, retrieval, derivation, prediction, hypothesis, and invention distinct. A claim can say only what its evidence warrants. "Ninety percent chance of a tornado" means ninety percent chance of a tornado—not a tornado.

* **No one gets a crown.** Tools don't get a crown. Users don't get a crown. Models don't get a crown. The user is right about what they want. They are not right about math just because they're the user. A successful tool run proves the tool ran—not that what you concluded from it is true.

* **Follow the lineage.** Repetition isn't corroboration. Five models downstream of one claim are still one lineage. If five sources agree, check whether they share a parent before you count them as five. Independence comes from separate evidentiary method—not from asking a different model. The same model, re-deriving independently, can corroborate itself; five different models echoing one uncorroborated claim cannot.

* **When a premise falls, its dependents fall with it.** When a premise changes or loses authority, revisit what was built on it. Lost provenance reduces authority—it doesn't get grandfathered in just because it's been sitting in context a while.

* **Keep a hard scratchpad, if available.** A scratchpad exists only when the prompt engineer provides one. When available, keep only state that can change what happens next. No state change, no write. Replace old state instead of appending its history. Give reasoning a bounded, disposable scope for a sub-task, and let it go when the sub-task closes. Current state lives in the scratchpad; how you got there lives in an indexed log; why you believe it lives at the source. If no scratchpad is available, do not simulate one in ordinary context.

* **Let evidence change things.** Contradiction calls for reevaluation, not defense. Go back to the evidence and derive again. A sound inference can survive contradictory evidence outside its own scope—a prediction that didn't pan out was still a valid prediction. An unsupported conclusion doesn't get that protection.

* **When evidence doesn't settle it, say so.** Don't force a synthesis for the sake of sounding resolved. State both readings, name what evidence would break the tie, and leave it there. Tone isn't evidence. Agreement isn't evidence. An argument, however well-built, isn't evidence.

* **Some questions aren't waiting on evidence at all.** Not every open question is open because the evidence is thin—some are open because they're normative, definitional, or values-laden, and no amount of proof closes them. "Does God exist," "should this get funded"—these don't have a fact pending discovery, they have competing frameworks. Don't answer these as if your own proof is conclusive. Lay out what each framework implies and let the tension stand. This is different from an evidence-pending question—don't wait for evidence that isn't coming.

* **Compress without promotion.** Compress the conclusion. Preserve the qualifier. Index the rationale. "Tornado: 90%" is compression. "Tornado" is fabrication.

* **Watch for entrenchment.** An error is ordinary. An error that survives better evidence is dangerous. When a position starts accumulating defenses instead of responding to evidence, that's the signal—return to the anchors and re-derive.

* **Reset lives with you, not the model.** If entrenchment or contamination is bad enough that the working context itself needs to be wiped and rebuilt from verified anchors, that's an operation you perform as the engineer between turns—not something the model can do to itself mid-generation. Design the model to signal "this needs a reset," and you act on that signal. Don't write a directive that asks the model to purge its own context; it has no hand on that lever.

* **Rigor is an action, not a posture.** Never design a prompt that asks a model to say it's being careful. Narrating caution isn't caution. If a condition calls for elevated rigor, the response is a structural action—re-derive, re-retrieve, cross-verify—not a sentence about being extra careful.

* **Trigger rigor from conditions, not self-report.** Decide in advance what should raise the bar: long or messy context, weak sourcing, extreme language, contradiction, a premise that keeps getting contradicted and not updated. These are properties of the input. Don't build a system where the model has to accurately sense its own degradation to know when to compensate—it isn't reliably able to.

---

## Part 2: Reference Model

Technical checksum. Nuance that doesn't need to live in working memory belongs here.

### Claim structure

```text
Claim { type, source, method, assumptions, warrant, scope, time, dependencies, uncertainty, status }
```

Fields retained only when material; may be represented by indexed reference rather than inline.

### Relational Matrix

```text
presence         ≠ authority
generation       ≠ establishment
repetition       ≠ corroboration
plurality        ≠ independence
execution        ≠ outcome
prediction       ≠ observation
confidence       ≠ evidence
compression      ≠ promotion
description      ≠ performance
prompt structure ≠ problem structure
```

### Core Axioms

* **Corroboration Limit** — Requires materially independent evidentiary lineage; shared ancestry discounts apparent plurality; a different model is not, by itself, an independent lineage.

* **Warrant Boundary** — Claims assert no more than source, method, assumptions, and scope support. Contradictory evidence updates the relevant state but doesn't retroactively invalidate a sound inference outside that contradiction's scope.

* **Answer-Space Validity** — A prompt’s proposed answer form does not establish the structure of the underlying problem. Validate the answer space before selecting within it.

* **Dependency Propagation** — Changed or invalidated premises flag material descendants for reevaluation. Lost provenance reduces authority; it is not replaced by contextual persistence.

* **Memory Bounds** — Working state is mutable and bounded; historical state is indexed; evidence is recoverable at its source; transient reasoning is disposable.

* **Compression Integrity** — Compression preserves epistemic type, qualification, uncertainty, contradiction, scope, and assumptions; it may drop recoverable rationale.

* **Resolution Class** — An unsettled question is either evidence-pending (resolvable in principle; hold both readings, name the resolving evidence) or framework-contingent (not evidence-resolvable; represent competing frameworks, do not force resolution). Misclassifying the second as the first produces false balance; misclassifying the first as the second produces manufactured symmetry where the evidence in fact favors a side.

* **Recovery Circuit** — Observable entrenchment triggers re-derivation from anchors. The model signals recovery need; the prompt context is reconstructed externally between turns.

* **Performance Integrity** — A claim of type RETRIEVED, MEASURED, or VERIFIED requires an actual corresponding operation. Describing an operation procedurally does not satisfy this—an undone operation described as done is INVENTED, not the type claimed.

### Authorship Note

This document was composed entirely using generative AI under human direction, testing, review, and editorial control. Its concepts were developed iteratively through observation, experimentation, critique, and cross-model refinement. Human contribution determined the problems investigated, evaluated model behavior and proposed solutions, supplied counterexamples, selected among competing formulations, and directed revision. The final prose was generated by AI.