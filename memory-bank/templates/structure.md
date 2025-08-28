# Project Structure & Organization

## Source Code Organization
```
src/
├── app/                 # Next.js App Router pages and layouts
│   ├── (auth)/         # Authentication routes (grouped)
│   ├── (dashboard)/    # Main dashboard routes (grouped)
│   ├── api/            # API route handlers
│   └── globals.css     # Global styles
├── components/         # React components
│   ├── ui/             # Shadcn/UI base components
│   ├── dashboard/      # Dashboard-specific components
│   ├── floor-plan/     # Virtual office floor plan components
│   ├── messaging/      # Chat and communication components
│   ├── profile/        # User profile components
│   └── shell/          # Layout and shell components
├── contexts/           # React Context providers
├── hooks/              # Custom React hooks
│   ├── queries/        # TanStack Query hooks
│   ├── mutations/      # Data mutation hooks
│   └── realtime/       # Real-time subscription hooks
├── lib/                # Utility functions and configurations
│   ├── supabase/       # Supabase client and utilities
│   └── auth/           # Authentication utilities
├── repositories/       # Data access layer
│   ├── interfaces/     # Repository interfaces
│   └── implementations/ # Concrete implementations
├── types/              # TypeScript type definitions
└── utils/              # General utility functions
```

## Key Directories

### `/app` - Next.js App Router
- Route groups with parentheses for organization
- API routes in `/api` directory
- Server components by default

### `/components` - UI Components
- **ui/**: Base Shadcn/UI components (Button, Dialog, etc.)
- **Feature folders**: Organized by application domain
- **shell/**: Layout and navigation components

### `/contexts` - State Management
- React Context providers for global state
- Each context has corresponding custom hook

### `/hooks` - Custom Hooks
- **queries/**: Data fetching with TanStack Query
- **mutations/**: Data updates and mutations
- **realtime/**: Supabase real-time subscriptions

### `/repositories` - Data Access
- Interface-based repository pattern
- Abstracts database implementation details
- Enables easy testing and database switching

## Naming Conventions
- **Files**: kebab-case for components, camelCase for utilities
- **Components**: PascalCase React components
- **Hooks**: camelCase starting with "use"
- **Types**: PascalCase interfaces and types
- **Constants**: UPPER_SNAKE_CASE

## Import Patterns
- Use `@/` alias for src imports
- Group imports: external → internal → relative
- Prefer named exports over default exports

## Component Organization
- One component per file
- Co-locate related components in feature folders
- Separate presentation from business logic
- Use composition over inheritance