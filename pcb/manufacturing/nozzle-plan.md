# Nozzle Plan — Opulo LumenPnP

Populate the **top (front) side first** since it has the smaller components.

## Top Side Pass: N045 + N1

| Nozzle | Packages | Count |
|--------|----------|-------|
| N045 | 0402 caps & resistors | 42 |
| N1 | SK6805-EC15 LEDs (1.5x1.5mm), 0603, SOT-23-5, SC-70-5, SOD-128, 3.2x2.5mm oscillators | 97 |

## Bottom Side Pass 1: N1 + N2

| Nozzle | Packages | Count |
|--------|----------|-------|
| N1 (or N045) | 0402, 0603, DFN-10, SOT-23/SOT-23-6, SOT-563, SC-70-5 | 109 |
| N2 | 0805, QFN-16, QFN-20, SRN4018 inductors (4x4mm), CP_Elec (5x3.9mm), SOIC-8 | 20 |

## Bottom Side Pass 2: N2 + N4

Use PnP for the large QFNs to avoid smashing solder paste and causing shorts.

| Nozzle | Packages | Count |
|--------|----------|-------|
| N4 | QFN-56 RP2040 (7x7mm), QFN-100 USB7206C (12x12mm) | 2 |

## Manual Placement

| Packages | Count |
|----------|-------|
| USB-C receptacles, USB-A receptacles, FFC connector, tact switch | 7 |

## Rotation Verification Checklist

KiCad and OpenPnP may disagree on 0° rotation. Before running a full board,
place one of each polarized/asymmetric package on a scrap board and verify
pin 1 orientation under a microscope.

Check the per-feeder tape rotation offset in OpenPnP — parts come off tape
at a fixed orientation that depends on how the feeder sits on the machine.

### Polarized — rotation critical
- [ ] SK6805-EC15 LED (84/board — verify one early, a 180° mistake is expensive)
- [ ] BAV70 SOT-23 diode (42/board)
- [ ] PMEG3030EP SOD-128 Schottky diode
- [ ] APXF6R3ARA151ME40G polymer electrolytic cap (CP_Elec 5x3.9)

### Pin 1 orientation critical (QFN/DFN)
- [ ] RP2040 QFN-56 (7x7mm)
- [ ] USB7206C QFN-100 (12x12mm)
- [ ] CBTL02043ABQ QFN-20 (2.5x4.5mm)
- [ ] PTN5110NHQZ QFN-16 (2.6x2.6mm)
- [ ] PUSB3FR4Z DFN-10 (1x2.5mm)

### Asymmetric — verify orientation
- [ ] SN74LVC1G08DCKR SC-70-5
- [ ] AP22811AW5-7 SOT-23-5
- [ ] LP5907MFX-3.3 SOT-23-5
- [ ] USBLC6-2SC6 SOT-23-6
- [ ] TLV62585DRLR SOT-563
- [ ] W25Q16JVSSIQ SOIC-8
- [ ] XO23C3EREHX25M000 oscillator (3.2x2.5mm)
- [ ] ABM8G crystal (3.2x2.5mm)

### Non-polarized — low risk
- 0402 caps and resistors (symmetric, no polarity)
- 0603 caps and resistors (symmetric)
- 0805 caps (symmetric)
- SRN4018 inductors (symmetric)
