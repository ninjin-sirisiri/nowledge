# Development Workflow

## Package Manager

- Use **Bun** for all operations (`bun install`, `bun run dev`, `bun run deploy`).

## Git Workflow

### Branching Strategy (GitHub Flow)
- **Main Branch**: `main` (Always deployable/production-ready).
- **Feature Branches**: Create a new branch for every task.
- **Naming Convention**:
  - `feat/feature-name` (New features)
  - `fix/bug-name` (Bug fixes)
  - `docs/topic` (Documentation)
  - `refactor/topic` (Code refactoring)
  - `chore/topic` (Maintenance, config)
  - `test/topic` (Tests)

### Commit Messages
- Use **Conventional Commits** in **English** with **Emojis**.
- **Format**: `<type>: <emoji> <subject>`
- **Types & Emojis**:
  - `feat`: ✨ Feature (New feature)
  - `fix`: 🐛 Fix (Bug fix)
  - `docs`: 📚 Docs (Documentation only)
  - `style`: 💎 Style (Formatting, missing semi colons, etc; no code change)
  - `refactor`: ♻️ Refactor (Refactoring production code)
  - `perf`: 🚀 Perf (Performance improvements)
  - `test`: 🚨 Test (Adding missing tests, refactoring tests)
  - `chore`: 🔧 Chore (Build process, auxiliary tools)

### Pull Requests & Merging
- **Solo Development**: Direct commits/pushes to `main` are allowed for small fixes.
- **Team/Major Features**: Using Pull Requests (PR) is recommended.
- **Merge Strategy**: **Squash and Merge** is recommended to keep the `main` history clean and linear.

### Continuous Integration (CI)
- Ensure the following checks pass before pushing or merging:
  - **Linting**: `bun run lint`
  - **Tests**: `bun run test` (if applicable)

### Versioning
- Follow **Semantic Versioning (SemVer)**: `vMajor.Minor.Patch`
  - **Major**: Incompatible API changes.
  - **Minor**: Backward-compatible functionality.
  - **Patch**: Backward-compatible bug fixes.
- Create git tags for releases (e.g., `v1.0.0`).
