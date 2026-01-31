# Monorepo

A TypeScript monorepo powered by Turborepo for managing shared packages and configurations.

## What's inside?

This monorepo includes the following packages:

### Packages

- `@repo/ui`: React component library with Button, Card, and Code components
- `@repo/shared`: Shared TypeScript types and utilities
- `@repo/eslint-config`: Shared ESLint configurations (base, Next.js, React)
- `@repo/typescript-config`: Shared TypeScript configurations

Each package is 100% [TypeScript](https://www.typescriptlang.org/).

## Project Structure

```
monorepo/
├── packages/
│   ├── ui/                  # React component library
│   ├── shared/              # Shared types and utilities
│   ├── eslint-config/       # ESLint configurations
│   └── typescript-config/   # TypeScript configurations
├── package.json             # Root workspace configuration
├── turbo.json              # Turborepo configuration
└── tsconfig.json           # Root TypeScript config
```

## Tech Stack

- **Build System**: [Turborepo](https://turbo.build/repo) - High-performance build system for monorepos
- **Language**: [TypeScript](https://www.typescriptlang.org/) 5.7.3 - Static type checking
- **UI Framework**: [React](https://react.dev/) 19.0.0 - Component library
- **Linting**: [ESLint](https://eslint.org/) 9.19.0 - Code quality
- **Formatting**: [Prettier](https://prettier.io) 3.5.1 - Code formatting
- **Package Manager**: npm 6.14.13
- **Node Version**: >= 18

## Getting Started

### Installation

```bash
npm install
```

### Build

Build all packages:

```bash
npm run build
```

This will compile TypeScript to JavaScript in each package's `dist/` directory.

### Development

Run type checking across all packages:

```bash
npm run check-types
```

### Linting

Run ESLint on all packages:

```bash
npm run lint
```

### Formatting

Format all code with Prettier:

```bash
npm run format
```

## Package Commands

### @repo/ui

```bash
# Build the component library
npm run build --workspace=@repo/ui

# Type check
npm run check-types --workspace=@repo/ui

# Lint
npm run lint --workspace=@repo/ui

# Clean build artifacts
npm run clean --workspace=@repo/ui

# Generate a new component
npm run generate:component --workspace=@repo/ui
```

### @repo/shared

```bash
# Build shared types
npm run build --workspace=@repo/shared

# Type check
npm run check-types --workspace=@repo/shared

# Clean build artifacts
npm run clean --workspace=@repo/shared
```

## Available Scripts

- `npm run build` - Build all packages
- `npm run check-types` - Type check all packages
- `npm run lint` - Lint all packages
- `npm run format` - Format all files with Prettier
- `npm run dev` - Run development mode (Turbo)

## Using Packages

### Using @repo/ui Components

```typescript
import { Button } from "@repo/ui/button";
import { Card } from "@repo/ui/card";
import { Code } from "@repo/ui/code";

function App() {
  return (
    <Card href="https://example.com">
      <Button appName="My App">Click me</Button>
      <Code>console.log("Hello World")</Code>
    </Card>
  );
}
```

### Using @repo/shared Types

```typescript
import { User } from "@repo/shared";

const user: User = {
  id: "1",
  name: "John Doe",
  email: "john@example.com",
  role: "admin",
};
```

## Build Output

All packages build to a `dist/` directory:

```
packages/
├── ui/
│   ├── src/           # TypeScript source files
│   └── dist/          # Compiled JavaScript + type definitions
├── shared/
│   ├── src/           # TypeScript source files
│   └── dist/          # Compiled JavaScript + type definitions
```

The `dist/` directories are ignored by git and generated during build.

## Turborepo

This monorepo uses Turborepo for efficient task execution with caching.

### Remote Caching

Turborepo can use [Remote Caching](https://turbo.build/repo/docs/core-concepts/remote-caching) to share cache artifacts across machines.

To enable Remote Caching:

```bash
npx turbo login
npx turbo link
```

## Useful Links

Learn more about Turborepo:

- [Tasks](https://turbo.build/repo/docs/core-concepts/monorepos/running-tasks)
- [Caching](https://turbo.build/repo/docs/core-concepts/caching)
- [Remote Caching](https://turbo.build/repo/docs/core-concepts/remote-caching)
- [Configuration Options](https://turbo.build/repo/docs/reference/configuration)
- [CLI Usage](https://turbo.build/repo/docs/reference/command-line-reference)
