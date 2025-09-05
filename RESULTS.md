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
