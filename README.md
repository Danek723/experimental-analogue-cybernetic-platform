

# Experimental Analogue Cybernetic Platform (ES-Analog)

> *"Behaviour is not programmed. It is the geometry of the system returning to equilibrium."*

An experimental hardware platform reviving Grey Walter's analog cybernetics architecture using thermionic valves (vacuum tubes), un-stabilized power buses, and passive RC memory cascades—investigating emergent behavior without a digital processor.

## 🏛 Architectural Philosophy
Unlike modern digital robotics, where energy is a mere service subsystem, this platform treats the **power supply and physical circuit topology as direct participants in computation**. 
- **Unstablised Entropy Bus:** High internal resistance causes voltage sags under motor load/collisions, instantly altering valve operating points and RC charge rates.
- **Three-Tier Passive Memory Cascade ($\tau = RC$):** Distributed temporal memory spanning instant reflex ($C_1$, ~5s), habit ($C_2$, ~2m), and structural homeostasis/fatigue ($C_3$, ~15m).
- **Embodied Physics:** No microcontrollers, no code, no digital clock cycles. Computation emerges entirely from thermionic non-linearities and circuit geometry.

---

## 🗺 System Blueprint

Resource Inflow (Light) ──┐
├──> [ UNSTABILISED ENTROPY BUS ] ──> Valve Operating Points
Entropy (Obstacles/Load) ──┘                                   └──> Passive Memory Cascade (C1-C3)

### Decentralised Three-Module Architecture
1. **Optoelectronic Forebrain:** Chassis front housing subminiature 6N17B-V pencil valves and photoresistors (isolated from motor switching noise).
2. **Unstablised Mainframe:** Neural Trunk core anchoring BMS, power delivery, and un-isolated RC memory cascades.
3. **Actuator Tail:** Low-impedance valve buffers modulating IRFZ44N MOSFET gates for smooth differential drive.

---

## 📋 Bill of Materials (BOM)

### Robot Platform Module
- **Valves:** 2–6 pcs of 6N2P / 6N2P-EV or subminiature 6N17B-V triodes (with Noval 9-pin bases or direct solder).
- **Memory Capacitors:** 
  - $C_1$: ~47 µF (Instant balance / "Emotion")
  - $C_2$: ~470 µF ("Habit")
  - $C_3$: ~2200 µF ("Structural Homeostasis" / "Fatigue")
- **Control Elements:** Multi-turn potentiometers (100kΩ, 500kΩ, 1MΩ).
- **Output Stage:** 4 pcs IRFZ44N / IRF540N N-Channel MOSFETs.

### "V-Trap" Docking Module
- 12V (2A–3A) Switch-Mode Power Supply
- High-Power 1–3W LED (Warm White / Yellow)
- Resettable PTC Fuses (1.5A–2A) & Schottky Diodes (1N5822 3A)
- Brass / Copper contact strips (0.5–0.8 mm)

---

## 🚀 Evolutionary Roadmap
- [x] **Phase 1:** Two-Valve Tropism (MVP verification of triode non-linear curves).
- [ ] **Phase 2:** Four-Valve Integration (Adding $C_1$ and $C_2$ memory layers for historical trajectory drift).
- [ ] **Phase 3:** Six-Valve Totality (Full matrix with $C_3$ homeostasis and mirror differential output).

---

Author: Unsinkable Sam
