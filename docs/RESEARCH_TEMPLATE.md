# Research Paper Title

_Author: Your Name — YYYY-MM-DD_

## Abstract

Brief 2–4 sentence summary of the problem, what you did, and what you found.  
_Example: This paper explores RF methods for rocket telemetry, comparing LoRa, XBee, and custom FSK systems._

---

## Background

Introduce the problem and why it matters.  
_Example: Reliable telemetry is critical for rocket recovery. Current options vary in range, bandwidth, and complexity._

---

## Methods

What approaches did you take? How did you research or test?

- Reviewed manufacturer datasheets
- Built test setup for range evaluation
- Surveyed antenna options

---

## Results

Summarize key data, findings, or outcomes. Use tables or bullet points if helpful.  
_Example:_

- LoRa achieved ~12 km LOS range
- XBee failed beyond 3 km
- Yagi antenna improved SNR by ~6 dB

---

## Discussion

Interpret results. What do they mean? What worked, what didn’t, what do you recommend?  
_Example: LoRa provides best tradeoff of range and simplicity; XBee not suitable; future work: mesh testing._

---

## References

List datasheets, papers, or links that informed your work.

- [LoRa SX1276 Datasheet](https://example.com)
- IEEE paper on RF propagation
- Internal test logs in `/docs/tests/rf-range-test.md`
