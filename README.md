# M15 Weekly Edge

A mid-term, weekly-trade strategy built around monthly trend direction, M15 pullbacks, ZigZag structure, Fibonacci levels, LWMA confluence, and staged position management.

## 1. Timeframe

- Primary execution timeframe: **M15 (15-minute)**.
- The strategy is designed for **weekly trade opportunities** and a **mid-term trading horizon**.

## 2. Markets

The strategy is applied to five markets:

- EUR/USD
- XAU/USD (Gold)
- BTC/USD (Bitcoin)
- DJI (Dow Jones Industrial Average)
- Brent Crude Oil

## 3. Volume

- The strategy uses the **Volume** indicator as part of market analysis.

## 4. Moving Averages

Two Linearly Weighted Moving Averages (LWMA) are used:

- **LWMA 55**
- **LWMA 220**

## 5. ZigZag

The ZigZag configuration is:

- **Depth:** 350
- **Deviation:** 150
- **Backstep:** 60

ZigZag is used to define the relevant swing structure and legs of the setup.

## 6. Fibonacci Retracement

A **Fibonacci Retracement** is applied to the relevant ZigZag structure.

Configured levels:

- **33.4**
- **113**
- **200**
- **400**

## 7. Monthly Trend

Trade direction is determined by the established **monthly technical and fundamental trend**.

- Monthly trend UP → only the long-side setup is considered.
- Monthly trend DOWN → the corresponding short-side setup is considered.

The strategy does not define the monthly technical/fundamental trend calculation further at this stage.

## 8. Pullback

The strategy requires a **pullback against the established monthly technical and fundamental trend** before an entry setup is considered.

The pullback is identified through the ZigZag structure and its Fibonacci levels. It must develop as a corrective movement relative to the primary monthly trend and provide the reaction/structure required for subsequent entry confirmation.

The pullback itself is **not an entry signal**. Entry requires the defined confirmation conditions.

## 9. Long Entry Setup

When the monthly technical and fundamental trend is **UP**:

1. Wait for a downward ZigZag reaction/pullback.
2. Apply Fibonacci Retracement to the relevant ZigZag structure.
3. Around the **33.4 Fibonacci level**, identify the latest price reaction and draw the relevant trendline.
4. A long entry becomes valid only when:
   - Price breaks above the trendline; and
   - **LWMA 55** crosses/breaks above the same trendline.

Both conditions are required for the long entry confirmation.

## 10. Stop Loss

For a long trade, the initial Stop Loss is placed **below the low of the relevant ZigZag reaction**.

The corresponding short-side implementation is the directional inverse and must follow the same structural logic.

## 11. Position Structure and Take Profit

Each trade is opened with **three positions**.

Take-profit levels are defined by the Fibonacci structure:

- **TP1 = 113**
- **TP2 = 200**
- **TP3 = 400**

Management sequence:

### TP1 — 113

- Close **1 position**.
- Keep **2 positions** open.
- Move the Stop Loss of both remaining positions to **33.4**.

### TP2 — 200

- Close **1 position**.
- Keep **1 final position** open.
- Move the Stop Loss of the final position to **113**.

### TP3 — 400

- The final position is held toward **400**, unless the adjusted Stop Loss is triggered first.

## 12. ZigZag Leg Formation and 33.4 Reaction

During the formation of each ZigZag leg, price is expected to produce a reaction around its own **33.4 Fibonacci level**.

The price level that ultimately becomes the completed and clearly defined structure is determined later as the ZigZag leg develops.

A ZigZag leg is therefore **not treated as final while it is still forming**. The final structure is determined only after the relevant price action completes and the ZigZag point is confirmed.

This distinction is important for avoiding look-ahead bias in research and backtesting.

## 13. 33.4 Touch, Pullback, and Continuation Toward 113

After price moves upward and **touches the 33.4 Fibonacci level**, price may make a **pullback/reaction** before continuing toward the **113 Fibonacci level**.

This pullback is a new minor corrective movement that can form within the broader move from 33.4 toward 113.

The sequence is therefore:

**33.4 touch → minor pullback/reaction → continuation toward 113**

The pullback does not mean that the broader move has failed; it is part of the price-action development toward the next Fibonacci level.

## 14. Shark Pattern

The Shark Pattern consists of **four ZigZag legs and five price points**.

- Five consecutive ZigZag points define four legs.
- Draw a trendline between **Point 1 and Point 3**.
- A break of the Point 1–Point 3 trendline is used to identify and confirm **Leg 4** of the Shark Pattern.

Pattern completion/confirmation is based on the confirmed ZigZag structure together with the relevant trendline break.

## 15. Confluence Confirmation

Before confirming a trade setup, the following elements are evaluated together:

1. **Price Action** — highs and lows formed by the last two ZigZag legs.
2. **Fibonacci Structure** — Fibonacci levels derived from the last two ZigZag legs.
3. **Moving Averages** — LWMA 55 and LWMA 220.
4. **Break Structure** — relevant break levels and structural breaks formed by the last two ZigZag legs.

These elements form the strategy's confluence framework for trade confirmation. Exact relationships between the individual confluence components are intentionally left undefined until the corresponding rules are specified.

## Core Strategy Flow

```text
Monthly Technical + Fundamental Trend
                    ↓
                Pullback
                    ↓
             ZigZag Structure
                    ↓
          Fibonacci 33.4 Reaction
                    ↓
          Confluence Confirmation
                    ↓
      Trendline Break + LWMA 55 Break
                    ↓
                Entry
                    ↓
          3-Position Management
                    ↓
       113 → 200 → 400 Targets
```

## Research Principles

The strategy specification is intended to remain mechanically testable. In particular:

- Unconfirmed ZigZag points must not be treated as known future information.
- Final ZigZag structures are only available after confirmation.
- Entry conditions must be evaluated using information available at the decision time.
- Position management must follow the defined staged exits and Stop Loss adjustments.

## Status

**Strategy specification v1 — rules 1–15 captured.**

Further rules should be added only when explicitly defined; no additional entry filters or relationships should be assumed.