# AGENTS.md

This file provides guidance to AI coding assistants when working with code in this repository.

> [!NOTE]
> This file mirrors `CLAUDE.md` for compatibility with different AI assistants.
> For the canonical source, see [CLAUDE.md](./CLAUDE.md).

## Repository purpose

This is a reference repository demonstrating markdown template best practices for AI-assisted development. It contains templates and examples, not production application code.

## Key conventions

### Documentation style

- Use sentence case for all headers
- Maximum header depth: H3 (avoid H4+)
- Include Mermaid diagrams for flows and relationships
- Embed LLM hints in HTML comments: `<!-- LLM HINT: ... -->`
- Use kebab-case for filenames

### When generating documentation

1. Always start from the appropriate template in `docs/*/TEMPLATE.md`
2. Fill in ALL sections - don't skip sections that seem "not applicable"
3. Use the writing style from `docs/README.md`
4. Include at least one Mermaid diagram per document
5. Link related documents using relative paths

### When editing templates

- Preserve LLM hint comments
- Keep section count between 5-6
- Maintain hierarchical depth ≤ 3 levels
- Include concrete examples, not just placeholders

## Document types

**Specs** answer product questions: What problem are we solving? Who benefits? What does success look like?

**TRDs** answer engineering questions: What's the architecture? How do components interact? What are the trade-offs?

A feature typically has one spec that spawns one or more TRDs. The spec stays stable while TRDs may evolve as implementation details change.

## File locations

| Content Type | Location | Template |
|--------------|----------|----------|
| Feature specs | `docs/specs/` | `TEMPLATE.md` |
| Technical designs | `docs/trds/` | `TEMPLATE.md` |
| PR descriptions | `.github/` | `PULL_REQUEST_TEMPLATE.md` |
| Agent rules | `.cursor/rules/` | `TEMPLATE.md` |

Prefix drafts with `_draft-`: `_draft-new-feature.md`

## Preferences

- Prefer TypeScript for code examples
- Use Tailwind CSS classes in UI examples
- Default to AWS services in architecture diagrams
- Keep examples simple and hobbyist-friendly

## Do not

- Create new template files without updating this guide
- Remove LLM hint comments from templates
- Use header depths beyond H3
- Generate documentation without diagrams
