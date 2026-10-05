# Experimental Analogue Cybernetic Platform (ES-Analog)

> *"Behaviour is not programmed. It is the geometry of the system returning to equilibrium."*

An experimental hardware platform that revisits Grey Walter's analogue cybernetics using thermionic valves (vacuum tubes), an unstabilised power bus and passive RC memory cascades. The goal is to investigate whether long-term adaptive behaviour can arise from circuit physics alone, without a digital processor in the control loop.

**Status (October 2026):** concept and theory are written; Phase 1 hardware is in preparation. **No experimental results yet.** Nothing in this repository should be read as a validated finding.

[Русская версия](README.ru.md)

Copyright © 2026 Unsinkable Sam
Source Location: https://github.com/Danek723/experimental-analogue-cybernetic-platform
SPDX-License-Identifier: CERN-OHL-S-2.0
Documentation (text): CC BY-SA 4.0

---

## Core idea

In most robots, power supply is a service subsystem. Here, the power bus and the physical topology of the circuit take part in the computation.

- **Unstabilised bus.** A source with high internal resistance sags under motor load or collision. The sag shifts valve operating points, RC charge rates and comparator thresholds. Heaters are powered from a separate stabilised line.
- **Three-tier passive memory** (time constant τ = RC), working like a slow, global "hormonal background" rather than addressed storage:
  - C1 (~47 µF, τ ≈ 5 s): fast balance.
  - C2 (~470 µF, τ ≈ 2 min): intermediate accumulation.
  - C3 (~2200 µF, τ ≈ 15 min): slow integrator of long-term load.
  The names "emotion / habit / fatigue" used in the paper are metaphors, not claims.
- **Derivative sensitivity.** Sharp events (a collision) and slow chronic load are distinguished by the rate of change dVC3/dt, not by a fixed threshold.
- **Terracotta hull** (planned): a thermal slow variable. Whether it really influences the circuit is a measurable question, not an assumption.

## System blueprint

Resource inflow (light) ──┐
├──> [ UNSTABILISED BUS ] ──> valve operating points
Entropy (obstacles/load) ─┘            └──────────────> passive memory cascade (C1–C3)

### Three-module architecture

1. **Optoelectronic forebrain.** Subminiature 6N17B-V valves and photoresistors, kept away from motor switching noise.
2. **Unstabilised mainframe.** Power delivery and the RC memory cascades.
3. **Actuator tail.** Valve buffers driving IRFZ44N MOSFET gates for smooth differential motor control (no relays).

## Bill of materials (draft)

**Robot platform**
- Valves: 2–6 pcs, 6N2P / 6N2P-EV or 6N17B-V.
- Capacitors: 47 µF (C1), 470 µF (C2), 2200 µF (C3); other values via jumpers (see configurations A/B/C in the paper).
- Multi-turn potentiometers: 100 kΩ, 500 kΩ, 1 MΩ.
- N-channel MOSFETs: IRFZ44N / IRF540N (4 pcs).

**"V-Trap" docking module**
- 12 V (2–3 A) switch-mode power supply, 1–3 W warm LED.
- Resettable PTC fuses (1.5–2 A), Schottky diodes (1N5822), brass/copper contact strips.

## Roadmap

- [ ] **Phase 1: Two-valve tropism.** Differential optical bridge driving the motors through valves and MOSFETs. Verify triode curves and the effect of bus sag. *(in preparation; see [technical brief](docs/TZ_Phase1_master.md))*
- [ ] **Phase 2: Four-valve integration.** Add C1 and C2 memory layers; observe trajectory drift with load history.
- [ ] **Phase 3: Six-valve system.** Add C3 homeostasis and the mirror differential output.

## Planned experiments

1. **Bench stage, no motors:** triode characteristics, light-to-gate transfer function, noise on the grids.
2. **Bus-sag test:** how a stalled motor changes anode voltage and valve currents.
3. **Ablation (key test):** the same robot with C2/C3 replaced by fixed resistors versus the full robot. If trajectories differ depending on load history, the memory layers do real work.
4. **Thermal log:** hull and valve temperatures, to test whether heat acts as a slow variable.
5. **Passive logging only:** a microcontroller may *record* voltages and temperatures but never controls anything.

## Open design questions

- **Anode voltage.** The BOM lists a 12 V supply, but the valves normally need higher anode voltage. Options: run at low voltage in a deliberately starved regime, or add a boost converter. Not decided.
- **How C1–C3 are charged** (which elements, through what resistors/diodes) needs a full schematic.
- **Leakage term.** The energy-balance model dS/dt = α·L − β·M − γ·B has no decay term and will saturate; a −S/τ term is probably needed.
- **Grid current** of the valves is small but not zero; high-impedance paths will drift.
- **Power budget.** Six heaters draw continuous power; battery and thermal budget must be calculated early.

## Related work

Ashby's homeostat, Grey Walter's tortoises, Braitenberg's vehicles, Tilden's BEAM robotics, physical reservoir computing, and Man & Damasio's work on homeostasis in "feeling machines". The platform is closest to embodied analogue control and homeostatic machines; it does not include a trained readout layer, so it is not reservoir computing in the strict sense.

## Documents

- Article: `docs/Experimental_Analogue_Cybernetic_Platform.pdf` *(add to repository)*
- Phase 1 technical brief: [`docs/TZ_Phase1_master.md`](docs/TZ_Phase1_master.md) *(add to repository)*

## Authorship and tools

The thesis and design are by the author. A large language model was used as a drafting aid to structure the technical text.

## Contributing

Issues are welcome, especially from people with valve electronics experience (circuit review, build advice, measurement ideas). Please keep claims tied to measurements.
