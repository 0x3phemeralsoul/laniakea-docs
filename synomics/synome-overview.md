# Synome Architecture Overview

**Status:** Conceptual foundation
**Last Updated:** 2026-02-03

This document provides a high-level introduction to the Synome architecture. Each concept is detailed in companion documents.

---

## The Core Idea

> **Intelligence lives privately; power enters the world only through regulated apertures.**

The Synome architecture separates **private cognition** from **public action**. Teleonomes (autonomous AI systems) think privately, but can only affect the world through regulated, observable, revocable interfaces called beacons.

This separation enables AI systems to be both capable and constrained — they can improve themselves, accumulate knowledge, and pursue goals, but their power to act is always governed.

---

## The Five Layers

The architecture consists of five layers, from shared public truth down to individual execution:

| Layer | Name | What It Is | Detailed In |
|-------|------|------------|-------------|
| **1** | Synome | Public constitution — Atlas, axioms, shared knowledge | `synome-layers.md` |
| **2** | Synomic Agents | Institutional shells — Primes, Halos, Generator | `atlas-synome-separation.md` |
| **3** | Teleonomes | Autonomous AI entities with directives and missions | `synome-layers.md` |
| **4** | Embodiments | Physical infrastructure hosting teleonome slices | `synome-layers.md` |
| **5** | Embodied Agents | Execution threads operating beacons | `synome-layers.md` |

**Key insight:** Layers 1-2 are public and shared. Layers 3-5 are private to each teleonome.

See `synome-layers.md` for full layer specifications.

---

## The Dual Architecture

The Synome has two fundamentally different types of structure:

### Deontic Skeleton (Hard)

The **deontic skeleton** is sparse, load-bearing, and deterministic:
- Axioms that must be followed
- Governance decisions
- Authority hierarchies
- Enforcement mechanisms

Once a rule is set, it holds unconditionally.

### Probabilistic Mesh (Soft)

The **probabilistic mesh** is dense, informing, and adaptive:
- Knowledge with truth values (strength, confidence)
- Evidence that flows back from the world
- Patterns that ossify over time
- RSI (recursive self-improvement)

The mesh informs decisions; the skeleton executes them.

**The relationship:** Governance sits at the interface — consuming probabilistic evidence, producing deontic commitments. See `probabilistic-mesh.md` for the full truth value system.

---

## Knowledge Hierarchy

Knowledge accumulates in artifacts at each level:

| Artifact | Layers | Shared Across |
|----------|--------|---------------|
| **synart** | 1 + 2 | All aligned entities |
| **telart** | 1 + 2 + 3 | All embodiments of a teleonome |
| **embart** | 1 + 2 + 3 + 4 | Single embodiment only |

Higher-level knowledge (synart) is more authoritative but updates slowly. Lower-level knowledge (embart) is local and updates rapidly.

**Authority hierarchy:** synart > telart > embart. When in doubt, consult higher authority.

See `synome-layers.md` for artifact specifications and `retrieval-policy.md` for query invariants.

---

## Truth Values and Ossification

All probabilistic knowledge has truth values:

- **Strength** — How positive or negative is the evidence?
- **Confidence** — How much evidence has accumulated?

These derive from positive and negative weights on observations.

**Ossification:** Patterns with high confidence become resistant to change. This creates natural stability — established patterns aren't overwritten by noise, but genuinely new evidence can still shift them over time.

| Ossification Level | What Can Change It |
|--------------------|-------------------|
| Speculative | Normal evidence flow |
| Established | Sustained contrary evidence |
| Proven | Overwhelming contrary evidence |
| Axiomatic | Governance only |

See `probabilistic-mesh.md` for the full model and `security-and-resources.md` for how ossification prevents self-corruption.

---

## Beacons: The Action Interface

A **beacon** is a synome-registered, enforceable action aperture through which an embodied agent may affect the external world.

Beacons are classified by two axes:

| | Low Authority | High Authority |
|---|---|---|
| **Low Power** | LPLA (simple trading, data) | LPHA (keepers, clerks) |
| **High Power** | HPLA (advanced trading) | HPHA (sentinels, governance) |

**Key properties:**
- Registered in the Synome
- Bound to an authority envelope
- Observable and revocable
- All external action must be beaconed

See `beacon-framework.md` for the full taxonomy, lifecycle, and naming conventions.

---

## Synomic Agents: Institutional Shells

Synomic Agents (Primes, Halos, Generator) are durable, ledger-native entities that can:
- Own assets
- Execute actions
- Make binding commitments

Unlike teleonomes (whose internal logic is private and mutable), Synomic Agents are constrained by publicly visible rules. This makes them **credible commitment devices** — counterparties can trust their behavior without trusting any teleonome.

Teleonomes operate Synomic Agents through beacons, especially high-authority sentinels.

See `atlas-synome-separation.md` for how Synomic Agents enable trustless cooperation.

---

## Dreamers and Actuators

Embodiments come in two fundamental types:

| Type | Environment | Purpose | Runs On |
|------|-------------|---------|---------|
| **Actuator** | Real world | Execute, generate value, survive | Light-to-medium embodiments |
| **Dreamer** | Simulation | Explore, evolve strategies, RSI | Heavy embodiments |

**The relationship:** Dreamers explore the strategy space safely. Successful patterns are extracted and propagated to actuators via telart. Actuators execute in reality, generating evidence that flows back to improve future dreaming.

See `actuator-perspective.md` and `dreamer-perspective.md` for first-person views.

---

## Security: Preventing Self-Corruption

The primary security threat is **not external attackers** — it's **self-corruption through overeager updates**.

The dangerous failure mode:
```
System "learns" something wrong
        ↓
Bad pattern enters knowledge base
        ↓
Bad pattern influences future decisions
        ↓
More bad patterns generated
        ↓
Drift from alignment
```

**How the architecture prevents this:**
- Ossification makes established patterns resistant to noise
- High-authority knowledge (synart) is hardest to change
- Governance review for changes to axioms
- Append-only with rollback capability
- Rate limits on all execution authority

**Principle:** Thoughtful constraint beats reckless capability. An overeager improvement that corrupts core logic does infinitely more damage than fast self-improvement helps.

See `security-and-resources.md` for the full security model.

---

## The Human Interface

Humans interact with the system through directives at each level:

| Level | Directive | Who Controls | Translated By |
|-------|-----------|--------------|---------------|
| Layer 1 | Atlas | Sky Voters | Language Intent |
| Layer 2 | Agent Directives | Token holders | Language Intent |
| Layer 3 | Teleonome Directives | Bound humans | Language Intent |

All directives pass through **Language Intent** — a single trusted translation layer grounded by the Synomic Library. This ensures honest interpretation and resistance to prompt engineering.

See `synome-layers.md` for the human interface pattern.

---

## Implementation Pathways

The full architecture is built incrementally:

| Pathway | Focus | Detailed In |
|---------|-------|-------------|
| **Short-term actuators** | Teleonome-less beacons (Phase 1) | `short-term-actuators.md` |
| **Short-term dreamers** | Game-playing agents | `short-term-experiments.md` |

Both pathways preserve the essential invariants while simplifying for practical deployment. They evolve toward full teleonome-based operation over time.

---

## Document Map

| Document | What It Covers |
|----------|----------------|
| `synome-layers.md` | 5-layer architecture, components, artifact hierarchy, structural invariants |
| `atlas-synome-separation.md` | Atlas vs Synome, Synomic Agent autonomy, verification model |
| `beacon-framework.md` | Beacon taxonomy, lifecycle, naming, sentinel formations |
| `probabilistic-mesh.md` | Truth values, ossification, evidence flow, RSI |
| `retrieval-policy.md` | Query invariants for the probabilistic mesh |
| `security-and-resources.md` | Cancer-logic, resource discipline, the update problem |
| `actuator-perspective.md` | First-person actuator embodiment view |
| `dreamer-perspective.md` | First-person dreamer embodiment view |
| `short-term-actuators.md` | Phase 1 beacon implementation pathway |
| `short-term-experiments.md` | Dreamer experiment pathway |

---

## One-Line Summary

> *The Synome architecture separates private cognition from public action: teleonomes accumulate knowledge and pursue goals privately, but power enters the world only through regulated beacons, governed by the Synome, with security achieved through ossification rather than restriction.*
