# Markdown Templates for AI-Assisted Development

A reference repository demonstrating best practices for documentation-as-code in LLM-driven development workflows.

## Why Templates Matter

In an LLM-as-dev world, documentation quality directly impacts productivity. Poor docs translate to wasted tokens, broken inference loops, and repeated iterations. Templates enforce consistency and provide structure that both humans and AI can navigate efficiently.

## Repository Structure

```text
.
├── .cursor/
│   └── rules/           # Agent rules for Cursor IDE
│       └── TEMPLATE.md  # Template for creating new rules
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   └── form.yml     # GitHub issue form template
│   └── PULL_REQUEST_TEMPLATE.md
├── docs/
│   ├── README.md        # Documentation conventions & style guide
│   ├── specs/           # Feature specifications
│   │   ├── TEMPLATE.md  # Spec template
│   │   └── *.md         # Individual feature specs
│   └── trds/            # Technical Requirements Documents
│       ├── TEMPLATE.md  # TRD template
│       └── *.md         # Individual TRDs
└── README.md            # This file
```

## Quick Start

1. **For PRs**: Use `.github/PULL_REQUEST_TEMPLATE.md` automatically
2. **For features**: Copy `docs/specs/TEMPLATE.md` to `docs/specs/your-feature.md`
3. **For architecture**: Copy `docs/trds/TEMPLATE.md` to `docs/trds/your-design.md`
4. **For agent rules**: Copy `.cursor/rules/TEMPLATE.md` to `.cursor/rules/your-rule.mdc`

## Template Philosophy

- **Hierarchical depth**: Keep under 3 levels
- **Section count**: Target 5-6 sections max
- **LLM hints**: Use markdown comments for AI guidance
- **Visualizations**: Prefer diagrams over prose where appropriate
- **Opinionated**: Enforce consistent style ruthlessly

## Tooling Recommendations

- [markdownlint](https://github.com/markdownlint/markdownlint) - Enforce formatting conventions
- [Mermaid.js](https://mermaid.js.org/) - Embed diagrams in markdown
- Preview your docs before merging - broken diagrams erode trust

## License

MIT
