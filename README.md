# TRUSTFALL AI
### Cross-Session Trust and Action Security for AI Agents

**HackCulture — AI & Cybersecurity**

## Overview

TRUSTFALL AI is a proposed security layer for AI agents that investigates how untrusted information can influence sensitive decisions across multiple sessions.

AI agents may use external documents, retrieved content, persistent memory, and tools. Information from an untrusted source can influence a later decision, making it difficult to understand why an action was proposed or permitted.

TRUSTFALL AI proposes to track information provenance, identify risky information flows, and require verification before sensitive actions are executed.

## Problem Statement

Prompt-level checks alone may miss risks that emerge when information is retrieved, stored, and used later by an AI agent. Security teams need visibility into where information originated, how it influenced a decision, and why a sensitive action was allowed or blocked.

## Proposed Solution

1. **Information provenance:** Record the origin and trust label of information used by the agent.
2. **Influence graph:** Link source documents, retrieved memories, decisions, and proposed actions.
3. **Trust-aware action control:** Require verification or human approval when untrusted information influences a sensitive operation.
4. **Forensic replay:** Reconstruct the evidence trail behind a flagged decision.

## Proposed Architecture

- AI agent and document retrieval layer
- Provenance and event-tracking engine
- Trust and risk policy engine
- Sensitive-action approval layer
- Incident timeline and evidence dashboard

## Planned Demonstration

The prototype will use synthetic documents and a controlled AI-agent environment to simulate a delayed prompt-injection scenario. It will trace the untrusted source, identify its connection to a proposed sensitive action, apply a defensive policy, and compare the result with an unprotected baseline.

## Evaluation Plan

The proposed evaluation will measure:

- Detection rate across defined test scenarios
- False-positive rate on benign scenarios
- Number of unsafe actions blocked
- Traceability from source to action
- Additional response latency

Results will be reported only after experiments are conducted.

## Current Status

**Status: Research and prototype planning.**

The architecture and evaluation criteria are proposed and will be refined during implementation. Features and experimental results will be documented as they become available.

## Research Areas

- Prompt injection and indirect prompt injection
- AI-agent memory security
- Information provenance and data lineage
- AI application security
- Human approval and least-privilege action controls
