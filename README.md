# Last N Daily High/Low Lines (NinjaTrader 8)

A free NinjaTrader 8 indicator that draws horizontal levels at the **daily high and low** for each of the **most recent N trading sessions**, and keeps them visible during live trading.

## What it does
- Tracks each session’s High and Low
- Draws a horizontal line at each day’s High and Low
- Keeps the most recent **N** sessions (default: 5)
- Updates **today’s** High/Low in real time as price makes new extremes
- Lines extend forward (NT horizontal lines are infinite)

## Best use
Great for identifying higher-timeframe support/resistance on intraday charts:
- Prior day high/low reactions
- Multi-day “ceiling/floor” levels
- Breakout / rejection zones

## Parameters
- **DaysToShow** (default 5): number of most recent sessions to display
- **HighLineBrush**: color for high lines
- **LowLineBrush**: color for low lines
- **LineWidth**: thickness of lines

## Installation (recommended: import via ZIP)
This is the easiest way for end users.

1. Download the release ZIP (or your provided ZIP).
2. Open NinjaTrader 8.
3. Go to **Control Center → Tools → Import → NinjaScript Add-On...**
4. Select the ZIP file and import.
5. If prompted, allow NinjaTrader to compile.
6. Open a chart → right-click → **Indicators**
7. Add **LastNDailyHighLowLines**

### Notes
- Works best on **intraday charts** (e.g., 1m/5m/15m).
- “Day” is based on your chart’s **Trading Hours / session template** (RTH vs ETH matters).

## Installation (developer/manual: paste source file)
If you’re a developer or prefer source installation:

1. Open NinjaTrader 8 → **New → NinjaScript Editor**
2. In the Project tree, expand **Indicators**
3. Right-click **Indicators → Add New Item** (or open an existing indicator file)
4. Create `LastNDailyHighLowLines.cs`
5. Paste the contents from `src/Indicators/LastNDailyHighLowLines.cs`
6. Press **F5** (Compile)
7. Add the indicator to a chart via **Indicators**

## Troubleshooting
- **No lines appear**: make sure you are on an **intraday** chart and that there is enough history loaded for multiple sessions.
- **“Day” boundaries look wrong**: check chart **Trading Hours** template (RTH vs ETH).
- **Performance**: the indicator redraws on each tick to update today’s levels. If you want less redraw frequency, change `Calculate` to `OnBarClose`.

## License
MIT (see LICENSE).
