# agentswarms

Notes and source material on **how agent systems are designed** — collecting and comparing the
different architectural patterns people use to build systems that AI agents operate inside.

## Why this repo exists

There is no settled way to design a system for an agent to drive. Different people are converging
on very different answers:

- monolithic single-agent loops with a rich internal world model
- hierarchical planner/worker splits
- flat swarms of peers that coordinate by shared artefacts
- thin orchestration over direct model calls, with almost no architecture at all

Each design makes a different bet about what agents are bad at — losing context, hallucinating
state, burning tokens, collapsing uncertainty to the single most likely story. This repo captures
those designs in enough detail to compare them, including the arguments against each.

## What's here

`docs/` holds one file per source, dated and attributed:

| File | Subject |
|---|---|
| [`docs/20260831-jeffrey-emmanuel.md`](docs/20260831-jeffrey-emmanuel.md) | Jeffrey Emanuel's "agent-ergonomic" prompt and the system design it produces: one cognitive centre, a canonical operating loop, an L0–L10 abstraction tower, `SituationCapsule` as the single read surface, `WorldEnvelope` instead of a confidence scalar, and `ActionAffordance` frontiers instead of hidden recommendation scores. Includes the literature that supports it (Endsley, BDI, SOAR/ACT-R, affordances) and the case against it (unearned complexity, unbounded cost of keeping possible worlds live). |

Each doc is written to be **self-contained and portable**: another agent should be able to pick one
up cold, without the conversation that produced it, and either apply the design to a new domain or
critique it.

## Conventions

- One document per source, named `YYYYMMDD-<source>.md`.
- Separate the **method** (the portable, domain-independent pattern) from the **specimen** (the
  particular project the source happened to be building). Conflating the two is the main way these
  write-ups go wrong.
- Record the counter-arguments alongside the design. A pattern with no stated failure mode has not
  been understood yet.
- Mark what was *not* established. Don't invent the missing parts.

## Status

Early. One source so far, and it documents a single-agent cognitive architecture rather than a
multi-agent swarm — useful as a baseline for what the multi-agent designs are reacting against.
Multi-agent and swarm topologies are the next thing to add.

## Licence

Apache 2.0 — see [LICENSE](LICENSE).
