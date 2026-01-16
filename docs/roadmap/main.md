# NowLedge Roadmap

This document outlines the high-level roadmap for the development of NowLedge. The focus is on iterative delivery, starting with a strong foundation and moving towards a feature-rich platform.

## Phase 1: Foundation & Infrastructure
**Goal:** Establish a stable and scalable development environment and core backend services.

- **Project Initialization**: Setup SolidStart with Bun and TypeScript.
- **Design System Setup**: Configure Tailwind CSS v4 and integrate Shadcn Solid.
- **Database Schema**: Design and implement initial schema in Neon using Drizzle ORM.
- **Authentication**: Implement secure signup/login flows using Better Auth (GitHub/Google providers).
- **Type Safety Pipeline**: Setup oRPC for end-to-end type safety between frontend and backend.

## Phase 2: Core Content Experience (MVP Scope)
**Goal:** Enable users to create and consume content effectively.

- **Markdown Editor**: Build a distraction-free editor with live preview and syntax highlighting.
- **Article Rendering**: Implement high-performance rendering of articles with SSR.
- **Content Management**: Basic CRUD operations for articles (Create, Read, Update, Delete).
- **Media Handling**: Implement image upload and hosting logic.
- **User Profiles**: Create user profile pages displaying basic info and user's articles.

## Phase 3: Discovery & Engagement
**Goal:** Foster a community and help users find relevant content.

- **Home Feed Algorithm**: Implement the "Freshness" sorting logic for the main feed.
- **Tagging System**: Allow categorization of articles to improve discoverability.
- **Interactions**: Add "Like" and "Stock" (bookmark) features.
- **Search**: Implement efficient keyword and tag-based search functionality.

## Phase 4: Polish & Launch Readiness
**Goal:** Ensure the platform is production-ready, performant, and accessible.

- **SEO Optimization**: Fine-tune meta tags, sitemaps, and SSR for maximum visibility.
- **Performance Tuning**: optimize hydration and minimize comprehensive layout shifts (CLS).
- **UI/UX Refinement**: Add micro-interactions, smooth transitions, and ensure mobile responsiveness.
- **Accessibility Audit**: Verify keyboard navigation and semantic HTML compliance.
- **Beta Launch**: Deploy to production environment (e.g., Cloudflare Workers/Pages) and open for initial users.

---

*Note: This roadmap is subject to change based on user feedback and technical challenges encountered during development.*
