# Full Stack House Prompts

Reusable AI agent instructions using [PromptScript](https://getpromptscript.dev).

## Packages

| Package | Description |
|---------|-------------|
| `@fullstackhouse/core-workflow` | Plan mode, subagents, verification, self-improvement |
| `@fullstackhouse/code-style` | Clean code, no comments policy, error handling |
| `@fullstackhouse/typescript` | TypeScript best practices (no `any`) |
| `@fullstackhouse/git-commits` | Conventional commits format |
| `@fullstackhouse/opentofu` | Infrastructure as Code (OpenTofu over Terraform) |
| `@fullstackhouse/context7` | Auto-use Context7 for library docs |
| `@fullstackhouse/testing` | Testing patterns and practices |
| `@fullstackhouse/shell-scripts` | Bash script best practices |

## Presets

| Preset | Includes |
|--------|----------|
| `@fullstackhouse/typescript-fullstack` | core-workflow + code-style + typescript + git-commits + testing + context7 |

## Usage

### In a project's `.prs` file

```prs
@meta {
  id: "my-project"
  syntax: "1.0.0"
}

@use @fullstackhouse/typescript-fullstack
@use @fullstackhouse/opentofu

# Project-specific standards below
@standards {
  framework: [
    "Use NestJS for backend",
    "Use Next.js for frontend"
  ]
}
```

### Compile to CLAUDE.md

```bash
prs compile
```

This generates tool-specific config files including `CLAUDE.md`.

## Development

```bash
# Install PromptScript CLI
npm install -g promptscript

# Validate packages
prs validate

# Compile all packages
prs compile
```

## Adding New Packages

1. Create directory under `packages/`
2. Add `index.prs` with `@meta`, `@standards`, `@identity` sections
3. Update `promptscript.yaml` to include new package
4. Run `prs validate` to check syntax
