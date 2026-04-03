# Full Stack House Prompts

Reusable AI agent instructions using [PromptScript](https://getpromptscript.dev).

## Available Modules

| Module | Description |
|--------|-------------|
| `core-workflow` | Plan mode, subagents, verification, self-improvement |
| `code-style` | Clean code, no comments policy, error handling |
| `typescript` | TypeScript best practices (no `any`) |
| `git-commits` | Conventional commits format |
| `opentofu` | Infrastructure as Code (OpenTofu over Terraform) |
| `context7` | Auto-use Context7 for library docs |
| `testing` | Testing patterns and practices |
| `shell-scripts` | Bash script best practices |
| `typescript-fullstack` | Preset: core-workflow + code-style + typescript + git-commits + testing + context7 |

## Usage

In your project's `promptscript.yaml`:

```yaml
registries:
  fullstackhouse:
    url: github.com/fullstackhouse/prompts

targets:
  - claude
```

In your `.promptscript/project.prs`:

```prs
@meta {
  id: "my-project"
  syntax: "1.2.0"
}

@use @fullstackhouse/typescript-fullstack
@use @fullstackhouse/opentofu

@identity {
  """
  Your project description here.
  """
}
```

Then run:

```bash
prs compile
```
