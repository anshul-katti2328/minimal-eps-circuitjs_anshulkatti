Key queries & actions I asked the assistant during the project (chronological / paraphrased):

“Where do I add the OBC resistor (27 Ω) and why 27 Ω?”

“Add the OBC load (always ON) in Falstad — how to place and value it.”

“Where do I put the relay and which pins connect to what?” (multiple pin-by-pin wiring checks)

“My relay coil draws huge current — why and how to fix?”

“Why does PWL not work in a simple voltage/current source?” (explain dependent source requirement)

“How do I make a timed sun/eclipse profile (60 min on / 30 min off) using PWL?”

“How to replace the solar relay with a timed source (VCCS) — exact PWL string?”

“How to wire the VCCS pins (control +/−, output +/−) to the bus and ground.”

“How to probe Vbus and per-branch currents with the scope (where exactly to place probes).”

“Why doesn’t the bus drop to 0 V during eclipse and how do we force 0 V if needed?”

“Simulation options: what time step and time scale to use for fast test vs real orbit.”

Use these exact prompts in the order above if you want to reproduce the same debugging path.
AI_USAGE.md — what I corrected the assistant on & external materials used

What I corrected / insisted on (important corrections I made to the assistant):

PWL placement: I insisted that PWL only works in dependent sources (VCCS/VCVS) in CircuitJS; placing a PWL in a simple voltage/current source is ignored.

Relay coil resistance: The assistant originally left relay coil R small; I corrected to raise coil resistance (0.2 → 200 Ω) to avoid huge coil currents.

Timescale choice: I pushed for a fast test timescale (60 s on / 30 s off) to debug quickly, and clarified the difference between test scale and the real 60 min / 30 min orbit.

Which element to replace: I clarified that the solar relay (left relay) should be replaced by the VCCS PWL, while retaining relays for load switching (payload / TT&C).

Scope placement: I corrected probe placement advice — probe BUS node after the 0.3 Ω for Vbus and right-click components for currents (don’t rely on short-wire popups).

External references / PDFs I used while building the model:

FINALVERSION (1).pdf (uploaded) — file:///C:/Users/Anshul/Downloads/FINALVERSION%20(1).pdf

KiboCUBE_Academy_2021_OPL08.pdf (uploaded) — https://www.unoosa.org/documents/pdf/psa/access2space4all/KiboCUBE/AcademySeason2/On-demand_Pre-recorded_Lectures/KiboCUBE_Academy_2021_OPL08.pdf
