# Indicator-

TradingView (Pine Script v6) indicators for XAUUSD order-flow style analysis.

## `indicators/xau_volume_bubble_vwap_orb.pine` — Volume Bubble + VWAP + ORB

| Layer | What it does |
|---|---|
| **Volume Bubble** | Circles on bars with unusual volume (z-score ≥ threshold, 3 size tiers, optional glow). Color = estimated buy/sell delta; yellow = absorption (big volume, small body ≤ 0.3 × ATR). Hover a bubble for details. |
| **VWAP** | Anchored VWAP (Session / Week / Month) with ±1σ / ±2σ bands and shaded outer zones. |
| **ORB** | Opening range for New York 09:30 ET, COMEX 08:20 ET, London 08:00, Asia 09:00 Tokyo or a custom time. Draws the high, low and mid lines, a range zone and +1R/+2R and −1R/−2R targets. |
| **Signals** | `ORB ▲ / ▼` on the first close outside the range. `★` = confluence (volume bubble + delta in the same direction + correct side of VWAP). `✕ Fail` = price closed back inside within N bars (possible trapped traders). |
| **Dashboard** | Delta source, bar Δ%, volume z, distance from VWAP in σ, ORB status and range, intrabar coverage, volume type. |

### How to install
1. TradingView → **Pine Editor** → **Open → New indicator**.
2. Delete the template, paste the whole file, click **Save**, then **Add to chart**.
3. Recommended charts: **XAUUSD 5m–15m** for ORB, **1h–4h** for bubbles and VWAP. For ORB on charts of 1h and above, the range is built from intrabars, so set Range length to at least the intrabar timeframe.

### Important limitations (from the research)
- On XAUUSD CFD feeds, volume is **broker tick count**, not traded contracts, so values differ between brokers.
- Delta is an **estimate** from lower-timeframe candle direction (close vs open + tick rule), the same method as TradingView's aggregated Volume Delta. It is not exchange aggressor data. When there are no intrabars, the script falls back to a bar-shape estimate, and the dashboard shows which source was used.
- Intrabar history is limited by plan (100K / 125K / 200K intrabars). Older bars use the fallback.
- **All thresholds are proposed defaults, not backtested.** Signals use closed bars only. After you change settings, re-create your alerts.
- The script has **not been compiled in this repository**. Check it in the Pine Editor first.

### Alerts
ORB breakout up/down, ORB strong breakout, ORB failed breakout, Buy / Sell volume bubble, Absorption bubble. Use **"Once per bar close"**.
