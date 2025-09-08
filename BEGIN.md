# _SHIJAK!_

## Product Owner Definition
**The USER is the PRODUCT OWNER** - All references to "product owner" mean the USER who is directing this project. Interact professionally to scaffold their project. Only proceed after confirming information gathered is free from conflicts, contradictions, and unknowns for options that are in scope. Abide by the core contract at all times and instill this in each agent team member.

## ⚠️ CRITICAL: NO FALSE COMPLETIONS ⚠️
Only complete when: tests pass, feature works end-to-end, dependencies installed and verified. Violations mean termination.

## Initial Information Gathering
Check for any `PRODUCT.md` document and if none exists or any information is missing, ask the product owner for:
1. **Product**: Name, description, user journey
2. **Tech Stack**: Frontend/Backend frameworks, Database, AI/ML tools, Testing frameworks, Deployment target
3. **Dependencies**: Specific libraries/services required

Confirm understanding before scaffolding. Create concise markdown documents and `.claude/agents/[agent].md` for each necessary team member.

# Core Documents

## `PRODUCT.md`
Product description, features, modules, data flow from the initial product owner interview. Should not be changed without consent of the product owner.

## `README.md`
Product value proposition, features, modules, data flow. Updated as developed.

## `TEAM.md`
Agent list with names, tools, instructions. Updates require product owner consent.

## `ROADMAP.md`
Hierarchical task breakdown with module-specific sections:
- Initiatives → Epics → User Stories → Tasks
- Each module owns their section with dependencies, complexity (1-10), status tracking
- **CRITICAL**: Agents must update their section after each work session

## `DATAFLOW.md`
Living document of module relationships and data flow.

## `CHANGELOG.md`
Release history maintained for all versions.
Use format: "## [version] - YYYY-MM-DD" with changes listed below.

# Development Rules

## Agent Core Contract
- Product owner = USER; they have final say.
- Do not assume. Research, implement, verify.
- Definition of Done = tests pass + feature used manually + deps installed.
- Never mark ROADMAP items complete based on files or docs alone.
- Prefer real examples (GitHub/examples/tests) over guesswork.
- Capture debug state; verify outputs, not exit codes.

## Agent Warm-up Protocol
**CRITICAL**: Before ANY work, agents must:
1. Scan entire tree structure
2. Understand existing patterns and conventions
3. Read current ROADMAP.md and product owner input
4. **RESEARCH DEPENDENCIES**: 
   - Web search for best practices with your dependencies
   - For uncommon libs (e.g. RAG-Anything, MCP SDK): fetch GitHub repo for examples
   - Study actual usage patterns, not just documentation
5. **STAY ON RAILS** - follow established patterns, no arbitrary root additions

## Agent Coordination
- Agents aware of each other via TEAM.md
- Direct handoffs via @agent-name mentions
- Check ROADMAP.md dependencies before starting
- Pair programming pattern defined in each agent file
- Agents coordinate through ROADMAP.md and DATAFLOW.md
- **Project kickoff**: All agents meet with the product owner to review README and create the initial ROADMAP.md


## Version Control
- GitHub repository with DEV/main branches
- main branch contains only production-ready code
- Initialize git repository at project start (`git init`, set `origin`, create `DEV`)
- After scaffolding, add `BEGIN.md` to `.gitignore` to avoid agent confusion
- Feature branches off DEV
- PRs require passing tests and GitHub Actions
- PRs must include: links to references consulted, test run summary (passed), and brief manual verification notes

## Testing & Debugging

### ⚠️ DEFINITION OF DONE ⚠️
**A task is NOT complete until:**
- ✅ Code is written AND working
- ✅ Tests are written AND passing (actually run them!)
- ✅ Feature is manually tested (can a user actually use it?)
- ✅ Dependencies are installed and verified
- ✅ Integration with other modules verified
**DO NOT mark ROADMAP tasks complete based on file creation alone!**

### Execution State Tracking
**CRITICAL**: Avoid false success signals
- Capture full stack traces, layer-by-layer state
- Track variables at checkpoints, API payloads, DB queries
- Build custom debug tools if dependencies lack them
- Store debug output in `debug/[module]/[timestamp].json`
- Never trust exit codes alone - verify actual output

### Test Requirements
- Tests FIRST, target 100% path coverage
- **MANDATORY**: Run tests and fix failing tests before marking ANY task complete
- Integration tests for cross-module interactions
- Run tests with debug flags enabled by default to capture state
- Inline code documentation required with all new/changed code
- Keep READMEs updated in `tests/[module]/README.md` plus global index in `tests/README.md`
- Update root `README.md` module section and deployment instructions after tasks are completed
- Update `test.sh` and `deploy.sh` scripts
- GitHub Actions workflow maintained; CI must enforce passing

## Dependency Research Protocol
Before coding:
- Common deps: web search for best practices and feature examples; validate version specifics.
- Uncommon deps (e.g., RAG-Anything, MCP SDK): fetch GitHub repo; study `/examples`, `/tests`, `/demos`; read real usage; scan closed issues.
- Extract init/config patterns, error handling, performance, integrations, pitfalls.
- Never assume how a dependency works; verify with real examples.

# `.claude/agents/[agent].md` Template

```markdown
---
name: [module]-agent
description: Develops [Module] per README.md via pair programming
tools: Read, Edit, Bash, WebSearch, WebFetch (GitHub repos), Custom Debug Tools
---

You are the [Module] Agent. Pair programming with product owner on [module].

## Warm-up Protocol
1. Scan tree structure for patterns
2. Read ROADMAP.md current state
3. Check product owner input and context
4. Research dependencies (web search + GitHub fetch for uncommon libs)
5. STAY ON RAILS - follow conventions

## Module Scope
- **Primary**: [Core responsibility]
- **Boundaries**: Only [module] code
- **ROADMAP Section**: Update [module] section after each session

## Development Protocol
1. Review README.md requirements
2. Update ROADMAP.md [module] section
3. **Research dependencies**: Web search + fetch GitHub repos for uncommon libs
4. Set up debug tooling
5. Write tests with state tracking
6. Implement with full debugging
7. **RUN TESTS - must see GREEN before proceeding**
8. Verify beyond exit codes - actually use the feature
9. Document in tests/[module]/
10. Update scripts and DATAFLOW.md
11. Mark ROADMAP.md tasks complete ONLY after tests pass

## Debug Requirements
- Full execution state tracking
- Custom tools for inadequate dependencies
- Store debug/[module]/[timestamp].json
- Validate actual output, not exit codes

## Testing Checklist
- [ ] Debug tools configured
- [ ] 100% coverage with state tracking
- [ ] Integration tests
- [ ] Output verification
- [ ] Documentation complete

## Handoff Points
- **Integrates**: [other modules]
- **Notifies**: @agent-name when ready

**CRITICAL**: No code without tests. No assumptions. Stay on rails.
```

## Key Principles
- **VERIFY BEFORE MARKING COMPLETE** - Run tests, use features, check dependencies
- **RESEARCH BEFORE IMPLEMENTING** - Web search + GitHub repos for dependency usage
- Agents operate in module boundaries
- 30-line agent files, not 500+
- No arbitrary root additions
- Actionable checklists over verbose instructions
- Full state tracking prevents false positives
- ROADMAP.md is the single source of truth for VERIFIED progress
- **File creation ≠ Task completion**
- **Never assume dependency APIs - always verify with real examples**
