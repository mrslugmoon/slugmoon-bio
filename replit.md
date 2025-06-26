# System Architecture Guide

## Overview

This is a full-stack web application built with React, TypeScript, and Express.js. The application appears to be a personal portfolio/landing page for "Slugmoon," a developer showcasing their work and social connections. The stack includes modern frontend tooling (Vite, TailwindCSS, shadcn/ui) with a Node.js backend and PostgreSQL database integration via Drizzle ORM.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite for fast development and optimized builds
- **Routing**: Wouter for lightweight client-side routing
- **State Management**: TanStack Query (React Query) for server state management
- **Styling**: TailwindCSS with CSS custom properties for theming
- **UI Components**: shadcn/ui component library built on Radix UI primitives
- **Animations**: Framer Motion for smooth animations and transitions

### Backend Architecture
- **Runtime**: Node.js with TypeScript
- **Framework**: Express.js for API server
- **Database ORM**: Drizzle ORM for type-safe database operations
- **Database**: PostgreSQL (configured via Neon serverless)
- **Session Management**: Express sessions with PostgreSQL store (connect-pg-simple)
- **Development**: tsx for TypeScript execution in development

### Data Storage Solutions
- **Primary Database**: PostgreSQL via Neon serverless connection
- **ORM**: Drizzle ORM with zod integration for schema validation
- **Session Store**: PostgreSQL-backed session storage
- **Development Fallback**: In-memory storage implementation for development

## Key Components

### Database Schema
- **Users Table**: Basic user management with id, username, and password fields
- **Schema Definition**: Located in `shared/schema.ts` with Drizzle table definitions
- **Validation**: Zod schemas generated from Drizzle for runtime validation

### Authentication System
- Session-based authentication (infrastructure present but not fully implemented)
- Password storage capability (hashing implementation needed)
- User registration and login endpoints (to be implemented)

### Frontend Components
- **Home Page**: Personal portfolio with animated background, social links, and responsive design
- **404 Page**: Clean error handling for unknown routes
- **UI Library**: Comprehensive component library with consistent theming
- **Responsive Design**: Mobile-first approach with breakpoint management

### API Structure
- RESTful API design with `/api` prefix for all endpoints
- Express middleware for request logging and error handling
- CRUD operations interface defined but not fully implemented
- JSON-based request/response handling

## Data Flow

1. **Client Requests**: Frontend makes API calls using TanStack Query for caching and error handling
2. **API Processing**: Express server handles requests with middleware for logging and error handling
3. **Database Operations**: Drizzle ORM manages database interactions with type safety
4. **Response Handling**: JSON responses with consistent error handling
5. **State Management**: Client-side caching and optimistic updates via React Query

## External Dependencies

### Frontend Dependencies
- **UI Framework**: Radix UI primitives for accessible components
- **Icons**: Lucide React for general icons, React Icons for brand icons
- **Forms**: React Hook Form with resolver integration
- **Date Handling**: date-fns for date manipulation
- **Animations**: Framer Motion for enhanced user experience

### Backend Dependencies
- **Database**: Neon PostgreSQL serverless database
- **Session Management**: PostgreSQL-based session store
- **Build Tools**: esbuild for production builds, tsx for development

### Development Tools
- **TypeScript**: Full type safety across the stack
- **ESLint/Prettier**: Code quality and formatting (implied by modern setup)
- **Vite Plugins**: Development experience enhancements including error overlay

## Deployment Strategy

### Production Build
- **Frontend**: Vite builds optimized static assets to `dist/public`
- **Backend**: esbuild bundles server code to `dist/index.js`
- **Database**: Migrations managed via Drizzle Kit

### Environment Configuration
- **Database**: Environment variable `DATABASE_URL` required for database connection
- **Sessions**: Production session management via PostgreSQL
- **Static Assets**: Express serves built frontend from `dist/public`

### Replit Integration
- **Modules**: Node.js 20, web development, and PostgreSQL 16
- **Ports**: Application runs on port 5000, exposed externally on port 80
- **Autoscale Deployment**: Configured for automatic scaling on Replit's infrastructure

## Changelog
- June 26, 2025. Initial setup

## User Preferences

Preferred communication style: Simple, everyday language.