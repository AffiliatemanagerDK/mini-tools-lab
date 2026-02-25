# Mini Tools Lab — Design System v2

Every tool shares brand DNA but has its own visual personality. The hub should feel like a curated collection of specialist instruments — not the same template reskinned five times.

---

## LAYER 1: SHARED DNA (same on every tool)

These are the ONLY things that stay identical across tools:

### Brand constants
- **Dark base:** Background is always dark (`#0B1121` to `#0F172A` range). Never white.
- **Typography:** Same font family across all tools (Inter, Satoshi, or General Sans).
- **Card surface treatment:** Glassmorphism cards — `rgba(255,255,255,0.04-0.08)` with backdrop-blur and subtle border.
- **Header pattern:** Tool logo + name (left), utility controls + "← Tool Hub" (right).
- **Footer:** "Built by Mini Tools Lab" — centered, muted.
- **Pill badges:** Same style for trust signals (Privacy-first, No API, Browser-side).
- **Sticky bottom bar** with key outputs + Copy/Reset. Always present.
- **Pre-filled default values.** Never show "-" on load. This is non-negotiable.
- **Color-coded output states** (green/orange/red for healthy/warning/danger).

### Brand DON'Ts
- ❌ No white backgrounds, ever.
- ❌ No empty/placeholder outputs on load.
- ❌ No contradictory labels (positive label on negative number).
- ❌ No default browser-styled form elements.

That's it. Everything else is FLEXIBLE per tool.

---

## LAYER 2: TOOL PERSONALITY (unique per tool)

Each tool chooses its own combination from the options below. No two tools should make the same choices across all categories.

### A. Accent color (pick ONE primary accent per tool)
- Electric teal / cyan (`#22D3EE`) — MarginRadar uses this
- Amber / gold (`#F59E0B`) — warm, inventory/stock feel
- Violet / purple (`#A78BFA`) — premium, analytical
- Emerald (`#10B981`) — growth, health
- Rose / coral (`#FB7185`) — urgency, alerts
- Blue (`#3B82F6`) — trust, data

Each tool owns its accent. It tints: sliders, focus rings, active states, primary output numbers, links, icons.

### B. Layout archetype (pick ONE per tool)

**1. Control Panel** (MarginRadar uses this)
Two-column card grid. Sliders + inputs on left/right. Dense, dashboard-like.
Best for: tools with two related calculators.

**2. Vertical Flow / Timeline**
Single column. Inputs flow top-down in a clear sequence.
Outputs appear as a result "destination" at the bottom — like arriving at an answer.
Best for: tools with one linear calculation (input → process → result).
StockPulse fits this.

**3. Scenario Comparator**
Side-by-side columns where the user builds 2-3 scenarios and compares them.
Think "before/after" or "option A vs B".
Best for: PromoGuard (compare discount scenarios), A/B test tools.

**4. Dashboard / Scorecard**
Output-first layout. Big numbers and visualizations at the top.
Inputs collapse into an "assumptions" panel below or in a sidebar.
Best for: tools where the result is the star, not the inputs.

**5. Wizard / Stepper**
Multi-step flow with progress indicator. One section at a time.
Reveals complexity progressively.
Best for: complex tools with 8+ inputs that would overwhelm in a single view.

### C. Input style (pick ONE primary style per tool)

**1. Slider + number input combo** (MarginRadar uses this)
Best for: ranges where dragging aids exploration.

**2. Styled number inputs only** (no sliders)
Clean, compact.
Best for: tools where precision matters more than exploration, or where inputs are few.

**3. Segmented controls / button groups**
For categorical or preset choices.
E.g., "Low / Medium / High" or "Express / Standard / Economy".

**4. Card selectors**
Clickable cards for major choices.
E.g., selecting a shipping method, product category, or scenario.

**5. Inline editable table**
For tools with multiple SKUs, line items, or rows of data.

Mix styles within a tool when it makes sense — e.g., sliders for the main inputs + a segmented control for a mode toggle.

### D. Hero visualization (pick ONE per tool — this is what makes each tool visually memorable)

**1. Donut / radial gauge** (MarginRadar uses this)
Shows a percentage or health score.

**2. Horizontal runway bar**
A progress-style bar showing "days remaining" or "stock remaining".
Depletes left-to-right.
Color shifts green → orange → red as it empties.
Perfect for StockPulse.

**3. Timeline / Gantt-style bar**
Shows dates on a horizontal axis.
"Today" marker, "reorder date" marker, "stockout date" marker.
Visual storytelling of time.

**4. Before/after split**
Two big number cards side by side showing the delta.
Great for promo/discount tools.

**5. Sparkline or mini area chart**
Shows a projected trend (e.g., inventory depletion over time, margin under different scenarios).

**6. Traffic light / signal**
Three stacked circles (red/yellow/green).
Instantly scannable.
Great for go/no-go decisions.

**7. Animated counter / odometer**
Large number that rolls like a mechanical counter when inputs change.
High-impact, single-number tools.

### E. Micro-interaction flavor (pick a vibe)

**1. Precision** — clean transitions, no bounce, everything ease-out. Surgical. (MarginRadar)

**2. Pulse** — heartbeat-like animations, breathing glows, rhythmic. (StockPulse — it's a "pulse" after all)

**3. Snap** — quick, snappy spring animations. Playful but fast.

**4. Gravity** — elements slide in from top, numbers cascade down. Weighty, impactful.

---

## TOOL ASSIGNMENTS

### MarginRadar (existing — reference implementation)
- Accent: Teal/cyan
- Layout: Control Panel (2-col)
- Inputs: Slider + number combo
- Hero viz: Donut gauge
- Micro vibe: Precision

### StockPulse (needs redesign)
- Accent: **Amber/gold** (`#F59E0B`) — warm, warehouse feel. Urgency.
- Layout: **Vertical Flow** — single column. Inputs are a short linear sequence (stock → velocity → lead time → safety → MOQ), and the "answer" is a destination at the bottom.
- Inputs: **Styled number inputs only** (no sliders — StockPulse has only 5 inputs, sliders add bulk without value here). Consider a segmented control for a "velocity period" toggle (units/day vs units/week).
- Hero viz: **Horizontal runway bar** showing days remaining. "Today" on the left, "Stockout" on the right. Fill level depletes and changes color. Below it, a **timeline bar** with markers for "Reorder by" date and "Stockout" date — this tells a visual story that numbers alone can't.
- Micro vibe: **Pulse** — gentle breathing glow on the risk status indicator. The runway bar subtly pulses when in warning/critical zone. Fits the "pulse" name perfectly.
- Additional unique element: **Calendar date display** for reorder date. Show an actual date (e.g., "March 14, 2026") with a small calendar icon, not just "X days". Makes it actionable — the user can put it in their calendar.
- Output cards: Arrange the 4 outputs in a **2x2 grid of mini-cards** instead of a vertical list. Each card gets an icon, the number, and a sublabel. This is visually distinct from MarginRadar's output style.

### PromoGuard (future)
- Accent: **Rose/coral** (`#FB7185`) — promotions, urgency, deals.
- Layout: **Scenario Comparator** — side-by-side "No discount" vs "With discount" columns.
- Inputs: **Segmented controls** for discount type (%, fixed, BOGO) + number inputs for values.
- Hero viz: **Before/after split** — two big cards showing margin with vs without the promo.
- Micro vibe: **Snap** — quick toggling between scenarios feels responsive and fun.

### Future tools: always pick DIFFERENT combinations from the options above.
Check existing tools first and deliberately diverge.

---

## HOW TO USE THIS DOCUMENT

When building a new tool:
1. Check which accents, layouts, input styles, and hero vizzes are already taken.
2. Pick a DIFFERENT combination for the new tool.
3. Apply Layer 1 (shared DNA) exactly as specified.
4. Apply Layer 2 (personality) based on your chosen combination.
5. If in doubt, the test is: "If I put screenshots of all tools side by side, can I instantly tell them apart?" If no, you need more differentiation.

---

*This is the canonical design system for Mini Tools Lab. Every tool ships styled from v1 with its own visual identity. There is no "plain first, style later" phase.*
