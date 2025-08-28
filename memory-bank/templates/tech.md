# Technical Stack & Guidelines

## Core Technologies
- **Framework**: Next.js 15.3.0 with App Router and TypeScript 5
- **Database**: Supabase (PostgreSQL) with real-time subscriptions
- **Authentication**: Supabase Auth
- **Styling**: TailwindCSS 4.1.3 + Shadcn/UI components
- **State Management**: TanStack Query v5 + React Context
- **Real-time**: Supabase Realtime + Socket.IO
- **Testing**: Vitest + Playwright + Testing Library

## Key Libraries
- **UI Components**: Radix UI primitives via Shadcn/UI
- **Icons**: Lucide React
- **Date Handling**: date-fns v4
- **Utilities**: clsx, tailwind-merge, class-variance-authority
- **Canvas**: React Zoom Pan Pinch for interactive floor plans
- **Notifications**: Sonner for toast messages

## Architecture Patterns
- **Repository Pattern**: Data access abstraction in `src/repositories/`
- **Context + Hooks**: State management with custom hooks
- **Server Components**: Next.js optimization for initial loads
- **Atomic Design**: Component organization by complexity

## Common Commands
```bash
# Development
npm run dev              # Start dev server with Turbopack
npm run build           # Production build
npm run start           # Start production server

# Testing
npm run test            # Run Vitest unit tests
npm run test:watch      # Watch mode for unit tests
npm run test:ui         # Vitest UI interface
npm run test:api        # Run Playwright API tests
npm run test:all        # Run all tests sequentially

# Code Quality
npm run lint            # ESLint check
```

## Database Strategy
- **Primary**: Supabase PostgreSQL with Row Level Security (RLS)
- **Real-time**: Supabase Realtime for live updates
- **Schema**: Company-based multi-tenancy with proper isolation
- **Migrations**: SQL files in `src/migrations/`
**IMPORTANT** When user choose to sign up with username/password we are using supabase auth, and we have a trigger that inserts the user on 'Users' table.
```sql
CREATE OR REPLACE FUNCTION public.handle_new_user()
RETURNS TRIGGER
LANGUAGE plpgsql
SECURITY DEFINER
SET search_path = public
AS $$
BEGIN
  -- Insert into public.users, letting 'id' default, and setting 'supabase_uid'
  INSERT INTO public.users (supabase_uid, email, display_name, role, status, preferences, avatar_url)
VALUES ( NEW.id,
         NEW.email,
         COALESCE(NEW.raw_user_meta_data->>'displayName', NEW.email),
         'member',
         'online',
         '{"theme":"light","notifications":true}',
         NEW.raw_user_meta_data->>'avatar_url')
ON CONFLICT (supabase_uid) DO NOTHING;

  RETURN NEW;
END;
$$;

-- Trigger to call the function after a new user is created in auth.users
DROP TRIGGER IF EXISTS on_auth_user_created ON auth.users;

CREATE TRIGGER on_auth_user_created
  AFTER INSERT ON auth.users
  FOR EACH ROW EXECUTE FUNCTION public.handle_new_user();
```

## Performance Considerations
- Server Components for initial page loads
- TanStack Query for client-side caching
- Image optimization with Next.js
- Tailwind CSS optimization and purging