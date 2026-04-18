# ICT-Weekly-Template-Dashboard-Scanner
A dashboard I made for my friends who aren't very familiar or comfortable with analyzing forex charts on MT5 or Tradingview

---

## What It Does

A multi-symbol ICT weekly template scanner that runs from a single chart and monitors up to 12 forex pairs simultaneously. Based on the ICT weekly template methodology 
---

A **"Yes / Sell"** or **"Yes / Buy"** signal means the full criteria have been met for that symbol on that day.

---

## Signal States

| Signal | Meaning |
|---|---|
| `Yes / Buy` | Full buy criteria met |
| `Yes / Sell` | Full sell criteria met |
| `Maybe Sell >` | High swept but no bearish close yet — watch tomorrow |
| `Maybe Buy >` | Low swept but no bullish close yet — watch tomorrow |
| `Inside Day` | Tuesday traded inside Monday's range — no setup |
| `Maybe NW` | No setup this week — watch next week |
| `Waiting...` | Day has opened but candle not yet closed |
| `—` | Weekend or Monday reset |

---

## Setup

1. Copy `ICT_Weekly_Scanner.mq5` into your `MQL5/Experts` folder
2. Open MetaEditor and compile the file
3. Attach the EA to **any single chart** — it doesn't matter which pair or timeframe the host chart is
4. Make sure **Algo Trading is enabled** in MT5 (the scanner doesn't place trades but needs this for market watch access)

---

## Inputs

| Input | Default | Description |
|---|---|---|
| `InpPanelX` | `10` | Horizontal offset of the dashboard from the screen edge |
| `InpPanelY` | `80` | Vertical offset — increase to push the dashboard lower |
| `InpCardCols` | `4` | Number of symbol cards per row — adjust to fit your screen |
| `InpCorner` | `CORNER_LEFT_UPPER` | Which corner the dashboard anchors to |

```

## Screen Size Guide (InpCardCols)

| Screen | Recommended Columns |
|---|---|
| Laptop (1366×768) | 3 |
| 1080p (1920×1080) | 4 – 5 |
| 1440p / Ultrawide | 5 – 6 |

---

## Important Notes

- The scanner only updates on a **new Daily candle** — it won't repaint or flicker on every tick
- If you attach the scanner **mid-week** (e.g. on a Friday), it will reconstruct the week's high and low from that week's existing candles automatically — no need to wait for Monday
- The scanner is **display only** — it does not place, modify, or close any trades
- All objects are cleaned up automatically when the EA is removed from the chart

---

*Built on the ICT Weekly Template methodology — for Crash Bandicoot & Dr. Benio, by Spook*
