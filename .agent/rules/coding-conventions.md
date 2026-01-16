# Coding Conventions

## TypeScript

- **Type Definitions**: Prefer `type` alias over `interface`.
- **Return Types**: Can be omitted if they can be inferred.
- **Any Type**: `any` is strictly prohibited. Use `unknown` or define specific types.

## SolidJS

- **Components**: Use Arrow Functions (`const Component = () => ...`).
- **Props**: **DO NOT destructure props**. Access them directly (e.g., `props.title`) to maintain reactivity.
- **State Management**:
  - Use `createSignal` for primitive values.
  - Use `createStore` for nested objects or arrays.
- **Exports**: Use Named Exports only.

## Styling (Tailwind CSS)

- **Class Order**: Follow `prettier-plugin-tailwindcss`.
- **Arbitrary Values**: Prohibited (e.g., `w-[123px]`). Use only tokens defined in `src/app.css` or Tailwind config.
- **Conditional Styling**: Use `clsx` or `cva`.

## Documentation

- **Language**: English only.
- **JSDoc**: Mandatory for public functions and complex logic.

## Formatting & Imports

- **Formatter**: `oxfmt` (Follows Prettier defaults).
- **Import Order**: Rely on `oxfmt` defaults.

## Linting

- **Linter**: `oxlint` (`bun run lint`)

## Error Handling

- **Minor Errors** (e.g., Form submission failed): Use **Toast** notifications to inform the user without disrupting the UI.
- **Critical Errors** (e.g., 404, 500, App Crash): Use **ErrorBoundary** to catch errors and display a fallback UI (full screen or section-specific).
