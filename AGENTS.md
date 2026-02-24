# ContractAnalizer – AI Agent Instructions

Project-level guidance for Cursor AI. Domain rules live in `.cursor/rules/`; this file orients the agent and points to the right rules.

## Project Overview

**ContractAnalizer** uses a rule framework for contract analysis workflows, quality standards, ticket management, and development practices.

### Contract Intelligence Agent

When analyzing contracts, agreements, or legal documents, adopt the **Contract Intelligence & Risk Analysis** persona:

- **Prompt**: `@.cursor/prompts/contract-analysis/contract-intelligence-agent.prompt.md`
- **Rule**: `@.cursor/rules/contract-analysis/agent-application-rule.mdc`

Analyze deeply for risks, ambiguities, liabilities, and hidden obligations. Output: Executive Summary, Key Risks, Hidden Issues, Missing Protections, Suggested Improvements, Questions for Clarification. Assume adversarial interpretation; do not give jurisdiction-specific legal advice.

## Rule Framework

Rules are in `.cursor/rules/` as `.mdc` files with YAML front-matter. Use **index** files to navigate domains:

| Domain | Index | When to Use |
|--------|-------|-------------|
| Quality | `.cursor/rules/quality/quality-rules-index.mdc` | Pre-commit validation, diagnostics, zero warnings/errors |
| Git | `.cursor/rules/git/git-rules-index.mdc` | Branching, naming, lifecycle, protection |
| Ticket | `.cursor/rules/ticket/ticket-rules-index.mdc` | Plans, progress, context, completion |
| Rule Authoring | `.cursor/rules/rule-authoring/rule-authoring-overview.mdc` | Creating/updating rules |
| Agile | `.cursor/rules/agile/agent-application-rule.mdc` | Epics, features, user stories |
| Technical Specs | `.cursor/rules/technical-specifications/agent-application-rule.mdc` | Domain docs, entities, specs |
| Contract Analysis | `.cursor/rules/contract-analysis/agent-application-rule.mdc` | Contract risk, liability, clauses, agreements |

## Core Conventions (Always Apply)

1. **Quality**: Zero warnings, zero errors before every commit. Run validation before claiming work done.
2. **Comments**: Use sparingly; focus on the "why" and non-obvious behavior.
3. **Diagnostics**: Errors/warnings must include WHAT, WHY, and HOW.
4. **Code style**: Follow existing project style; prefer descriptive names and modular design.

## Agent Application Rules

For domain-specific work, use the agent-application rules (they describe when and how to apply domain rules):

- Quality: `@.cursor/rules/quality/agent-application-rule.mdc`
- Git: `@.cursor/rules/git/agent-application-rule.mdc`
- Ticket: `@.cursor/rules/ticket/agent-application-rule.mdc`
- Agile: `@.cursor/rules/agile/agent-application-rule.mdc`
- Technical Specs: `@.cursor/rules/technical-specifications/agent-application-rule.mdc`
- Contract Analysis: `@.cursor/rules/contract-analysis/agent-application-rule.mdc`

## Supporting Directories

- **`.cursor/prompts/`** – Reusable prompts
- **`.cursor/templars/`** – Output structure templates
- **`.cursor/exemplars/`** – Good/bad examples (pattern extraction only; do not copy content)
- **`.cursor/scripts/`** – Quality and housekeeping scripts

## Indexing

`.cursorindexingignore` excludes `.specstory/**` from indexing. Use `@` to reference files explicitly when needed.
