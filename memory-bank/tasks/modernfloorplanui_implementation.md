# Modern Floor Plan UI (IP4 v2)

## Overview
Rebuild the Modern Floor Plan UI with a DOM-first approach aligned with Tailwind v4 and Shadcn/UI, removing all Konva dependencies, integrating presence gracefully, and ensuring accessibility and performance.

## Tasks
- [x] T4_1: SpaceDesignSystem_v2 — Define tokens and base styles for Tailwind v4 ✓ DONE
  - [x] 1.1: Colors, radius, shadows, spacing tokens in Tailwind config
    Notes: Mapped color tokens and radius; using Tailwind v4 default shadows/spacing scales (no custom spacing needed).
  - [x] 1.2: Base typography and focus-ring styles
    Notes: Enabled font smoothing and base outline color via CSS variables.
  - [x] 1.3: Status badge variants (online/away/busy/offline)
    Notes: Added `bg-status-*` tokens and Badge variants `online|away|busy|offline`.
  - [x] 1.4: Motion tokens (durations/easings), respect reduced-motion
    Notes: Introduced motion CSS variables and utilities; honors prefers-reduced-motion.
- [ ] T4_2: SpaceCardComponent_v2 — Implement core card with states
## Completion Notes
- Files changed: `src/app/globals.css`, `tailwind.config.ts`, `src/components/ui/badge.tsx`, `src/components/floor-plan/modern/StatusIndicators.tsx`, `src/components/floor-plan/modern/SpaceCard.tsx`, `src/components/floor-plan/modern/ModernSpaceCard.tsx`, `src/components/floor-plan/modern/AvatarGroup.tsx`, docs + demo page.
- The design tokens are now available across modern floor plan components.
- Demo: `src/app/(dashboard)/floor-plan-test/components/page.tsx` shows default, loading, error, and empty states.
  - [x] 2.1: Header (name, type, status badge)
  - [x] 2.2: Occupancy (capacity/current) with accessible text and meter
  - [x] 2.3: AvatarGroup with presence states + overflow handling
  - [x] 2.4: Interactions (hover, focus, active) with keyboard support
  - [x] 2.5: Loading/empty/error states
- [ ] T4_3: FloorPlanLayout_v2 — Build container + zones + arrangement
  - [ ] 3.1: Floor container and sections (zones)
  - [ ] 3.2: Simple grid/flex layout; container queries for responsiveness
  - [ ] 3.3: Zone headers and grouping semantics
  - [ ] 3.4: No Konva; CSS transforms only
- [ ] T4_4: AnimationsTransitions_v2 — Add motion system and preferences
  - [ ] 4.1: Entry/exit transitions (opacity/transform)
  - [ ] 4.2: Staggered appearance for cards; disable when reduced-motion
  - [ ] 4.3: Micro-interactions (hover/press) tuned for performance
- [ ] T4_5: ResponsiveAdaptation_v2 — Ensure breakpoints and mobile ergonomics
  - [ ] 5.1: Mobile card condensation and touch targets
  - [ ] 5.2: Tablet/Desktop layout scaling and density
  - [ ] 5.3: Orientation handling and min-size guarantees
- [ ] T4_6: KonvaCleanup — Remove deprecated Konva remnants and code paths
  - [ ] 6.1: Static search for Konva imports/usages
  - [ ] 6.2: Delete or refactor any remaining canvas paths
  - [ ] 6.3: Update docs to reflect DOM-only approach

## Dependencies
- Requires: Tailwind v4 config in repo, Shadcn/UI installed
- Blocks: Execution of DOM floor plan until tokens and SpaceCard are ready

## Technical Notes
- You have access to Context7 mcp for any technical and Updated documentation on supabase/supabase auth/shadcn/supabase realtime/tailwind 4.x
- Prefer CSS transforms/transitions, container queries; avoid heavy reflows
- Accessibility: AA contrast; ARIA for status; focus-visible; keyboard nav
- Testing: unit tests for utils/components; visual checks; Lighthouse a11y
- Files to touch: `src/components/floor-plan/modern/*`, Tailwind tokens, docs
