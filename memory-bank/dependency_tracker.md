[DEP_MATRIX_START]
# KEY DEFINITIONS
K1: src/hooks/queries/useSpaces.ts
K2: src/hooks/mutations/useSpaceMutations.ts
K3: src/repositories/interfaces/ISpaceRepository.ts
K4: src/repositories/implementations/supabase/SupabaseSpaceRepository.ts
K5: src/lib/supabase/client.ts
K6: src/types/database.ts
K7: src/components/floor-plan
K8: src/api/spaces
K9: src/providers/QueryProvider.tsx
K10: src/hooks/useLastSpace.ts
K11: src/utils/debug-logger.ts
K12: src/components/floor-plan/space-debug-panel.tsx
K13: src/components/floor-plan/room-templates.tsx
K14: src/components/floor-plan/dom-floor-plan.tsx
K15: src/components/ui
K16: src/components/floor-plan/modern/SpaceCard.tsx

# MATRIX (Row depends on Column)
# Symbols: > (depends on), < (depended by), x (mutual), - (none), d (doc)
    | K1 | K2 | K3 | K4 | K5 | K6 | K7 | K8 | K9 | K10| K11| K12| K13| K14| K15| K16|
K1  | -  | -  | >  | >  | -  | >  | -  | -  | -  | -  | -  | -  | -  | -  | -  | -  |
K2  | -  | -  | -  | -  | -  | >  | >  | >  | -  | -  | -  | -  | -  | -  | -  | -  |
K3  | <  | -  | -  | <  | -  | >  | -  | -  | -  | -  | -  | -  | -  | -  | -  | -  |
K4  | <  | -  | >  | -  | >  | >  | -  | -  | -  | -  | -  | -  | -  | -  | -  | -  |
K5  | -  | -  | -  | <  | -  | -  | -  | -  | -  | -  | -  | -  | -  | -  | -  | -  |
K6  | <  | <  | <  | <  | -  | -  | <  | <  | -  | -  | -  | -  | -  | -  | -  | -  |
K7  | >  | >  | -  | -  | -  | >  | -  | -  | -  | >  | >  | >  | >  | >  | >  | >  |
K8  | -  | <  | >  | >  | -  | >  | -  | -  | -  | -  | -  | -  | -  | -  | -  | -  |
K9  | <  | <  | -  | -  | -  | -  | -  | -  | -  | -  | -  | -  | -  | -  | -  | -  |
K10 | -  | -  | -  | -  | -  | >  | -  | -  | -  | -  | -  | -  | -  | -  | -  | -  |
K11 | -  | -  | -  | -  | -  | -  | -  | -  | -  | -  | -  | -  | -  | -  | -  | -  |
K12 | -  | -  | -  | -  | -  | >  | -  | -  | -  | -  | >  | -  | -  | -  | >  | -  |
K13 | -  | -  | -  | -  | -  | >  | -  | -  | -  | -  | -  | -  | -  | -  | >  | -  |
K14 | -  | -  | -  | -  | -  | >  | -  | -  | -  | -  | -  | -  | -  | -  | >  | -  |
K15 | <  | -  | -  | -  | -  | -  | <  | -  | -  | -  | -  | <  | <  | <  | -  | -  |
K16 | -  | -  | -  | -  | -  | >  | <  | -  | -  | -  | -  | -  | -  | -  | <  | -  |
[DEP_MATRIX_END]

Additional Docs Links:
- K16: src/components/floor-plan/modern/designTokens.ts (docs depend on this)
- K17: docs/components/modern-ui-components-guide.md (documents tokens and guidelines)
 - K18: src/components/floor-plan/modern/ModernSpaceCard.tsx (depends on K16, K15, StatusIndicators, AvatarGroup)
 - K19: src/components/floor-plan/modern/StatusIndicators.tsx (depends on K15 tokens and Badge variants)
 - K20: src/components/floor-plan/modern/AvatarGroup.tsx (depends on ModernUserAvatar)

Direct Dependencies (new):
- ModernSpaceCard.tsx → depends on → StatusIndicators.tsx
- ModernSpaceCard.tsx → depends on → AvatarGroup.tsx
- ModernSpaceCard.tsx → depends on → designTokens.ts
- ModernSpaceCard.tsx → depends on → src/components/ui/badge.tsx
- StatusIndicators.tsx → depends on → src/components/ui/badge.tsx
- StatusIndicators.tsx → depends on → designTokens.ts
- AvatarGroup.tsx → depends on → ModernUserAvatar.tsx
