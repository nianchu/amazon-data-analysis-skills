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

The decisive test is the complete signal path:

`standard HDMI source → HDMI video output/pass-through + independent extracted audio output`

The words `audio extractor`, a resolution claim, gaming compatibility, or ARC/eARC support do not prove this path by themselves.

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

## Case-tested boundary rules

- Include an HDMI splitter, switch, matrix, decoder, scaler, or video-wall controller only when its Listing proves an independent extracted audio output in addition to HDMI video output.
- Exclude a plain HDMI splitter that only duplicates HDMI audio/video to multiple displays.
- Exclude a TV ARC/eARC adapter that sends TV-return audio to Optical/RCA/3.5mm but has no standard HDMI source input plus video pass-through.
- Include ARC/eARC products when ARC/eARC is an additional mode and the standard HDMI-source extraction path still exists.
- Treat `HDMI to Optical/RCA` in a title as ambiguous until the Listing confirms whether HDMI video continues to an HDMI output.
- A decoder remains eligible when it accepts HDMI, retains HDMI video output, and produces independent decoded audio.
- If the ASIN Listing is unavailable, use manufacturer or authorized product documentation. Leave it pending when the full path still cannot be proven.
