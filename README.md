<p align="center">
  <img src="assets/overview.svg" alt="Visual overview of Understand Chat" width="100%">
</p>

# Understand Chat

> Ask targeted questions about a codebase using its knowledge graph rather than guessing from filenames.

This repository packages a single, reusable Hermes skill as a documentation-first public reference. It explains the problem, operating contract, safety boundaries, expected evidence, and example usage without claiming a bundled runtime that is not present.

## Why this exists

Technical work becomes difficult to review when discovery, decisions, changes, and verification are mixed together. **Understand Chat** turns that work into an explicit sequence with visible inputs, outputs, review points, and completion evidence.

## Why the repository has this name

The shared `hermes-skill-` prefix identifies this as a portable Hermes workflow package. `understand-chat` names the capability directly—understand chat—so the repository remains searchable and understandable outside the original AI-OS workspace. The public title is **Understand Chat**.

## At a glance

| Question | Answer |
| --- | --- |
| What is it? | Engineering workflow packaged as a reusable Hermes `SKILL.md`. |
| What does it do? | Ask targeted questions about a codebase using its knowledge graph rather than guessing from filenames. |
| Who is it for? | Builders, operators, and reviewers who want a repeatable, inspectable workflow. |
| What is delivered? | A skill contract, examples, safety guidance, release checks, and rendered SVG diagrams. |
| Runtime status | Documentation-first reference package; connect it to the tools available in your own environment. |

## How it works

<p align="center">
  <img src="assets/workflow.svg" alt="Step-by-step workflow for Understand Chat" width="760">
</p>

1. Confirm the engineering question and allowed scope
2. Inspect the smallest relevant evidence set
3. Form a testable explanation or change plan
4. Perform the bounded analysis or implementation
5. Run focused checks and compare expected behavior
6. Report evidence, limitations, and next action

See [How it works](docs/HOW-IT-WORKS.md) for the detailed walkthrough, decision points, and verification checklist.

## Inputs

- A bounded repository, diff, runtime, or engineering question
- Constraints such as allowed files, tools, and change scope
- Existing tests, logs, or acceptance criteria

## Outputs

- An evidence-backed finding, plan, review, or implementation
- Verification results and remaining risks
- A concise handoff another engineer can reproduce

## Example request

> Use a disposable sample repository to ask targeted questions about a codebase using its knowledge graph rather than guessing from filenames. Return the result, the evidence used to verify it, and any limitations or actions that still require approval.

More scenarios and expected results are in [Examples](docs/EXAMPLES.md).

## Safety and trust model

<p align="center">
  <img src="assets/safety-boundary.svg" alt="Safety and approval boundaries for Understand Chat" width="900">
</p>

This workflow is designed around inspection and evidence; uncertainty must remain visible. It must stop when ownership, authorization, target state, or publication safety is ambiguous. Never place credentials, private endpoints, personal data, or environment-specific secrets in the skill package or its evidence.

Read [SAFETY.md](SAFETY.md) and [SECURITY.md](SECURITY.md) before connecting the workflow to real accounts, devices, repositories, or production data.

## What this repository does not claim

- It does not replace project-specific tests, code review, or production approval.
- It is not a hosted service, executable application, or vendor endorsement.
- It does not include credentials, private infrastructure, or the original personal AI-OS configuration.
- A successful example does not prove production readiness for every environment.

## Repository map

| Path | Purpose |
| --- | --- |
| `SKILL.md` | Concise trigger conditions and operating workflow used by an agent. |
| `docs/PRODUCT.md` | Problem framing, audience, boundaries, and readiness model. |
| `docs/HOW-IT-WORKS.md` | Expanded walkthrough with diagrams and verification points. |
| `docs/EXAMPLES.md` | Realistic safe, review-only, and stop-condition scenarios. |
| `docs/RELEASE.md` | Checks to complete before publishing a revision. |
| `assets/*.svg` | Accessible, GitHub-rendered visual explanations. |
| `tests/README.md` | Manual contract and package validation guidance. |
| `SAFETY.md` / `SECURITY.md` | Operational and disclosure boundaries. |

## Use this package

1. Read `SKILL.md` and confirm its trigger matches your task.
2. Copy the package into the skill location supported by your agent environment, or use it as a reference when authoring an equivalent workflow.
3. Replace tool assumptions with the tools actually available to you; do not add secrets to the repository.
4. Run the smallest safe example from `docs/EXAMPLES.md`.
5. Record verification evidence and review any consequential action before widening scope.

## Contributing

Improvements are welcome when they preserve narrow scope, honest capability claims, safe defaults, and reproducible verification. See [CONTRIBUTING.md](CONTRIBUTING.md).
