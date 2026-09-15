# AXM Hardware Recomposition — Research Seed v0.1

**Created:** 2026-09-15  
**Status:** Dormant future research seed  
**Purpose:** Preserve the idea and activation boundary so it does not depend on human or chat memory.

---

## 1. Origin

This idea emerged from the same capability-first line of thinking that produced AXM Device Capability Arbitrage.

The broader lineage began with examples of consumer/e-waste hardware being used for purposes unrelated to the label on the box. A social post about repurposed disposable/consumer electronics helped trigger deeper thinking about hidden compute in e-waste. Later examples — including custom software running on devices such as cameras — reinforced the same principle:

> **Human product categories do not define the machine capabilities inside the product.**

Device Capability Arbitrage currently studies the intact-device side of that idea.

Hardware Recomposition preserves the next physical step:

> **If a cheap product contains useful compute, memory, storage, networking, sensors, actuators, power regulation, or other capability blocks, could those blocks eventually be physically reconfigured or combined with blocks from other donor products around a new goal?**

The answer is not assumed to be yes in every case. This repository exists to make that a future evidence question rather than a forgotten idea.

---

## 2. Central hypothesis

> **A commercial product is one arrangement of hardware capabilities, not necessarily the only useful arrangement.**

A device might contain:

```text
compute board
RAM
flash / eMMC / removable storage
network radios
Ethernet PHY / switch
power regulation
battery + BMS
camera / microphone / lidar / environmental sensors
motors / relays / displays / speakers / LEDs
USB / UART / GPIO / I2C / SPI / PCIe or other interfaces
thermal hardware
enclosure / mechanical structure
```

For the original product, those parts are arranged around the manufacturer's intended use.

For a different machine goal, only some of those parts may matter.

The future research question is therefore not only:

> "Can we reuse this product?"

but also:

> **"Can we preserve the useful capability blocks, remove or replace irrelevant constraints, and form a safer/cheaper/better hardware state?"**

---

## 3. Relationship to AXM Device Capability Arbitrage

Sibling repo:

`mike-axiom-mir/axm-device-capability-arbitrage`

### Device Capability Arbitrage owns

- intact-device capability discovery;
- software/firmware execution surfaces;
- local/offline capability;
- recovery and provisioning;
- market/economic observations;
- capability contracts;
- choosing the cheapest useful intact device or device composition;
- firmware replacement when the physical product remains essentially intact.

### Hardware Recomposition will eventually own

- physical decomposition;
- donor subsystem mapping;
- board/module extraction;
- connector and pinout evidence;
- voltage/current/power-rail mapping;
- thermal dependencies;
- storage module replacement/relocation;
- cooling changes;
- antenna/interface relocation;
- physical rewiring;
- soldering/rework evidence;
- enclosure removal/replacement;
- multi-donor physical compositions;
- dependency graphs for physically separated subsystems;
- physical test/recovery receipts;
- resulting recomposed hardware capability records.

### Simple routing rule

```text
software / firmware / provisioning / role change
while hardware stays physically intact
    -> Device Capability Arbitrage

physical board/module/power/cooling/interface transformation
or multiple donor devices combined into one hardware state
    -> Hardware Recomposition
```

---

## 4. Why a separate repository is justified

The evidence model changes once hardware is physically altered.

An intact-device record can often rely on:

- model/revision;
- firmware;
- execution environment;
- network/runtime tests;
- power measurements;
- recovery procedures.

A recomposed device may additionally require:

- exact PCB revision;
- board photographs;
- connector identification;
- pinout provenance;
- voltage rail measurements;
- current draw and startup transients;
- dependency on removed daughterboards/peripherals;
- boot behavior after physical changes;
- thermal behavior outside the original enclosure;
- grounding/shielding/antenna effects;
- mechanical mounting;
- battery/BMS behavior;
- isolation requirements;
- rework method;
- reversibility/destructive state;
- failure evidence;
- physical safety classification.

That is a different enough truth boundary to deserve a sibling repo rather than overloading the intact-device census.

---

## 5. Example future patterns

These are **conceptual examples only**, not current capability claims.

### Example A — compute board reuse

A cheap consumer product contains:

```text
ARM SoC
RAM
flash
Wi-Fi
Ethernet
12 V input stage
```

The original human-facing enclosure/display/buttons are irrelevant to the target goal.

Future question:

> Can the compute/network board run safely and reliably as a headless node outside the original product configuration?

### Example B — donor composition

```text
Product A
  -> useful compute + networking

Product B
  -> useful sensor

Product C
  -> useful power subsystem / enclosure
```

Future question:

> Can those capability blocks form one grounded system for less total useful cost than purpose-built hardware?

### Example C — remove expensive irrelevance

A product is cheap on the used market because its main consumer function is obsolete or damaged, while its internal compute board remains useful.

Future question:

> Does harvesting the surviving capability reduce cost without creating more recovery/safety/maintenance burden than simply buying a normal board?

---

## 6. Hardware recompilation / recomposition model

Possible long-term flow:

```text
GOAL
  ↓
MINIMUM CAPABILITY CONTRACT
  ↓
INTACT DEVICE CANDIDATES
  ↓
DONOR PRODUCT CANDIDATES
  ↓
SUBSYSTEM INVENTORY
  ↓
DEPENDENCY GRAPH
  ↓
ELECTRICAL / THERMAL / MECHANICAL REQUIREMENTS
  ↓
SAFE COMPOSITION PLAN
  ↓
PHYSICAL BUILD
  ↓
MEASURED TEST
  ↓
RECOVERY / FAILURE TEST
  ↓
NEW VERIFIED HARDWARE STATE
  ↓
COST + POWER + FRICTION COMPARISON
```

This resembles "hardware compilation" only as a conceptual direction. The repo must not claim automatic hardware design until real evidence supports such a system.

---

## 7. Future donor capability record

A future donor/subsystem record might eventually need fields like:

```yaml
donor:
  manufacturer: unknown
  product_model: unknown
  product_revision: unknown
  pcb_revision: unknown

subsystem:
  type: compute_board
  original_role: unknown
  extraction_state: unknown

interfaces:
  power:
    input_voltage: unknown
    current_idle: unknown
    current_peak: unknown
    startup_transient: unknown
  data:
    usb: unknown
    uart: unknown
    gpio: unknown
    i2c: unknown
    spi: unknown
    ethernet: unknown

physical_dependencies:
  required_daughterboards: []
  required_peripherals: []
  enclosure_dependency: unknown
  antenna_dependency: unknown
  thermal_dependency: unknown

recomposition:
  tested_outside_original_product: false
  irreversible_steps: []
  rework_required: unknown

safety:
  mains_present: unknown
  lithium_battery_present: unknown
  high_current: unknown
  moving_parts: unknown
  heater_present: unknown
  safety_critical_parent_system: unknown

verification:
  locally_measured: false
  evidence: []
```

This is **not a frozen schema**. It is only a memory anchor for the kinds of evidence that physical work may require.

---

## 8. Activation conditions

Do not turn this repo into architecture churn before hands-on capability exists.

Deeper work becomes justified when AXM has begun collecting real hardware evidence such as:

- owned donor devices available for destructive/non-destructive study;
- repeatable safe disassembly;
- exact model/PCB identification;
- basic multimeter competence and measured voltage/current evidence;
- safe low-voltage power testing;
- connector/interface identification;
- UART/USB/GPIO experimentation where appropriate;
- thermal observation/measurement;
- boot/recovery testing;
- at least one successful physical modification or board reuse experiment;
- preserved photographs, measurements, commands/configuration, failures, and recovery notes.

Not every item must be mastered before any experiment, but the work must stay inside demonstrated competence and safe equipment boundaries.

### Initial activation milestone

A strong first real milestone would be:

> **Take one low-voltage, user-owned, non-safety-critical donor device; identify one useful subsystem; prove what it requires to function outside or differently from its original arrangement; preserve measurements and recovery evidence; then compare whether the modification was actually worthwhile.**

---

## 9. What should happen before activation

The sibling Device Capability Arbitrage project may preserve **future recomposition leads** when ordinary device research reveals them, for example:

- accessible PCB/module layout;
- obvious removable compute boards;
- exposed UART/GPIO;
- removable flash/storage;
- modular radio cards;
- interesting sensor boards;
- unusual low-voltage power arrangements;
- known teardown documentation;
- replacement/recovery images;
- high-value donor parts.

Those observations are leads only.

They do not become claims that AXM can safely extract or recombine the hardware.

---

## 10. Total useful cost still applies

Physical recomposition can make "cheap" deceptive.

A future cost model must consider at least:

```text
purchase cost of donor devices
+ shipping
+ adapters / regulators / connectors
+ replacement storage
+ enclosure / mounting
+ cooling
+ tools
+ consumables
+ rework time
+ measurement time
+ failure probability
+ replacement donor cost
+ power consumption
+ maintenance
+ recovery burden
+ opportunity cost
```

A EUR 5 donor board is not a bargain if safe extraction requires expensive tools, hours of reverse engineering, fragile soldering, or repeated replacement hardware.

The comparison should always include the option:

> **Do not modify it; buy/use a normal purpose-suitable device instead.**

---

## 11. Evidence discipline

Physical claims require physical evidence when the claim depends on physical modification.

Potential evidence classes:

```text
DOCUMENTED_TEARDOWN
DOCUMENTED_SCHEMATIC_OR_PINOUT
COMMUNITY_REPRODUCED
LOCALLY_OBSERVED
LOCALLY_MEASURED
LOCALLY_RECOMPOSED
REPRODUCIBLE
CONTRADICTED
```

Do not silently promote:

```text
PCB photo
  -> known pinout

community guess
  -> measured voltage

same connector shape
  -> electrical compatibility

board powers on
  -> stable subsystem

boot once
  -> reliable deployment

runs outside enclosure
  -> thermally safe

root access
  -> actuator safety

cheap donor price
  -> cheap final system
```

Unknown stays unknown.

---

## 12. Safety boundary

This repo must be more conservative physically than the software-only research layer because mistakes can damage hardware, start fires, cause shocks, or create mechanical hazards.

### High-risk areas requiring appropriate expertise/equipment before hands-on work

- mains voltage;
- lithium-ion / lithium-polymer cells and battery management systems;
- high-current power rails;
- exposed power supplies;
- heaters;
- motors / moving machinery;
- lasers;
- high-power RF;
- medical hardware;
- security/alarm systems;
- automotive safety-critical systems;
- industrial machinery capable of injury.

Research may document these devices without physically experimenting beyond safe competence.

### Default early experimental target

Prefer:

- low voltage;
- externally powered;
- user-owned;
- inexpensive/replaceable;
- non-safety-critical;
- no hazardous battery work;
- no mains-side modification;
- known recovery path;
- easy visual inspection;
- reversible changes where possible.

---

## 13. Relationship to e-waste

This direction is not an excuse to accumulate junk.

The useful e-waste question is:

> **Can a discarded or underpriced object contribute a capability that is actually needed?**

A donor should have a reason to exist in the system.

Future success is not measured by how many products can be disassembled. It is measured by whether a recomposed capability is:

- useful;
- cheaper or otherwise materially better;
- measurable;
- recoverable;
- maintainable;
- safe;
- understandable;
- reproducible.

---

## 14. Root merge gate

### Truth

- No fake electrical knowledge.
- No guessed pinouts presented as fact.
- No guessed voltage/current limits.
- No "works" claim from appearance alone.
- Preserve failed experiments and damaged states.
- Exact model/PCB/revision matters.

### Agency / non-domination

- Work only on owned/authorized hardware.
- No hidden modification of another person's device.
- Preserve understandable control and disable/recovery paths.
- Physical automation does not override surrounding human authority.

### Continuity

- Preserve source donor identity.
- Preserve photographs/diagrams/measurements.
- Preserve wiring/pinout provenance.
- Record irreversible steps.
- Preserve original firmware/images when relevant.
- Preserve rebuild and recovery procedures.
- Do not let one chat/operator become the only place the hardware state is understood.

### Wisdom before speed

- Count tools, labor, risk, power and fragility.
- Prefer reversible tests before destructive rework.
- Use safe low-voltage targets first.
- Do not physically cross a risk boundary just because the capability is interesting.
- Compare against the intact-device alternative before celebrating a hack.

---

## 15. What this repo should not become

Do not let it drift into:

- random teardown collecting;
- e-waste hoarding;
- unsafe electronics experiments;
- a generic repair wiki;
- guessed reverse engineering;
- a soldering challenge collection;
- physical modifications with no capability goal;
- automatic claims that custom hardware is cheaper than commercial boards;
- hardware architecture built entirely from imagination before measurement.

The differentiator should remain:

> **goal → required capability → donor evidence → physical dependencies → safe recomposition → measured result → total useful cost**

---

## 16. Dormant-state instruction

Until real hands-on hardware evidence exists:

- preserve this seed;
- accept useful leads from Device Capability Arbitrage;
- do not manufacture progress;
- do not create recurring growth work solely to fill the repo;
- do not freeze a detailed physical schema prematurely;
- do not claim AXM has hardware-recomposition capability yet.

A quiet repo that preserves the idea truthfully is preferable to a large speculative repo.

---

## 17. One-line anchor

> **Do not treat a product as the final form of its hardware. Once we can measure and modify hardware safely, investigate whether useful capability blocks can be recomposed around goals at lower total useful cost — and prove every physical claim with evidence.**
