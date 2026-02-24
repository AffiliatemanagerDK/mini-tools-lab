# Mini Tools Lab — Design System Prompt

Use this as a persistent instruction for every tool built under mini-tools-lab.vercel.app.
Every new tool MUST follow these rules from the first version.
Do not build "plain" first and style later — ship styled from day one.

---

## IDENTITY & BRAND
- **Parent brand:** NorthGrid Tools / Mini Tools Lab
- **Aesthetic:** "Dark control room" — inspired by Linear, Vercel, Raycast. Technical, precise, premium.
- **Tone:** Professional utility. No fluff. Built for e-commerce operators who make decisions fast.
- **Each tool has its own name** (MarginRadar, StockPulse, PromoGuard, etc.) but shares the same visual system.

## COLOR PALETTE (mandatory)
- **Background:** Deep navy/near-black (`#0B1121` or `#0F172A`). Never white.
- **Card surfaces:** Glassmorphism — `rgba(255,255,255,0.05)` with `backdrop-blur-xl` and `1px border rgba(255,255,255,0.08)`.
- **Primary accent:** Electric teal (`#22D3EE` / `cyan-400`). Used for: slider tracks, active states, primary output numbers, links, focus rings.
- **Positive/Healthy:** Green (`#22C55E`). For: healthy margins, safe stock levels, profitable results.
- **Warning/Tight:** Orange (`#F97316`). For: marginal results, "order soon" states, cost-driver sliders (return rate, discount %).
- **Danger/Loss:** Red (`#EF4444`). For: negative profit, critical stock, break-even violations.
- **Text primary:** White or near-white (`#F1F5F9`).
- **Text secondary:** Muted (`#94A3B8` / slate-400).
- **Text in inputs:** White (`#F1F5F9`) on dark input backgrounds.

## LAYOUT STRUCTURE (every tool)
```
┌─────────────────────────────────┐
│ Logo + Tool Name    Currency ← │ ← Header: logo, name, currency selector, back link
├─────────────────────────────────┤
│ Hero: H1 tagline + subtitle    │ ← 1-2 sentences max
│ [Pill badges: No API, etc.]    │
├─────────────────────────────────┤
│ ┌─────────┐      ┌─────────┐    │ ← On desktop: 2-col grid for calculator cards
│ │ Card 1  │      │ Card 2  │    │   On mobile: stacked
│ │         │      │         │    │
│ └─────────┘      └─────────┘    │
├─────────────────────────────────┤
│ CTA section: "Explore more →"  │ ← Soft cross-sell to other tools
├─────────────────────────────────┤
│ "Built by Mini Tools Lab"      │ ← Footer
├─────────────────────────────────┤
│ ██ Sticky bar: Key outputs ██   │ ← Always visible, even on scroll
│ [Copy results] [Reset]          │
└─────────────────────────────────┘
```

## INPUT FIELDS (every tool)
1. **Slider + number input combo** for every numeric field. Slider on the left, editable number input on the right.
2. **Sublabel under every field** — one sentence explaining what it is, in plain language.
3. **Pre-fill all fields with realistic default values** so the tool shows a live, meaningful result on first load. Never show "-" or empty outputs at page load.
4. **Group related fields** under section headers (uppercase, small, muted text like "REVENUE ASSUMPTIONS", "ORDER ECONOMICS").
5. **Focus state:** Teal glow ring on input fields when focused/tapped.
6. **Touch targets:** Minimum 24px diameter on slider thumbs, 48px height on input fields.
7. **Cost-driver sliders** should use orange/red track color instead of teal.

## OUTPUT DISPLAY (every tool)
1. **Primary output number:** 32-48px font, accent color (teal/green/red depending on health).
2. **Always color-code outputs:** Green/Orange/Red.
3. **Use at least 3 labeled states** with clear thresholds (e.g., Healthy/Tight/Loss or Safe/Order soon/Critical).
4. **Add a visual indicator** (donut/gauge/progress/countdown).
5. **Secondary outputs** in mini-cards with icon + label.
6. **Count-up animation** (300ms) on output numbers when values change.
7. **Differentiate visually** between similar numbers.

## STICKY BOTTOM BAR (every tool)
- Always present.
- Contains 1-2 key outputs + "Copy results" + "Reset".
- Mobile: fixed bottom, always visible.
- Primary metric visually larger.

## HEADER (every tool)
- **Left:** Tool logo + name + one-line subtitle.
- **Right:** Currency selector (DKK/EUR/USD/GBP) + "← Tool Hub".
- Currency selector only for monetary tools.

## PILL BADGES (every tool)
- 🛡️ Privacy-first
- 🌐 100% browser-side
- ⚡ No API cost

## MICRO-INTERACTIONS (every tool)
- Cards fade/slide in on load (stagger 100ms).
- Outputs count-up (300ms ease-out).
- Inputs teal focus glow.
- Critical states subtle pulse.
- Buttons subtle scale/brightness on hover/tap.

## CTA SECTION (every tool)
- Soft cross-sell before footer.
- Teal link or ghost button with clear contrast.

## FOOTER (every tool)
- "Built by Mini Tools Lab" centered, muted, links to hub.

## RESPONSIVE RULES
- Desktop: 2-column where relevant.
- Mobile: stacked cards + sticky bottom bar + large touch targets.

## COMMON MISTAKES TO AVOID
- ❌ No empty outputs on first load.
- ❌ No white backgrounds.
- ❌ No contradictory health labels.
- ❌ No single-color sliders for all inputs.
- ❌ No shipping without sticky bar.
- ❌ No missing currency selector on monetary tools.
- ❌ No default browser-styled inputs.

---

*Every tool ships styled from v1 — no "plain first, style later" phase.*
