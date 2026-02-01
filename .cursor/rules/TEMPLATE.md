# Agent rules template

> [!NOTE]
> **Template rules:**
> - Copy this to a `.mdc` file and customize for your use case
> - Remove blockquoted guidance before publishing
> - Keep HTML comments (LLM hints) for AI assistants
> - Include both good and bad examples

<!--
LLM HINT: This template creates Cursor rules (.mdc files).
Rules should be specific, actionable, and scoped appropriately.
Copy this to a .mdc file and customize for your use case.
-->

> This template helps you create consistent Cursor rules. Copy to `.cursor/rules/your-rule.mdc` and fill in the sections.

---

## Rule structure

> Use this structure for all rules. The frontmatter controls when the rule applies.

```markdown
---
description: [Brief description of when this rule applies]
globs: [File patterns this rule applies to, e.g., "src/**/*.ts"]
alwaysApply: [true if this should always be active, false if conditional]
---

# [Rule Name]

[Concise description of what this rule enforces or guides]

## Guidelines

- [Specific guideline 1]
- [Specific guideline 2]
- [Specific guideline 3]

## Examples

### Do this

\`\`\`typescript
// Good example
\`\`\`

### Don't do this

\`\`\`typescript
// Bad example
\`\`\`

## Context

[Any additional context the LLM needs to apply this rule correctly]
```

---

## Example rules

### TypeScript style rule

```markdown
---
description: TypeScript code style and conventions
globs: "**/*.{ts,tsx}"
alwaysApply: true
---

# TypeScript conventions

Follow these conventions for all TypeScript code.

## Guidelines

- Use explicit return types on exported functions
- Prefer `interface` over `type` for object shapes
- Use `const` assertions for literal types
- Avoid `any` - use `unknown` and narrow with type guards

## Examples

### Do this

\`\`\`typescript
export function calculateTotal(items: Item[]): number {
  return items.reduce((sum, item) => sum + item.price, 0);
}
\`\`\`

### Don't do this

\`\`\`typescript
export function calculateTotal(items) {
  return items.reduce((sum, item) => sum + item.price, 0);
}
\`\`\`
```

### React component rule

```markdown
---
description: React component patterns and best practices
globs: "src/components/**/*.tsx"
alwaysApply: false
---

# React component patterns

Guidelines for building React components in this project.

## Guidelines

- Use functional components with hooks
- Colocate styles with components using Tailwind
- Extract reusable logic into custom hooks
- Prefer composition over prop drilling

## Component structure

\`\`\`tsx
// Imports
import { useState } from 'react';

// Types
interface Props {
  title: string;
  onAction: () => void;
}

// Component
export function MyComponent({ title, onAction }: Props) {
  const [state, setState] = useState(false);

  return (
    <div className="p-4">
      <h1>{title}</h1>
      <button onClick={onAction}>Action</button>
    </div>
  );
}
```

### Documentation rule

```markdown
---
description: Documentation standards for markdown files
globs: "docs/**/*.md"
alwaysApply: true
---

# Documentation standards

Enforce consistent documentation across the project.

## Guidelines

- Use sentence case for headers
- Include LLM hints in HTML comments
- Maximum header depth: H3
- All diagrams must use Mermaid.js
- Test diagram rendering before committing

## Diagram example

\`\`\`mermaid
graph LR
    A[Start] --> B[Process]
    B --> C[End]
\`\`\`
```

---

## Tips for effective rules

> Remove this section when creating your actual rule file.

1. **Be specific**: Vague rules lead to inconsistent application
2. **Include examples**: Show both good and bad patterns
3. **Scope appropriately**: Use globs to limit where rules apply
4. **Keep it short**: Long rules get ignored or misapplied
5. **Update regularly**: Rules should evolve with the codebase
