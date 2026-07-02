# Spec-Driven Development (AWS/Kiro)

Notes from an AWS talk on spec-driven development (SDD) with AI coding assistants.

## Core Philosophy

- **Clarity before code** — invest time upfront to understand what you're trying to build.
- **Iterative refinement** — iterate and capture the evolution of what you're trying to build.
- **Code via docs** — move from ephemeral chat to persistent documents that can be shared with stakeholders.

## The Workflow: Intent → Steering → Requirements → Design → Tasks

SDD starts with intent and layers structure on top of it before any code is generated.

**1. Start with intent.** As you think about intent, think about what additional *context* you need to bring in — technical and domain knowledge. Context can be managed dynamically, including via Model Context Protocol (MCP) servers.

**2. Steering documents.** Steering documents and intent are closely linked: the steering docs you create should align with the intent you have. They guide agent behavior and responses.

**3. Requirements.** The intent is translated into a set of requirements, written in a consistent format — EARS (Easy Approach to Requirements Syntax) — optimized for both human readability and LLM understanding.

Requirements (and the broader spec) exist to:
- Transform vague feature ideas into concrete, measurable requirements
- Establish clear acceptance criteria for feature success
- Create a shared understanding between stakeholders
- Provide a foundation for design and implementation decisions

### EARS Requirement Patterns

| Pattern Name | Pattern |
|---|---|
| Ubiquitous | The `<system name>` shall `<system response>` |
| Event-Driven | WHEN `<trigger>` `<optional precondition>`, the `<system name>` shall `<system response>` |
| Unwanted Behavior | IF `<unwanted condition or event>`, THEN the `<system name>` shall `<system response>` |
| State-Driven | WHILE `<system state>`, the `<system name>` shall `<system response>` |
| Optional Feature | WHERE `<feature is included>`, the `<system name>` shall `<system response>` |
| Complex | (combinations of the above patterns) |

## Steering Documents: Context Strategy

**Smart context selection**
- Automatic
- Pattern match
- Manual

**Generation**
- Generate context from existing codebases (brownfield)
- Generate context files from MCP servers

**Strategies for writing steering docs**
- Start small — include just the core knowledge you want to influence the assistant
- Use different inclusion modes to help the AI coding assistant optimize which steering files to use and manage context window utilization
- Use clear, descriptive file names (e.g. `api-rest-conventions.md`) and descriptions
- Provide examples — code snippets, style/structure guides, sample input/output
- **Security first** — never include sensitive information in steering docs: no API keys, passwords, or sensitive data
- Review and maintain steering files as you iterate; treat them as first-class citizens

## Keeping Specs Current: Triggers for Updates

| Trigger | Description |
|---|---|
| Clarification | Minor updates that don't functionally change design/implementation but improve precision |
| Changes | Changes to existing specs (requirements or design), or new requirements |
| Discoveries | During implementation, you may discover details that lead to changes in design |
| Technical Constraints | During code generation you hit sub-optimal choices: library/API limitations, performance issues, security concerns |
| Integration Challenges | Data/interface format issues, authentication/authorization complexity, new or updated interfaces |
| Feedback | Testing or user feedback — accessibility, mobile support, responsiveness, browser compatibility |

## How SDD Compares to Existing Methodologies

**vs. Test-Driven Development (TDD)**
- Similarities: both define success criteria before implementation; both use an iterative red-green-refactor-style cycle (requirements → design → implementation)
- Differences: SDD operates at a higher level of abstraction, includes business requirements and use cases (not just tests), can incorporate TDD practices within its implementation phase, and provides broader context beyond just testing

**vs. Waterfall**
- Similarities: both emphasize upfront planning and documentation; both follow a sequential phase approach
- Differences: SDD is more iterative within each phase; specs are living documents that evolve; SDD is optimized for feature-level development rather than entire projects; greater emphasis on AI-assisted development and collaboration

**vs. Behaviour-Driven Development (BDD)**
- Similarities: both prioritize design and planning before coding; both create detailed technical specifications
- Differences: SDD includes explicit requirements gathering, a more structured approach to task breakdown and planning, is designed specifically for AI-assisted development workflows, and includes specific methodologies like EARS for requirements

## Vibe Coding vs. Spec-Driven Development

| The Vibe (prompts to chase implementations) | Spec-Driven (preserve intent, improve visibility) |
|---|---|
| Rapid, conversational code generation ("CHOP") | Focus on upfront planning and intent |
| Iterative, back-and-forth | Break down requests into discrete tasks |
| Ephemeral | Steering documents ground agentic outputs |
| Point-in-time prompts | Lineage between intent and code |
| Transient context | |

## Closing Takeaway

Everyone is developing their own spec-driven development workflow — there's no single standard yet, but the underlying pattern (intent → steering → requirements → design → tasks, kept as living documents) is converging across teams.
