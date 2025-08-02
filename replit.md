# Overview

CourtEase is a full-stack court booking platform that connects sports facility owners with customers looking to book courts for various sports. The application allows owners to list their courts and customers to search, book, and review facilities. Built with a modern React frontend and Express.js backend, it uses PostgreSQL for data persistence and implements session-based authentication.

# User Preferences

Preferred communication style: Simple, everyday language.

Color scheme: Blue and neon green instead of orange (updated August 2, 2025)
- Primary color: Blue (hsl(219, 85%, 46%))
- Secondary/Accent color: Neon green (hsl(142, 76%, 36%))
- Hero gradient updated from orange to blue-green

Demo data: Added 6 sample courts with realistic pricing and amenities to showcase booking functionality

# System Architecture

## Frontend Architecture
The client is built using React with TypeScript and follows a component-based architecture:
- **UI Framework**: Vite for development and building, with React 18
- **Styling**: Tailwind CSS with shadcn/ui component library for consistent design
- **Routing**: Wouter for lightweight client-side routing
- **State Management**: TanStack Query (React Query) for server state management
- **Form Handling**: React Hook Form with Zod validation
- **Authentication**: Context-based auth provider with protected routes

## Backend Architecture
The server follows a RESTful API design with Express.js:
- **Framework**: Express.js with TypeScript support
- **Authentication**: Passport.js with local strategy and session-based auth
- **Session Management**: Express sessions with PostgreSQL session store
- **Password Security**: Node.js crypto with scrypt for secure password hashing
- **API Structure**: Organized routes for courts, bookings, users, and reviews
- **Middleware**: Request logging, JSON parsing, and error handling

## Database Design
Uses PostgreSQL with Drizzle ORM for type-safe database operations:
- **Users Table**: Stores customer and owner accounts with role-based access
- **Courts Table**: Contains court information, pricing, amenities, and owner relationships
- **Bookings Table**: Manages reservation data with status tracking
- **Reviews Table**: Customer feedback and ratings system
- **Availability Table**: Court scheduling and time slot management

## Key Design Patterns
- **Role-based Access Control**: Separate dashboards and permissions for customers vs owners
- **Protected Routes**: Client-side route protection based on authentication status
- **Query Invalidation**: Automatic cache updates after mutations
- **Form Validation**: Consistent validation using Zod schemas shared between client and server
- **Error Boundaries**: Graceful error handling throughout the application

## Development Workflow
- **TypeScript**: Full type safety across frontend, backend, and shared schemas
- **Hot Reload**: Vite development server with fast refresh
- **Database Migrations**: Drizzle Kit for schema management
- **Build Process**: Separate builds for client (Vite) and server (esbuild)

# External Dependencies

## Database
- **Neon Database**: Serverless PostgreSQL hosting via @neondatabase/serverless
- **Connection Pooling**: Built-in connection management for serverless environments

## UI Components
- **Radix UI**: Headless component primitives for accessibility
- **Tailwind CSS**: Utility-first CSS framework
- **Lucide React**: Icon library for consistent iconography

## Development Tools
- **Replit Integration**: Custom plugins for development environment
- **ESBuild**: Fast bundling for production server builds
- **PostCSS**: CSS processing with Tailwind and Autoprefixer

## Authentication & Security
- **Passport.js**: Authentication middleware with local strategy
- **Express Session**: Session management with PostgreSQL store
- **Connect PG Simple**: PostgreSQL session storage adapter

## Data Management
- **Drizzle ORM**: Type-safe database operations
- **Drizzle Zod**: Schema validation integration
- **TanStack Query**: Server state management and caching