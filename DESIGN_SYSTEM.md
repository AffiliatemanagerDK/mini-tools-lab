# Mini Tools Lab — Design System v3

The hub is a curated collection of specialist instruments. Each tool should feel like its own product that happens to share a family resemblance.

Think of it like Teenage Engineering's product line — every product is unmistakably "them" but no two products look alike.

---

## LAYER 1: SHARED DNA (the ONLY constants)

This list is intentionally minimal. If it's not listed here, it's FREE to vary per tool.

1. **Dark base.** Background is always in the dark spectrum (#0B1121 to #1E293B). Never white. But the shade, gradients, grain, and texture are free to vary.
2. **One font family** across all tools (Inter, Satoshi, or General Sans). But sizes, weights, and how type is used can vary dramatically.
3. **"← Tool Hub" link** exists somewhere in the header area.
4. **"Built by Mini Tools Lab"** exists somewhere at the bottom.
5. **Pre-filled values.** Tools always show a live result on first load. Never "-" or empty.
6. **Output color logic.** Green = good, orange = warning, red = danger. The shades, how they're applied, and what visualization they appear in — all free to vary.
7. **Functional buttons.** Every tool has a way to copy results and reset inputs. Where they live and how they look is free.

That's it. Seven rules. Everything else below is a menu of options, not requirements.

---

## LAYER 2: TOOL PERSONALITY

For each new tool, make deliberate choices across these dimensions.
The rule is simple: **look at what existing tools chose, then choose differently.**

### A. COLOR ACCENT

Pick one. It tints interactive elements, key outputs, and the tool's overall mood.

| Color | Hex | Mood | Taken by |
|-------|-----|------|----------|
| Teal/cyan | #22D3EE | Precision, tech | MarginRadar |
| Amber/gold | #F59E0B | Warmth, urgency | — |
| Violet | #A78BFA | Premium, analytical | — |
| Emerald | #10B981 | Growth, health | — |
| Rose/coral | #FB7185 | Deals, alerts | — |
| Sky blue | #38BDF8 | Trust, calm | — |

### B. PAGE STRUCTURE

This is where the biggest visual differentiation comes from.
Don't just pick a "layout" — think about the EXPERIENCE of using the tool.

**1. Stacked Cards** (MarginRadar uses this)
Traditional form-like flow. Cards with grouped inputs stacked or in columns. Familiar, dense.

**2. Output-First / Dashboard**
The hero IS the output. Big visualization(s) dominate the top 60% of the viewport.
Inputs are collapsed below in an accordion, a slide-out drawer, or a compact settings panel.
The user sees the ANSWER first and tweaks assumptions second.

**3. Horizontal Swimlanes**
Content flows in horizontal bands across the full viewport width.
Each band is a different "zone" with its own background shade, height, and content type.
Creates a layered, parallax-like depth.
Think of it as a scrollytelling page where each section is visually distinct.

**4. Split Screen**
Left half = inputs. Right half = live outputs. Persistent side-by-side.
On mobile: tabs or a toggle between "Configure" and "Results" views.

**5. Scenario Builder**
Multiple columns the user can add/remove. Each column is a scenario.
Great for comparison tools (PromoGuard).

**6. Wizard / Stepper**
One step at a time. Progress bar at top. Reveal complexity progressively.
Final step = full results dashboard.

**7. Single Canvas**
One big interactive visualization IS the tool.
Inputs are overlaid as floating controls or embedded directly into the viz (e.g., draggable points on a chart, editable numbers inside a diagram).
Minimal chrome.

### C. INPUT TREATMENT

How the user enters data. This changes the entire feel of interaction.

**1. Slider + number box** (MarginRadar uses this)
Exploratory. Good for ranges.

**2. Clean number inputs only**
Minimal, fast. Good for tools with few inputs.
Can be styled as large, bold inline-editable numbers.

**3. Inline editable — numbers live inside the output visualization**
The number IS part of the graphic.
User clicks a number in a diagram/chart/sentence and edits it in place.
No separate "form" area.

**4. Natural language input**
"I have [___] units, selling [___] per day, lead time is [___] days"
Inputs are embedded in a readable sentence. The form IS the explanation.

**5. Card/tile selectors + number inputs**
Major choices as clickable cards (e.g., shipping method, product category), detail values as number inputs.

**6. Compact parameter row**
All inputs in a single horizontal row or grid at the top — like a toolbar/control bar.
The rest of the page is all output.
Good for tools with 3-6 simple inputs.

### D. HERO VISUALIZATION

The single most memorable visual element per tool.
This is what makes each tool instantly recognizable in a screenshot.

**1. Donut / radial gauge** (MarginRadar uses this)

**2. Runway depletion bar**
Horizontal bar that empties left-to-right.
Shows time remaining.
Color gradient shifts as it depletes.

**3. Timeline with date markers**
Horizontal timeline.
"Today" pin, "Reorder by" pin, "Stockout" pin.
Distances are proportional to actual days.
Tells a time story.

**4. Animated counter / odometer**
A single giant number that rolls/ticks when inputs change.
Mechanical counter feel.
Dramatic for single-KPI tools.

**5. Comparison bars / before-after**
Two horizontal bars or two big number cards showing delta between scenarios.

**6. Heat map or risk matrix**
Colored grid cells.
Great for multi-variable risk assessment.

**7. Sparkline / area chart**
Projected depletion curve, margin curve over time, etc.
Adds a temporal dimension.

**8. Isometric or 3D illustration**
Stylized warehouse boxes, product stacks, etc.
Decorative but informative — stack height represents quantity.

**9. Circular countdown**
Like a timer/clock face counting down days.
Combines the urgency of a countdown with the radial aesthetic.

**10. Status dashboard with signal indicators**
Multiple small indicators (dots, traffic lights, status bars) arranged in a grid.
Each shows one metric's health at a glance.
Feels like a monitoring console.

### E. ANIMATION PERSONALITY

**1. Precision** — clean ease-out, no bounce. Surgical. (MarginRadar)

**2. Pulse** — breathing glows, rhythmic fades. Living, organic.

**3. Snap** — spring physics, quick overshoots. Energetic.

**4. Gravity** — elements drop in, numbers cascade. Weighty.

**5. Typewriter** — numbers and text reveal character by character. Retro-tech.

### F. SURFACE TREATMENT

The card/container style. This subtly but powerfully changes the feel.

**1. Glassmorphism** — frosted glass, blur, subtle borders. (MarginRadar uses this)

**2. Solid elevated cards** — opaque dark cards with soft shadow. No blur. Clean and defined.

**3. Borderless sections** — no cards at all. Content sits on subtle background shade shifts between sections. Minimal, editorial.

**4. Outlined/wireframe** — thin borders, no fills. Blueprint/schematic feel.

**5. Gradient mesh backgrounds** — subtle color gradients behind sections. Atmospheric, modern.

**6. Noise/grain texture** — subtle film grain overlay on surfaces. Analog, tactile.

---

## OUTPUT BAR BEHAVIOR (replaces "sticky bar" rule)

### Desktop (>768px)

**No sticky bar.**
Outputs live inline in the layout — in a sidebar, in the top section, or as part of the visualization.
On desktop the viewport is large enough that good layout eliminates the need for sticky elements.

### Mobile (<768px)

**Smart sticky bar** that appears ONLY when the output section has scrolled out of the viewport.
Uses IntersectionObserver:
- Output section visible → no sticky bar.
- Output section scrolled away → sticky bar fades in.
- Footer enters viewport → sticky bar fades out (never blocks footer).

Implementation: observe both the output section and the footer.
Bar is visible only when outputs are NOT in view AND footer is NOT in view.

### Copy/Reset buttons

Live wherever makes sense per tool — in the output section, in the sticky bar on mobile, in a toolbar, or as floating actions.
Not mandated to a specific location.

---

## TOOL ASSIGNMENTS

### MarginRadar ✅ (shipped)
- Accent: Teal
- Structure: Stacked Cards (2-col on desktop)
- Inputs: Slider + number box
- Hero viz: Donut gauge
- Animation: Precision
- Surface: Glassmorphism

### StockPulse 🔄 (needs redesign — currently too similar to MarginRadar)

**Direction: "Output-First Dashboard" — the answer dominates, inputs are secondary.**

- **Accent: Amber/gold** (`#F59E0B`). Warm, warehouse, urgency.
- **Structure: Output-First Dashboard.** Top 50-60% of the page is a big, visual results area. Below that, a compact inputs section — either in an accordion panel labeled "Assumptions" that can collapse, or as a compact parameter grid (2-3 columns of small input fields). The inversion of MarginRadar's "form first, result at bottom" structure is the single biggest differentiator.
- **Inputs: Natural language input** — or at minimum, a compact parameter row. Five inputs can fit in a tight 2x3 grid without needing individual slider rows. Each input is just a label + a styled number field. No sliders, no sublabels (tooltip on hover/tap instead). This makes it feel fundamentally different from MarginRadar's tall, slider-heavy form.
- **Hero viz: Timeline with date markers.** A horizontal timeline spanning the top section showing:
  - "Today" (left, pinned)
  - "Reorder by [date]" (amber marker)
  - "Stockout [date]" (red marker, if applicable)
  - The space between markers is proportional to actual days
  - Below the timeline: a runway depletion bar showing remaining stock as a percentage
  - Below that: the 4 output values in a 2x2 grid of compact cards
- **Animation: Pulse.** The runway bar subtly breathes. The reorder date marker gently pulses amber when in warning zone. Risk status indicator has a heartbeat-like glow when critical.
- **Surface: Borderless sections.** No glassmorphism cards. Instead, content sits on subtle background shade shifts — the output zone is slightly lighter (#1a2744), the input zone is slightly darker (#0d1526). A single thin horizontal divider separates them. Feels completely different from MarginRadar's frosted card aesthetic.
- **Risk status:** Large, bold, color-coded word in the output zone — "SAFE" / "ORDER NOW" / "CRITICAL". Not a small badge. It should be the first thing you read.

**The screenshot test:**
If you put MarginRadar and StockPulse side by side, you should see:
- MarginRadar: Dense, card-heavy, teal, slider-filled, donut chart, glassmorphism
- StockPulse: Open, output-dominated, amber, timeline viz, compact inputs, borderless sections

They should look like siblings, not twins.

### PromoGuard (future)
- Accent: Rose/coral
- Structure: Scenario Builder (2-3 columns to compare discount scenarios)
- Inputs: Segmented controls for discount type + number inputs
- Hero viz: Before/after comparison bars
- Animation: Snap
- Surface: Solid elevated cards (no blur, clean shadows)

---

## DECISION CHECKLIST FOR NEW TOOLS

Before building, fill in:

```
Tool name: _______________
Accent color: _____________ (different from existing tools)
Page structure: ____________ (different from existing tools)
Input treatment: ___________ (different from existing tools)
Hero visualization: ________ (different from existing tools)
Animation personality: _____ (different from existing tools)
Surface treatment: _________ (different from existing tools)
Screenshot test: If I put all tools side-by-side, can I instantly tell this one apart by silhouette alone? YES / NO
```

If you answered NO, change at least 2 more dimensions.

---

## ANTI-PATTERNS (things that make tools look the same)

- ❌ Repeating the "section header → slider → input → sublabel" vertical rhythm from MarginRadar
- ❌ Using glassmorphism cards on every tool
- ❌ Putting all outputs at the bottom below a long form
- ❌ Using the same font sizes and weights for headers across tools
- ❌ Always using the same hero section layout (icon + H1 + subtitle + pills)
- ❌ Making every input a slider — sliders are ONE option among many
- ❌ Copying MarginRadar's spacing and padding values. Each tool can breathe differently.

---

*This is the canonical design system for Mini Tools Lab v3. Shared DNA is minimal. Per-tool personality is maximal. Every tool ships with its own identity from v1. The test is always: "Can I tell the tools apart by silhouette alone?"*
