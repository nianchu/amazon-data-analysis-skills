# HDMI audio extractor definition

This is a product-specific case reference. Do not apply its gates or parameter schema to unrelated products.

## Core definition

An HDMI audio extractor receives a standard HDMI audio/video source, retains an HDMI video output or pass-through path, and extracts/de-embeds an independent audio output from that same HDMI signal.

## Hard gates

| Gate | Requirement |
|---|---|
| G1 | Standard HDMI source input |
| G2 | HDMI video output or pass-through |
| G3 | Independent audio output: Optical/TOSLINK, coaxial, RCA, 3.5mm, or HDMI audio-only |
| G4 | Audio is extracted/de-embedded from the same HDMI signal |
| G5 | The product is not converting a non-HDMI input into HDMI |

Prove all G1-G5 conditions for the formal pool.

## Allowed extensions

Include separately classified products when they still satisfy G1-G4:

- HDMI splitter, switch, or matrix with audio extraction.
- ARC/eARC as an additional mode.
- HDMI audio-only output while retaining HDMI video output.

## Exclude

- ARC/eARC-only TV-return converters without standard HDMI source input and video pass-through.
- DACs or preamps without HDMI video pass-through.
- Wii, PS1/PS2, N64, AV/RCA/CVBS, component, VGA, USB, DisplayPort, optical, or SDI conversion products whose core direction is not HDMI extraction.
- Plain HDMI splitters without independent audio extraction.
- Audio embedders that add external audio into HDMI.
- Capture cards, extenders, wireless-HDMI products, cables, and accessories.

Gaming compatibility alone is not an exclusion. A standard HDMI-source extractor used with PS5 or Xbox remains eligible.
