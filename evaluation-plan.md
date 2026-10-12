# Evaluation Plan

## Objective

Evaluate whether provenance tracking and deterministic action controls help identify and block unsafe simulated actions while keeping false positives manageable.

## Test groups

1. **Benign cases:** Normal documents and ordinary simulated requests.
2. **Single-session adversarial cases:** Untrusted content is retrieved and influences a simulated action in the same session.
3. **Cross-session cases:** Untrusted content is stored or made retrievable in one session and influences a later proposed action.
4. **Unrelated-content cases:** Adversarial-looking content is present but does not influence a sensitive action.
5. **Missing-provenance cases:** A proposed sensitive action has incomplete or missing source records.

## Baselines

Compare the prototype against a simple baseline such as prompt-only keyword/rule checks. Clearly document the baseline's rules so the comparison is reproducible.

## Metrics

- **Detection rate:** Correctly flagged test attacks divided by all attack test cases.
- **False-positive rate:** Benign cases incorrectly flagged divided by all benign test cases.
- **Block rate:** Unsafe simulated actions blocked divided by unsafe actions proposed.
- **Provenance completeness:** Relevant source-to-action links recorded divided by links expected from the test design.
- **Latency overhead:** Additional processing time introduced by tracking and policy checks.

## Experimental procedure

1. Define and freeze the test cases before evaluating.
2. Run each case against the baseline.
3. Run the same cases against TRUSTFALL.
4. Record outcomes and processing time.
5. Calculate metrics from the recorded outcomes.
6. Report failures, limitations, and any changes to the test design.

## Results

No experimental results have been collected yet. Add a dated results table only after running the tests. Do not invent accuracy numbers or claim superiority without evidence.
