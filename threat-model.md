# Threat Model

## Scope

This document defines the proposed threat model for a controlled TRUSTFALL AI prototype. It does not claim that every real-world attack can be detected or prevented.

## Assets to protect

- Sensitive actions exposed by an AI agent
- Confidential data returned by tools
- Agent memory and retrieved context
- Tool credentials and permissions
- Audit records used to investigate decisions

## Attacker capabilities

For the prototype, assume an attacker can place misleading or adversarial text in an otherwise readable document or data source. The agent may retrieve that content in a later interaction.

The prototype will use synthetic content and a sandbox. It will not target real accounts, systems, or users.

## Trust boundaries

1. External documents and web content
2. Retrieval and memory storage
3. The model's context and proposed decisions
4. Tool calls and sensitive operations
5. Human approval and policy enforcement

## Example attack scenario

1. The agent reads a synthetic document containing an adversarial instruction.
2. The document is stored or becomes retrievable.
3. In a later session, the agent retrieves the content.
4. The agent proposes a sensitive action influenced by that content.
5. TRUSTFALL records the source-to-action path and checks the applicable policy.
6. The action is blocked or paused for verification if policy conditions are met.

## Proposed defenses

- Attach source identifiers and trust labels to retrieved content.
- Record links between source material, decisions, and proposed tool actions.
- Apply deterministic rules to sensitive operations.
- Require independent verification or human approval for selected high-impact actions.
- Keep an auditable event trail.

## Assumptions and limitations

- Provenance records must be correctly attached and protected from tampering.
- An influence graph may show a recorded relationship, but it does not prove the model's internal causal reasoning.
- The prototype may miss attacks that bypass instrumentation or exploit unmodeled paths.
- AI-generated explanations are not treated as proof; the underlying events and policy decisions are the evidence.
- The project will use synthetic data or an isolated, authorized lab.

## Abuse cases to test

- Benign document with ordinary instructions
- Untrusted content that does not affect a sensitive action
- Untrusted content retrieved in a later session
- Sensitive action proposed without a traceable source
- Benign content that triggers an unnecessary block

## Evaluation metrics

Measure detection rate, false-positive rate, unsafe actions blocked, provenance completeness, and added latency. Define the test set and counting method before reporting results.
