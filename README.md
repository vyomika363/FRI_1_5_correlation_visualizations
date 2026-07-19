# FRI 1.5 — Interactive Visualisations

Interactive diagrams for the **Financial Readiness Index (FRI) 1.5**, which ranks 15 cities across 37 sub-indicators grouped into 7 parameters.

## Files

**`FRI_1_5_2d.html`** — Correlation Diagram
A chord-style ring that maps the statistical correlation and dependency between all 37 sub-indicators. Teal curves indicate positive correlation; rust indicates inverse. Thicker, darker curves mark stronger relationships. Features include adjustable Alpha (blend between pure data and subjective expert weights), a strength floor slider to filter weak links, and click-to-isolate on any node.

**`FRI_1_5_3d.html`** — Dependency Diagram
A compact variant with a collapsible side panel showing controls, a ranked link table, and a full parameter/indicator tree. Includes the same Alpha and threshold controls alongside a sortable breakdown of the strongest connections.

## Parameters

| # | Parameter | Sub-indicators |
|---|-----------|---------------|
| 1 | Business Environment | 6 |
| 2 | Human Capital | 5 |
| 3 | Infrastructure | 8 |
| 4 | Financial Sector Development | 8 |
| 5 | Reputation | 1 |
| 6 | Innovation & Startup Ecosystem | 6 |
| 7 | Sustainability | 3 |

## How to use

Open either `.html` file directly in a browser — no build step or server required. Everything is self-contained (data, styles, and scripts are inline).

- **Click** any dot on the ring to isolate its connections and dim everything else.
- **Hover** a curve to see the composite correlation score between two sub-indicators.
- **Drag the Alpha slider** to blend between full statistical correlation (α = 1) and full subjective expert weighting (α = 0).
- **Raise the Strength floor** to hide weaker links and focus on the dominant relationships.
- **Methodology** link (top-right) opens the full methodology document.

## Methodology

The composite score for each link is calculated as:

```
S = α · |r| + (1 − α) · w
```

where `r` is the Pearson correlation coefficient across the 15 cities, `w` is the normalised subjective expert weight, and `α` controls the blend. When no expert weight exists for a pair, the score falls back to `|r|`.
