# Indicator-

TradingView (Pine Script v6) indicators for XAUUSD order-flow style analysis.

## `indicators/xau_volume_bubble_vwap_orb.pine` — Volume Orbs + VWAP (v2)

| Layer | What it does |
|---|---|
| **Volume Orbs** | Only the N highest-volume closed candles in the last window (default 5 in 100 bars, at least 5 bars apart). Each orb has a glowing dot above the candle, a volume pill below it (`3.2K VOL  Δ+42%`) and a level line at that candle's volume-weighted price. A solid line means the level has not been retested yet; a dotted line means it has. Orbs are green for buy, red for sell and yellow for absorption. Everything is redrawn on the last bar, so the chart stays clean. |
| **VWAP** | Anchored (Session / Week / Month) with thin ±1σ / ±2σ lines. Band fill is optional. |
| **Opening Range** | Optional and off by default: NY / COMEX / London / Asia / custom times, with 1R/2R targets and breakout / failed-breakout markers. |
| **Dashboard** | Compact: delta source, volume ×average, Δ%, VWAP σ, and opening-range state when it is on. |

### Install
TradingView → Pine Editor → New indicator → paste the file → Save → Add to chart. On a 1m chart, delta uses the bar-shape estimate, because 1m intrabars on a 1m chart would always read ±100%.

### Limitations
- XAUUSD CFD volume is the broker's tick count, not traded size. Delta is an estimate, not aggressor data.
- Defaults have not been backtested. The script has not been compiled here, so check it in the Pine Editor.
