# IGDS — The Information Graphics Design System

> A design system distilled from the principles of **Dona M. Wong** —
> *The Wall Street Journal Guide to Information Graphics*, W. W. Norton, 2010.

---

## 1. Foundation

### 1.1 Philosophy
- **Audience first.** Every choice answers to the reader. The graphic is a service.
- **Content first.** The story dictates the chart, never the reverse.
- **Truth is non-negotiable.** Data integrity precedes all visual decisions.
- **Simplify and distill.** Strip everything that does not earn its place.
- **Round only at the end.** Carry precision to the final step.

### 1.2 The Charting Workflow
1. **Research** — Verify the data and its context.
2. **Edit** — Filter for the message, not the totality.
3. **Plot** — Choose the chart that fits the message.
4. **Review** — Check for fairness, legibility, and the black-and-white test.

---

## 2. Color System

### 2.1 Editorial (Ink & Paper)
| Token | Hex | Usage |
|---|---|---|
| `--ink-black` | `#1A1A1A` | Primary text, primary data series |
| `--ink-soft` | `#2C2C2C` | Body text |
| `--ink-muted` | `#6B6660` | Captions, labels, axis labels |
| `--ink-light` | `#A8A298` | Disabled, hint text |
| `--paper-white` | `#FAF7F2` | Primary background |
| `--paper-cream` | `#F4EFE6` | Secondary background, contrast pane |
| `--paper-rule` | `#D8D2C5` | Borders, rules |
| `--paper-line` | `#E8E2D5` | Grid lines, table separators |

### 2.2 Categorical Data Series
*Use the primary first. Add the next only when truly needed. Four series is the practical limit.*

| Token | Hex | Role |
|---|---|---|
| `--data-primary` | `#1A1A1A` | Series 01 — focus series |
| `--data-secondary` | `#8B6F3F` | Series 02 — ochre |
| `--data-tertiary` | `#4A5D4A` | Series 03 — forest |
| `--data-quaternary` | `#7A3838` | Series 04 — burgundy |

### 2.3 Semantic Data
| Token | Hex | Role |
|---|---|---|
| `--data-positive` | `#2D5016` | Gains, growth |
| `--data-negative` | `#8B2424` | Losses, decline |
| `--data-projection` | `#B8A87E` | Estimates, forecasts (lighter shade of primary) |

### 2.4 Sequential Shades
*Single hue, five steps. For ordered data, magnitudes, choropleth maps.*

```
SHADE 1  #2C2C2C   (100%)
SHADE 2  #5A5550   ( 75%)
SHADE 3  #8B8478   ( 50%)
SHADE 4  #B8B1A3   ( 25%)
SHADE 5  #D8D2C5   ( 10%)
```

The progression must move smoothly without alternating value strips in the middle.

### 2.5 Color Rules
- **Black-and-white test** — Every color chart must remain legible in monochrome.
- **Color blind safe** — Never rely on red-green pairs alone for distinction.
- **One variable, one color** — All bars in a single chart use one color and shade.
- **Shades over hues** — Prefer multiple shades of one color to multiple colors of one shade.
- **Lighter for projections** — Reduced saturation = reduced certainty.

---

## 3. Typography System

### 3.1 Type Families
| Role | Family | Notes |
|---|---|---|
| Display | Playfair Display | 900 / 700 / 400 italic |
| Body | Source Serif 4 | 400 / 600 / 700 / 400 italic |
| Data & Caption | JetBrains Mono | 400 / 500 / 700 — tabular figures |

### 3.2 Type Scale
| Token | Family | Weight | Size / Line / Tracking | Use |
|---|---|---|---|---|
| `display-h1` | Playfair | 900 | 56 / 1.0 / -0.02em | Masthead, hero |
| `display-h2` | Playfair | 700 | 36 / 1.1 / -0.015em | Section titles |
| `display-h3` | Playfair | 700 | 22 / 1.2 / 0 | Chart titles |
| `deck` | Source Serif | 400 italic | 20 / 1.4 / 0 | Subheadings, decks |
| `body` | Source Serif | 400 | 16 / 1.55 / 0 | Paragraph text |
| `body-sm` | Source Serif | 400 | 14 / 1.5 / 0 | Secondary text |
| `caption` | JetBrains Mono | 400 | 11 / 1.6 / 0.15em uppercase | Labels, sources |
| `meta` | JetBrains Mono | 400 | 10 / 1.5 / 0.2em uppercase | Metadata, eyebrows |
| `tabular` | JetBrains Mono | 500 | 14 / 1.0 / tabular-nums | Numbers in tables |

### 3.3 Typographic Conduct in Charts
- **Never angle type.** Rotate the chart instead.
- **Direct labels on lines.** Avoid legends when you can.
- **Whole numbers align flush right.** Decimals align on the point.
- **No more than four lines** on a line chart.
- **Use tabular figures** for any numerical column or alignment.
- **Currency symbols** — be consistent: align with the longest figure or hug each value, not both.

---

## 4. Spacing & Layout

### 4.1 Spacing Scale (4px baseline)
| Token | Value |
|---|---|
| `space-1` | 4px |
| `space-2` | 8px |
| `space-3` | 12px |
| `space-4` | 16px |
| `space-6` | 24px |
| `space-8` | 32px |
| `space-12` | 48px |
| `space-16` | 64px |

### 4.2 Rule Weights
| Token | Value | Use |
|---|---|---|
| `rule-thin` | 0.5px | Tabular grid lines, faint guides |
| `rule-base` | 1px | Section dividers, axis lines |
| `rule-thick` | 2px | Section opener, emphasized axes |
| `rule-heavy` | 4px (or 1px double) | Masthead, major hierarchy breaks |

### 4.3 Proportional Rules from Wong
- **Bar-to-gap ratio: 2:1** — A bar should be roughly twice the width of the space between it and its neighbor.
- **Maximum 4 lines** on a line chart.
- **Pictogram grouping: 5 or 10** — Icons cluster so the reader counts by glance.

---

## 5. Chart Patterns

### 5.1 Vertical Bar Charts
**Rules**
- Begin at the **zero baseline. No exceptions.**
- All bars in a single chart use **the same color and shade**.
- A **lighter shade** distinguishes projections from actuals.
- Bar width ≈ 2 × the gap between bars.
- **No 3D**, no decorative shading, no gradients.
- For broken bars (extreme outliers), mark the break explicitly.

**Anti-patterns**
- Truncated y-axis on a bar chart.
- Different colors per bar measuring the same variable.
- 3D bars where the reader must guess where the top meets the grid.

### 5.2 Horizontal Bar Charts
- Use when category labels are long.
- **Order bars by value**, not alphabet (unless the categorical order is meaningful — e.g., time periods, age cohorts).
- For negative bars, place the zero line in the middle and grow outward.

### 5.3 Line Charts
**Rules**
- **Maximum 4 lines.**
- **Direct-label lines** at their endpoints; the legend order should match the ranking of those endpoints.
- The y-axis does not need to start at zero (unlike bars), but the increments must be meaningful.
- Solid lines preferred. Reserve dashed for projections only.

**Dual y-axes**
- Permitted only when the two series measure related quantities with a defensible linear relationship.
- **Saving space is not a reason.**
- When in doubt: re-index to 100, use comparable scales, or use side-by-side small multiples.

### 5.4 Pie Charts
- The **largest slice begins at 12 o'clock** and reads clockwise.
- Use **shades of one color**, sorted from largest (darkest) to smallest (lightest).
- **Direct-label slices** with both percentage and absolute value.
- Maximum **5 slices**. Beyond that, group into "Other" or use a bar chart.
- **Never 3D, never tilted, never exploded.**
- For two pies of unequal totals, use **proportional pies** (radius ∝ √total).

### 5.5 Tables
- **Whole numbers flush right.** Decimals on the decimal point.
- Use **tabular figures**.
- **Minimize grid lines** — header rule, footer rule, often nothing else.
- **Order rows by meaning** (size, time, category) not alphabet.
- For mixed signs (gains/losses), use color sparingly — prefer +/− symbols.

### 5.6 Pictograms
- Choose **icons that read at small sizes.**
- **Group icons in 5s or 10s** for visual counting.
- Use whole icons. Avoid fractional pictograms; if rounding is required, declare it.

### 5.7 Maps
- Use a map **only when geography is relevant.** Sales by state on a map is misleading when state areas dominate the visual impression.
- Use **solid shades**, not patterns or cross-hatching.
- For change over time, use a **series of small-multiple maps**, not animation alone.

---

## 6. Scale & Numerical Treatment

### 6.1 Comparable Scales
When two series of similar nature (e.g., two stock prices) are charted side by side, the y-axis must be set so equal vertical distances represent equal **relative** changes — not equal absolute changes. Otherwise the more expensive series will always appear more volatile.

### 6.2 Re-indexing to 100
To compare series with different starting magnitudes:
```
indexed_value = (value / start_value) × 100
```
Every series begins at 100; subsequent values reveal proportional change.

### 6.3 Logarithmic Scale
Use when the data spans orders of magnitude. A move from 10 to 100 should occupy the same vertical distance as 100 to 1,000. Always label "log scale" explicitly.

### 6.4 Percentage Hygiene
- **Always declare the base.** "10% increase from 200 to 220."
- **Never average percentages** without weighting by their bases.
- A **percent of a percent** is not the simple sum.
- **Absolute change vs. percent change** can tell opposite stories — choose the one that fits the message and disclose it.

### 6.5 Rate of Return
- Use **arithmetic mean** for simple period-over-period comparison.
- Use **geometric mean (CAGR)** for compounded multi-period returns.
- Disclose which is being shown.

### 6.6 Currencies
- For multi-currency charts, choose: hold currency constant (translate at one rate) or show in local currency with the rate disclosed.
- Never combine without declaring the convention.

---

## 7. Edge Cases

### 7.1 Missing Data
Indicate the gap; do not interpolate.
- Use a **dashed segment** or a **labeled break**.
- Connecting points across an unknown invents history.

### 7.2 Big Numbers, Small Change
When variation is a tiny fraction of the total:
- Do not start at zero — show the change.
- **Annotate the truncation explicitly** so the reader is not deceived.
- Or: chart the percent change directly.

### 7.3 Coloring with Black Ink Alone
A graphic must remain "colorful" in a single ink. Use:
- **Shades of gray** (5 steps available).
- **Stroke weights** (thin/regular/bold).
- **Dotted/dashed strokes** sparingly, with consistent meaning.
- **Hatching and pattern fills** only when shades are exhausted.

---

## 8. Operational Charts

### 8.1 Org Chart
- Reporting lines only.
- **Limit each branch** to what the reader must understand.
- Boxes and connector lines, no decoration.

### 8.2 Flow Chart
- Decisions = diamonds. Processes = rectangles. Terminators = rounded rectangles.
- Arrows are unambiguous and one-directional unless stated otherwise.

### 8.3 Work Plan (Gantt)
- Tasks descend; time advances.
- Dependencies show as overlap or connector arrows.
- Use the **lighter projection shade** for forecasted/contingent tasks.

### 8.4 Timeline
- Horizontal axis of dates at scale.
- **Resist compressing** quiet periods — distortion erodes trust.

### 8.5 Spider Chart
- Useful only for **small profile counts** across **few dimensions** (3–6 axes).
- Beyond that, switch to small-multiples bar charts.

### 8.6 Schedule & Budget
- Combined view of time and money.
- Reader must spot slippage in either dimension instantly.

---

## 9. The Final Checklist

Before any chart ships, every one of these must be answered "yes."

1. **Message** — Can a stranger state the story in one sentence from the title and chart?
2. **Comparison** — Are bases declared, scales matched, baselines correct, percentages with denominators?
3. **B&W test** — Does it survive grayscale printing?
4. **Color blind** — Is hue carrying the meaning alone? (It shouldn't.)
5. **Provenance** — Are source and date present?
6. **Decoration** — Is everything earning its ink? Drop shadows, 3D, gradients, decorative icons — out.
7. **Dual axis defense** — If two y-axes, is there a real linear relationship?
8. **Rounding** — Was rounding deferred until the final step?
9. **Truncation disclosure** — If any axis was truncated, is it labeled?
10. **Audience** — Would the intended reader understand this in five minutes?

---

## 10. Component Index

| Component | Tokens used | Notes |
|---|---|---|
| Masthead | `display-h1`, `meta`, `paper-rule`, `rule-heavy` | Double-rule under masthead, eyebrow row above |
| Section header | `display-h2`, `deck`, `rule-thick`, `space-12` | Numbered, with deck |
| Chart frame | `paper-white`, `rule-base`, `space-6` | Title + subtitle + chart + caption |
| Compare panel (Do/Don't) | `paper-white` / `paper-cream`, `data-positive` / `data-negative` | Side-by-side, equal weight |
| Pull quote | `display-h2` italic, `rule-heavy` top, `rule-base` bottom | Centered |
| Rule strip | 3-column grid, `display-h3`, ornament glyph | Card-based axiom display |
| Swatch grid | 1px gridlines on `paper-rule`, `meta` labels | Color token reference |
| Tabular | `JetBrains Mono` 500 tabular-nums | Right-align numbers, color +/− |

---

## Sources

Wong, Dona M. *The Wall Street Journal Guide to Information Graphics: The Dos and Don'ts of Presenting Data, Facts, and Figures.* W. W. Norton & Company, 2010. 157 pp. ISBN 978-0-393-07295-2.

Structural inspiration: the book's own mini-workshop format — paired examples, prescriptive rules, restraint above flourish.
