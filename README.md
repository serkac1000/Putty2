# PuTTY Script Generator

## Overview

A web-based utility tool for IT professionals and network administrators to generate batch scripts that automate SSH commands across multiple devices using PuTTY. The application provides a clean form interface for inputting credentials, IP addresses, and commands, then generates downloadable batch scripts and command files for executing SSH operations on multiple devices simultaneously.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture

**Framework & Tooling**
- **React 18** with TypeScript for type-safe component development
- **Vite** as the build tool and development server for fast HMR (Hot Module Replacement)
- **Wouter** for lightweight client-side routing
- **TanStack Query** for server state management and data fetching

**UI Design System**
- **Shadcn/ui** component library based on Radix UI primitives
- **Tailwind CSS** for utility-first styling with custom design tokens
- **Material Design principles** adapted for developer tools with focus on clarity and efficiency
- Dark mode as primary theme with light mode support via theme provider
- Custom color palette optimized for dark/light modes with neutral base colors

**State Management**
- Local browser storage (localStorage) for persisting user settings
- React hooks for component-level state
- Form state managed through React Hook Form with Zod validation

**Key Design Decisions**
- Component composition using Radix UI primitives for accessibility and customization
- Utility-focused design prioritizing speed and clarity over visual flair
- Monospace fonts (JetBrains Mono) for code/script display
- Responsive layout with mobile-first approach

### Backend Architecture

**Server Framework**
- **Express.js** on Node.js for HTTP server
- **TypeScript** throughout the stack for type safety
- **ESM modules** (type: "module") for modern JavaScript patterns

**Development Setup**
- Custom Vite integration in development mode for SSR-like development experience
- Static file serving in production mode
- Separation of concerns: Vite handles frontend, Express handles API routes

**API Structure**
- RESTful API pattern with `/api` prefix for all backend routes
- Request/response logging middleware for debugging
- Error handling middleware with standardized error responses
- No authentication currently implemented (storage layer has user schema but unused)

**Script Generation Logic**
- Client-side script generation (no server processing required)
- Batch script templates for Windows PuTTY automation
- IP address parsing supporting ranges and CIDR notation
- Command sequencing with error handling and logging

### Data Storage Solutions

**Current Implementation**
- **In-memory storage** using Map data structure for user data (unused in current app)
- **LocalStorage** for client-side persistence of form settings
- Schema defined with Drizzle ORM but not actively used

**Database Configuration**
- **Drizzle ORM** configured with PostgreSQL dialect
- **Neon Database** serverless Postgres driver included
- Migration system configured but not currently utilized
- Schema defines users table with UUID primary keys

**Storage Interface Pattern**
- Abstract `IStorage` interface for potential future database integration
- `MemStorage` class implements interface for in-memory operations
- Easy migration path to PostgreSQL by implementing storage interface

### External Dependencies

**UI Component Libraries**
- **Radix UI** primitives (accordion, alert-dialog, checkbox, dialog, dropdown-menu, select, tabs, toast, tooltip, etc.)
- **Lucide React** for consistent iconography
- **cmdk** for command palette functionality
- **embla-carousel-react** for carousel components
- **react-day-picker** for date selection
- **vaul** for drawer components

**Form & Validation**
- **React Hook Form** for form state management
- **Zod** for schema validation
- **@hookform/resolvers** for Zod integration with React Hook Form
- **drizzle-zod** for generating Zod schemas from Drizzle tables

**Styling & Theming**
- **Tailwind CSS** with PostCSS and Autoprefixer
- **class-variance-authority** for variant-based component styling
- **tailwind-merge** and **clsx** for conditional class merging

**Development Tools**
- **@replit/vite-plugin-runtime-error-modal** for error overlays in development
- **@replit/vite-plugin-cartographer** for Replit-specific tooling
- **@replit/vite-plugin-dev-banner** for development environment indicators

**Database & ORM**
- **Drizzle ORM** for type-safe database operations
- **@neondatabase/serverless** for serverless Postgres connections
- **drizzle-kit** for migrations and schema management
- **connect-pg-simple** for PostgreSQL session store (configured but unused)

**Utilities**
- **date-fns** for date manipulation
- **nanoid** for generating unique IDs

**Build & Runtime**
- **esbuild** for backend bundling in production
- **tsx** for TypeScript execution in development
- **@vitejs/plugin-react** for React Fast Refresh# Putty2
