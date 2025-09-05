Minimal CubeSat EPS Circuit (CircuitJS1)
📌 Purpose

This project models a minimal Electrical Power Subsystem (EPS) for a CubeSat using the open-source browser tool CircuitJS1
.
It demonstrates how the EPS handles charge/discharge cycles during repeated sun (60 min) and eclipse (30 min) phases in orbit.

🛠️ Approach

Solar input modeled as a piecewise linear (PWL) current source: ~6 W during sunlight, 0 W during eclipse.

Battery represented as an ideal 7.4 V source with a small internal resistance to simulate voltage droop.

Loads implemented as timed resistors/switches:

OBC (On-Board Computer) → continuous load.

TT&C (Telemetry, Tracking & Command) → burst mode load.

Payload → active only in sunlight.

EPS losses represented as a simple series resistor (conversion + wiring losses).

Key telemetry observed: battery voltage (Vbatt), battery current (Ibatt), and a simple SOC proxy (based on current flow).

📋 Assumptions

Orbit period fixed at 90 minutes (60 min sunlight, 30 min eclipse).

No detailed DC/DC converter modeling; losses lumped into series resistance.

SOC is a qualitative proxy (not an accurate Li-ion chemistry model).

All subsystems powered from the same EPS bus.

⚡ Tools Used

CircuitJS1 → Circuit modeling and simulation.

Markdown & GitHub → Documentation and repository structure.

(If AI or external resources were used, details are in AI_USAGE.md.)📸 Figures

EPS circuit diagram (from CircuitJS1).

Battery V/I waveforms across one orbit.

SOC proxy trend.

(All figures included in /figures.)

📚 Resources

Falstad CircuitJS1

Basic CubeSat EPS design references.

AI tools + queries (documented in AI_USAGE.md).

✨ This repository demonstrates a simplified CubeSat EPS workflow and provides reproducible simulation steps for learning and evaluation.
