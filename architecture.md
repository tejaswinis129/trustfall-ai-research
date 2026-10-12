# Proposed Architecture

## Components

### 1. Agent simulator
A small controlled agent that reads synthetic documents, retrieves stored context, and proposes actions. Initially, actions should be simulated rather than executed against real systems.

### 2. Provenance event tracker
Record structured events with an event ID, timestamp, source ID, trust label, session ID, parent event IDs, and proposed action ID where applicable.

### 3. Influence graph
Represent recorded relationships between documents, retrieved memories, decisions, and proposed actions. The graph shows traceable links in the application; it does not claim direct access to a model's hidden reasoning.

### 4. Policy engine
Use deterministic rules to decide whether an action can proceed, should be blocked, or requires human approval. For example, a sensitive simulated action may require verification if its supporting source is untrusted.

### 5. Dashboard
Display the event timeline, source-to-action graph, policy decision, and before/after simulation results.

## Data flow

1. A document enters the sandbox.
2. The agent reads or retrieves it.
3. The tracker records provenance events.
4. The agent proposes a simulated action.
5. The policy engine evaluates the action and its recorded sources.
6. The dashboard shows the decision and evidence trail.

## Suggested technology stack

- Python for the prototype and policy engine
- FastAPI for the API
- SQLite or JSONL for early event storage
- NetworkX for graph relationships
- React for the dashboard
- An optional language model for agent behavior and plain-language summaries

## Safety design

- Start with synthetic documents and simulated actions.
- Do not connect the prototype to real email, payments, cloud accounts, or production tools.
- Keep policy enforcement outside the language model.
- Treat model-generated explanations as summaries, not authoritative evidence.
- Log why each policy decision was made.

## MVP boundary

The first version needs only one agent, a few synthetic documents, two sessions, a small number of simulated actions, and a graph showing the source-to-action chain.
