# Listing parameter contract

## General rules

- Derive the schema from the target product.
- Keep controlled values consistent in spelling, capitalization, and units.
- Use one column per analytical variable.
- Keep missing explicit claims blank.
- Record contradictory claims as `证据冲突` with both evidence locations.
- Use the current ASIN only.

## HDMI audio extractor schema

| Column | Controlled values |
|---|---|
| 输出端口 | Multi-select: HDMI、Optical/TOSLINK、RCA、3.5mm、同轴 |
| 是否支持ARC/eARC | 不支持、ARC、eARC、ARC/eARC |
| 最高声道 | Explicit maximum such as 2.0、5.1、7.1 |
| 最高分辨率 | Such as 1080P、4K@30Hz、4K@60Hz、4K@120Hz、8K@60Hz |
| HDMI版本 | Such as 1.4、2.0、2.0b、2.1 |
| HDCP版本 | Such as 1.4、2.2、2.3 |
| 是否支持Dolby Vision | 支持; blank when not stated |
| 其他功能 | Multi-select explicit features such as EDID、CEC、镜像、Scaler、HDR10、HDR10+、Dolby Atmos |

Also retain HDMI input, video pass-through, independent audio output, and extraction/de-embedding evidence plus source URL and position.
