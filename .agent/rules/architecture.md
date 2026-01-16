# Architecture & Directory Structure

## Architecture Pattern: Feature-based (Recommended)

Adopt a **Feature-based** architecture to ensure scalability and maintainability.

- **`src/features/`**: Group code by feature domain (e.g., `auth`, `articles`, `users`).
  - Each feature folder should contain its own `components`, `api`, `model`, `hooks`, etc.
  - Example: `src/features/auth/components/SignInForm.tsx`

## Component Classification

Organize UI components based on their reusability and dependency.

- **`src/components/ui`**: Primitive UI components (buttons, inputs, cards) that are domain-agnostic. (Shadcn UI style)
- **`src/components/common`**: Global domain-specific components shared across the app (e.g., Header, Footer).
- **Feature Components**: Place components specific to a feature within `src/features/<feature-name>/components`.

## Logic & State Management

Separation of concerns is critical.

- **Custom Hooks / Services**: Do not write complex logic directly inside components. Extract them into custom hooks or service functions.
- **Location**:
  - Global logic: `src/lib/` or `src/hooks/`
  - Feature logic: `src/features/<feature-name>/model` (Recommended for stores/context-providers) or `src/features/<feature-name>/hooks`

## Core Folder Structure

- **`/src/routes`**: File-system routing.
- **`/src/lib`**: Utility functions, DB connections.
- **`/src/db`**: Database schema and config.
