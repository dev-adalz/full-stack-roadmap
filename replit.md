# Overview

This is a React-based web application built with Vite as the build tool and bundler. The project appears to be a learning roadmap application for full-stack development, featuring an interactive interface to track progress through different technology phases. It uses modern frontend technologies and is configured for rapid development on Replit.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Framework

**Technology Stack:** React 18.2.0 with Vite 5.0.0

**Rationale:** 
- Vite provides extremely fast Hot Module Reloading (HMR) for rapid development
- React offers a component-based architecture ideal for interactive UI elements
- The combination enables modern development practices with minimal configuration

**Key Features:**
- TypeScript support configured but using JSX files (easy migration path available)
- Single Page Application (SPA) architecture
- Component-based UI with state management using React hooks

## Styling Architecture

**Technology Stack:** Tailwind CSS v4 with Vite Plugin

**Rationale:**
- Utility-first CSS framework enables rapid UI development
- Tailwind v4 Vite plugin (@tailwindcss/vite) provides optimal performance with automatic content detection
- CSS-first configuration eliminates need for JavaScript config files
- Modern approach with better performance and simpler setup

**Implementation:**
- Tailwind integrated via @tailwindcss/vite plugin
- Global styles imported in App.css using @import "tailwindcss"
- No tailwind.config.js or postcss.config.js required with v4
- Responsive design and dark mode capabilities built-in

## Build System

**Technology Stack:** Vite 5.0.0 with React Plugin

**Configuration Decisions:**
- Development server configured to run on host 0.0.0.0, port 5000 (Replit-optimized)
- ESNext target for modern JavaScript features
- Module system using ES Modules (type: "module" in package.json)
- React plugin with Fast Refresh for instant updates during development

**Build Scripts:**
- `dev`: Development server with HMR
- `build`: Production build with optimizations
- `preview`: Preview production build locally

## Component Architecture

**Application Structure:**
- Main component: FullStackRoadmap - Interactive learning roadmap for full-stack development
- 9 learning phases covering Foundation through Advanced Topics
- Features expandable/collapsible phases with nested learning nodes
- State management using React useState hooks
- Icon system powered by lucide-react for visual hierarchy
- Progress tracking with Set-based data structure for completed nodes

**Design Patterns:**
- Functional components with hooks
- Local state management (no global state library)
- Nested data structure for roadmap phases with prerequisites
- Progressive unlocking system - phases unlock when prerequisites complete
- Visual feedback with Tailwind gradients, animations, and hover effects

## TypeScript Configuration

**Current State:** Configured but not enforced

**Setup:**
- TypeScript 5.2.2 installed as dev dependency
- tsconfig.json configured for React with JSX support
- Strict mode enabled in compiler options
- Easy migration path: rename .jsx to .tsx files

**Rationale:** Provides optional type safety while maintaining JavaScript flexibility for rapid prototyping

# External Dependencies

## UI Libraries

**lucide-react (0.545.0):**
- Purpose: Icon library for visual elements
- Usage: Phase icons, status indicators (CheckCircle, Circle, Lock, etc.)
- Integration: Direct React component imports

## Styling Dependencies

**Tailwind CSS Ecosystem:**
- @tailwindcss/vite: Modern Vite integration plugin for Tailwind v4
- tailwindcss: Core framework with CSS-first configuration

## Development Tools

**React Development:**
- @types/react (18.2.37): TypeScript definitions
- @types/react-dom (18.2.15): TypeScript definitions for React DOM
- @vitejs/plugin-react (4.2.0): Official Vite plugin for React with Fast Refresh

## Hosting Platform

**Replit:**
- Server configured for Replit's networking requirements (0.0.0.0 host binding)
- Port 5000 for web preview
- Development-focused deployment (runs `dev` script by default)

## No Backend/Database

**Current Architecture:**
- Frontend-only application
- No API endpoints or server-side logic
- No database integration
- State persists only in browser memory (localStorage could be added for persistence)

**Future Considerations:**
- Application structure suggests potential for backend integration (roadmap progress tracking)
- Could integrate with authentication systems for user-specific progress
- Potential for API endpoints to save/sync roadmap progress across devices