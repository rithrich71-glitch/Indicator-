# Indicator-

TradingView (Pine Script v6) indicators for XAUUSD.

## `indicators/xau_volume_bubble_vwap_orb.pine` — Volume Bubble + VWAP (v3)

| Layer | What it does |
|---|---|
| **Volume Bubble** | A bubble on every closed bar whose volume is ≥ 2× its 20-bar average (adjustable). The bubble sits **on that bar's own VWAP price** (volume-weighted price inside the bar, from 1m/5m intrabars; HLC3 if none). It comes in 3 sizes by volume multiple, and the **real volume number** shown in a solid pill above (up bar) or below (down bar) the candle. Colour = candle direction (green up / red down), with no buy/sell estimation. |
| **VWAP** | Session / Week / Month VWAP line; optional ±1σ / ±2σ band lines. |
| **Alerts** | Volume bubble – up bar / down bar / large. |

Install: TradingView → Pine Editor → New indicator → paste → Save → Add to chart.

Note: XAUUSD CFD volume is the broker's tick count, which is the only volume the feed provides. The script shows it as it is. Not compiled here, so check it in the Pine Editor.
