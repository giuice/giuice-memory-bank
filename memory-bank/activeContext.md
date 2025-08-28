# Active Context

## Current Project State
Phase: Execution. IP4 v2 Modern Floor Plan — T4_1 and T4_2 completed.

## Recent Actions
- T4_1 SpaceDesignSystem_v2 completed: presence color tokens, motion tokens, base typography/focus styles; Badge presence variants added.
- T4_2 SpaceCardComponent_v2 completed: core card with header, occupancy meter (a11y text + progress bar), AvatarGroup, keyboard interactions, and loading/empty/error states.
- Demo updates in `src/app/(dashboard)/floor-plan-test/components/page.tsx` to showcase states; docs updated in `docs/components/modern-ui-components-guide.md`.

## Next Steps
- T4_3 FloorPlanLayout_v2: container + zones + arrangement
  - Floor container and zones, responsive grid/flex, zone headers, CSS transforms-only approach.

## Dependencies
- UI tokens in `src/app/globals.css` and color mapping in `tailwind.config.ts` are used by Badge, StatusIndicators, ModernSpaceCard.
- Components:
  - `ModernSpaceCard.tsx` depends on `StatusIndicators.tsx`, `AvatarGroup.tsx`, and tokens.
  - `SpaceCard.tsx` is a typed wrapper around `ModernSpaceCard`.

## Potential Issues
- Repo-wide ESLint warnings remain unrelated to T4_1/T4_2; no blocking errors from recent changes.

## Progress Summary
- Tokens and presence variants available and adopted.
- SpaceCard states implemented with a11y and keyboard support; demo and docs in place.

## Environment Notes
- Workspace: e:/Cursos/React/virtual-office

## Known Issues/Limitations
- Some tests fail due to external service/env assumptions (auth/avatar). Out of scope for IP4 UI tasks.

## Technical Notes
- Honors prefers-reduced-motion; motion tokens exposed via CSS variables.
- Occupancy meter uses token colors (`success`, `warning`, `status.busy`) for thresholds.
