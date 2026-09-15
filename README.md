# AXM Hardware Recomposition

**Status: DORMANT RESEARCH SEED — not an active hardware-building program yet.**

> **Products are temporary arrangements of capabilities.**

AXM Hardware Recomposition preserves a future research direction: once AXM has enough real hands-on hardware knowledge, investigate whether low-cost products can be **physically decomposed, reconfigured, and recombined around capability goals** instead of being treated as fixed products forever.

This repository exists now for continuity, not because the hardware work is ready.

The starting idea is preserved in [`RESEARCH_SEED_v0.1.md`](RESEARCH_SEED_v0.1.md).

## Relationship to Device Capability Arbitrage

Sibling repository:

`mike-axiom-mir/axm-device-capability-arbitrage`

That project asks:

> **What can this real device do, and is the intact device a good capability-for-cost match?**

Hardware Recomposition asks a later, more physical question:

> **What useful capability blocks exist inside one or more devices, what dependencies must survive, and can they be safely recomposed into a better hardware state for a specific goal?**

### Boundary

Keep work in **Device Capability Arbitrage** when the product remains physically intact and changes are primarily software, firmware, configuration, provisioning, or role selection.

Move into **Hardware Recomposition** when work involves physical transformation such as:

- opening devices;
- extracting or relocating boards/modules;
- changing power delivery;
- changing cooling;
- changing physical storage modules;
- exposing or rewiring connectors;
- soldering/rework;
- rehousing hardware;
- harvesting sensors/actuators/compute boards;
- composing subsystems from multiple donor products.

## Current rule

**Do not pretend we already know how to do this safely.**

For now this repo should preserve the hypothesis, vocabulary, boundaries, activation conditions, and future evidence requirements. Real implementation should begin only after hands-on hardware work provides grounded evidence.

## Future conceptual flow

```text
GOAL
  ↓
CAPABILITY CONTRACT
  ↓
INTACT DEVICE OPTIONS
  ↓
DONOR PRODUCTS / SUBSYSTEMS
  ↓
DEPENDENCY + POWER + THERMAL + INTERFACE MAP
  ↓
SAFE PHYSICAL RECOMPOSITION
  ↓
MEASURED TEST
  ↓
NEW VERIFIED CAPABILITY HOST
  ↓
FEEDBACK INTO CAPABILITY ARBITRAGE
```

## Root gate

The four AXM roots remain the internal merge gate:

- **Truth** — measurements and physical evidence before claims.
- **Agency / non-domination** — owned/authorized hardware, visible control, no hidden modification of others' devices.
- **Continuity** — preserve donor identity, diagrams, measurements, recovery state, photos, test receipts, and rollback/rebuild knowledge.
- **Wisdom before speed** — cheap parts are not useful if the result is unsafe, fragile, irrecoverable, thermally unsound, or costs more in labor/tools than a better intact device.

## Important safety boundary

Mains voltage, lithium batteries, high-current systems, heaters, motors, RF power stages, medical equipment, vehicle safety systems, and other physically hazardous hardware require appropriate expertise, isolation, tools, and evidence. Capability curiosity is not permission to experiment unsafely.

## Activation state

**Dormant until hands-on hardware evidence exists.**

The repo should not grow architecture for its own sake. Activate deeper work when real devices, measurements, disassembly evidence, and safe test capability exist.
