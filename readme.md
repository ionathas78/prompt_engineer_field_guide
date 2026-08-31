# Prompt Engineer's Field Guide: Thinking

A practical framework for designing AI systems that reason over evidence, context, memory, and their own generated material without quietly turning repetition into authority.

The **Thinking** field guide is concerned with the epistemic side of prompt engineering: how a model distinguishes what was observed, reported, retrieved, derived, predicted, hypothesized, or invented; how claims inherit authority from their sources; how working context is managed; and how a system should respond when evidence changes, conflicts, or fails to resolve a question.

Its two foundational principles are:

> **Keep the data. Kill the narrative.**  
> Context is a structured state ledger, not a dialogue script.
>
> **Authority follows lineage, not volume.**  
> A claim's weight comes from where it came from, never from how often, how confidently, or how eloquently it appears.

## What's Here

The project separates human-facing design guidance from model-facing implementation.

### Thinking - Guide

The human-facing guide.

It presents the principles behind the framework in compact, memorable language, followed by a Reference Model that makes the underlying epistemic structure explicit.

The guide covers:

- epistemic types and warrant
- source authority and provenance
- evidentiary lineage and corroboration
- dependency propagation
- working-state and scratchpad discipline
- contradiction and unresolved evidence
- evidence-pending versus framework-contingent questions
- epistemically safe compression
- entrenchment and context recovery
- operational rigor and performance integrity

The scratchpad rules are conditional. A scratchpad exists only when the prompt engineer provides one. When no scratchpad is available, the model should not simulate or claim one in ordinary context.

### Thinking - Prompt

The model-facing companion.

It contains the Reference Model and an annotated Agent Directive Stack translating the Field Guide's principles into instructions intended for model use.

The comments are intentional. They are not merely implementation decoration: they show the human reader how each directive implements a principle from the Field Guide and what failure mode it is intended to prevent.

The prompt is constrained to behavior a model can actually perform within its available interaction environment. It does not assume imaginary access to context deletion, hidden memory controls, runtime state, or other operations the model has not actually been given.

## Scope

The **Prompt Engineer's Field Guide** is intended as a practical, evolving guide to prompt engineering.

It is not comprehensive yet.

**Thinking** is the first developed domain: a framework for the epistemic side of prompt engineering, including evidence, inference, provenance, working context, contradiction, compression, and recovery.

Future domains may extend the Field Guide into other areas of prompt engineering as useful principles emerge and survive practical testing. The project is deliberately grown from observed problems and tested solutions rather than from an attempt to define the entire field in advance.

The current contents should therefore be read as a beginning, not a boundary.


## Design Philosophy

The framework treats context as working state rather than accumulated conversation history.

Generated text does not become established fact merely because it remains in context. Repetition does not create corroboration. Multiple apparent sources do not create independence when they share the same evidentiary ancestor. Successful execution of an operation does not establish the correctness of conclusions drawn from its result.

Likewise, the grammatical shape of a question does not dictate the legitimate shape of its answer. Some questions are waiting for better evidence. Others are contingent on definitions, values, or competing frameworks and cannot be settled merely by gathering more facts.

The goal is not to make a model *sound* cautious.

The goal is to make epistemic discipline operational.

## Authorship and Development

This project was composed entirely using generative AI under human direction, testing, review, and editorial control.

The framework was developed iteratively through practical observation of model behavior, experimentation, counterexamples, critique, and cross-model refinement. The human role included identifying failure modes, defining problems, designing and evaluating experiments, supplying counterexamples, challenging proposed rules, selecting among competing formulations, and directing subsequent revision.

Multiple generative AI systems participated in analysis, criticism, formulation, and revision. Consequently, agreement among those systems should not itself be interpreted as independent validation of the framework. One of the framework's central claims is that plurality is not necessarily independence.

The final prose of the project is AI-generated.

This provenance distinction is intentional: **composition, conceptual contribution, experimental observation, editorial judgment, and evidentiary authority are not the same thing.**

## Status

The framework is an evolving design document rather than a claim of settled theory.

Its rules are intended to be tested against actual model behavior. Where a principle proves model-specific, non-operational, redundant, or unsupported by observed behavior, it should be revised or removed.

In the spirit of the framework itself, persistence in this repository does not confer authority.

## Files

- `Thinking - Guide.md` — human-facing Designer's Guide and Reference Model
- `Thinking - Prompt.md` — Reference Model and annotated Agent Directive Stack

## License

Add the license appropriate to the repository here.