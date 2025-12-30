# Washington Advert

## Overview

Washington Advert is a premium digital marketing agency landing page featuring a cinematic, Washington DC-inspired design aesthetic. The application combines a React frontend with an Express backend, featuring an immersive 3D scroll experience using Three.js, Framer Motion animations, and a contact inquiry system backed by PostgreSQL.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter (lightweight React router)
- **State Management**: TanStack React Query for server state
- **Styling**: Tailwind CSS with CSS variables for theming
- **UI Components**: shadcn/ui (Radix primitives with custom styling)
- **3D Graphics**: Three.js via @react-three/fiber and @react-three/drei
- **Animations**: Framer Motion for scroll-based and UI animations
- **Forms**: React Hook Form with Zod validation

### Backend Architecture
- **Runtime**: Node.js with Express
- **Language**: TypeScript (ESM modules)
- **Database ORM**: Drizzle ORM
- **Database**: PostgreSQL
- **API Design**: REST endpoints with Zod schema validation

### Project Structure
```
├── client/           # React frontend
│   └── src/
│       ├── components/   # UI components (shadcn/ui)
│       ├── hooks/        # Custom React hooks
│       ├── lib/          # Utilities and query client
│       └── pages/        # Page components
├── server/           # Express backend
│   ├── routes.ts     # API route definitions
│   ├── storage.ts    # Database operations
│   └── db.ts         # Database connection
├── shared/           # Shared code between client/server
│   ├── schema.ts     # Drizzle schema + Zod types
│   └── routes.ts     # API contract definitions
└── migrations/       # Drizzle database migrations
```

### Build System
- **Development**: Vite dev server with HMR, proxied through Express
- **Production**: Vite builds static assets, esbuild bundles server code
- **Build Output**: `dist/public/` for client, `dist/index.cjs` for server

### Design System
- **Typography**: Playfair Display (headings) + DM Sans (body)
- **Color Palette**: Deep navy/blue theme inspired by Washington DC architecture
- **Visual Style**: Premium, authoritative, architectural with parallax depth effects

## External Dependencies

### Database
- **PostgreSQL**: Primary data store accessed via `DATABASE_URL` environment variable
- **Drizzle ORM**: Schema management and type-safe queries
- **connect-pg-simple**: Session storage (available but not currently used)

### Third-Party Libraries
- **@react-three/fiber**: React renderer for Three.js 3D scenes
- **@react-three/drei**: Helper components for Three.js (Stars, Float, Camera controls)
- **framer-motion**: Animation library for scroll-triggered effects
- **@tanstack/react-query**: Server state management and caching
- **zod**: Runtime schema validation for API contracts
- **react-hook-form**: Form state management with @hookform/resolvers

### Development Tools
- **Vite**: Frontend build tool and dev server
- **esbuild**: Server bundling for production
- **drizzle-kit**: Database migration tooling
- **TypeScript**: Type checking across the entire codebase