This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/app/building-your-application/optimizing/fonts) to automatically optimize and load [Geist](https://vercel.com/font), a new font family for Vercel.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/app/building-your-application/deploying) for more details.

## Git Commit Guidelines

This project enforces the **Conventional Commits** specification using Husky and Commitlint. If your commit message does not match the required format, the commit will automatically be blocked.

### Message Format

Every commit message must follow this structure:

```text
type(scope?): subject
```

### Examples

- **Adding a feature:** `feat(auth): add google OAuth login`
- **Fixing a bug:** `fix(ui): resolve navbar responsive alignment`
- **Configuration / Tooling:** `chore: update husky hook directories`
- **Documentation:** `docs: update setup steps in readme`

### Allowed Commit Types

- **`feat`**: A new feature for the application.
- **`fix`**: A bug fix.
- **`chore`**: Changes to the build process, tooling, or auxiliary libraries (like updating packages).
- **`docs`**: Documentation-only changes.
- **`style`**: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons).
- **`refactor`**: A code change that neither fixes a bug nor adds a feature.
- **`perf`**: A code change that improves performance.
- **`test`**: Adding missing tests or correcting existing tests.
- **`ci`**: Changes to CI configuration files and scripts.

## Project Structure

The project is structured as a monolithic repository containing our core application configurations and source code. Below is an overview of the main directories and their purposes:

```text
saas-boilerplate/
├── .husky/                  # Git hooks for automated pre-commit linting
├── saas-boilerplate/        # Core Next.js application workspace
│   ├── public/              # Static assets (images, icons, fonts)
│   ├── src/                 # Application source code
│   │   ├── app/             # Next.js App Router (pages, layouts, API routes)
│   │   ├── components/      # Reusable UI components (buttons, inputs, modals)
│   │   ├── hooks/           # Custom React hooks
│   │   ├── lib/             # Core utilities, database clients, SDK integrations
│   │   ├── styles/          # Global styles and Tailwind configurations
│   │   └── types/           # Shared TypeScript interfaces and types
│   ├── eslint.config.mjs    # ESLint flat configuration (ESM layout)
│   ├── next.config.ts       # Next.js framework configuration
│   ├── package.json         # Inner app workspace dependencies
│   └── tsconfig.json        # TypeScript compilation settings
├── .gitignore               # Root git exclusions (node_modules, environment variables)
└── package.json             # Root monorepo configuration
```

### Directory Breakdown

- **`src/app/`**: Utilizes Next.js App Router syntax. Contains layouts, pages, loading states, and error handling wrappers grouped by route groups or functional domains.
- **`src/components/`**: House for design system atoms, molecules, and organisms. Strictly decoupled from specific route contexts to remain completely reusable.
- **`src/lib/`**: Central initialization point for external services, database drivers (Prisma/Drizzle), authentication routines (NextAuth/Clerk), and payment gateways (Stripe).
