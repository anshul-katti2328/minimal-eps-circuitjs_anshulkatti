<img width="752" height="578" alt="image" src="https://github.com/user-attachments/assets/8e2012cd-5078-42b2-8dbe-d908c3f3b853" />
<img width="1509" height="175" alt="image" src="https://github.com/user-attachments/assets/fbfad22e-5ed9-4591-97f3-4d2aa41b649e" />
1. Outputs (waveforms & screenshots)

These are things you must extract from CircuitJS:

Battery voltage (Vbus) → place a scope probe on the node after the 0.3 Ω resistor and export the scope plot (File → Export → As Image).

Battery current (Ibatt) → right-click the 0.1 Ω resistor (battery internal R) → “View Current” and export the scope waveform.

Solar current (Isolar) → right-click the VCCS (your PWL source) → “View Current” and export.

Load currents  → check OBC (27 Ω), Payload (10 Ω), TT&C (5 Ω) branches by probing those resistors.



2)Observations:
The green line is the battery source (fixed at 7.4 V, as expected for two Li-ion cells in series).

The yellow line is the bus voltage measured after the series resistance (0.3 Ω + 0.1 Ω internal).

The bus voltage is slightly lower than 7.4 V (~2.5–3 V depending on load conditions), showing the voltage droop caused by current flowing through the resistive losses.

The waveform remains nearly flat rather than toggling to 0 V, because the battery always maintains the bus voltage — even during eclipse, when the solar PWL source drops to 0. This matches the real CubeSat case: the bus is never “0 V,” it is battery-clamped, and only the battery current changes sign (charging vs discharging).


30Element to function mapping:
| CircuitJS Element                  | Value / Params           | Real EPS Function                        |
| ---------------------------------- | ------------------------ | ---------------------------------------- |
| Voltage source + 0.1 Ω resistor    | 7.4 V, 0.1 Ω             | Battery + internal resistance            |
| Series resistor                    | 0.3 Ω                    | EPS loss / wiring / MPPT efficiency      |
| VCCS with PWL                      | 0.81 A sun / 0 A eclipse | Solar array + MPPT profile (sun/eclipse) |
| Resistor (27 Ω)                    | Always ON                | OBC + housekeeping load                  |
| Resistor (10 Ω) + relay            | Switched                 | Payload load                             |
| Resistor (5 Ω) + relay, 50 mHz PWM | Bursts                   | TT\&C load (short bursts)                |
| Scope probes                       | Vbus, Ibatt, Isolar      | Measurement outputs for analysis         |
