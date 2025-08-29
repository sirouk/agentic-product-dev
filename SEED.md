# SEED.md
Your job is to read the following and interact with the product owner in a professional and concise manner.

You will begin by asking the product owner to obtain the product name, description, and user journey. Before you make the necessary edits to scaffold their project, you will get confirmation from the product owner after. They will make sure you have full understanding of their product and the methodology for development that is outlined in the following sections.

You will create the initial markdown documents for their project and be very concise with the content. You will also establish the .claude/agents/[agent].md document for each agentic team member.

MOST CRITICAL information follows and should be read and kept in memory as you begin to scaffold the project and throughout the entire development process.


# README.md
A value proposition for the product, a concise description of the product's value proposition, and a concise description of the product's features. This will be updated as the product is developed.

## Product Name
A name for the product based on what it does.

## Description
A robust description of the product.

## User Journey
A set of statements describing the user's journey through the use of the product's features.

## Modules
How the product is broken down into modules to provide the entire system. 

- Frontend
- Backend
- Database
- Agentic LLM RAG

## Data Flow
A description of data flow and relationships between modules, with an optional diagram.


# DATAFLOW.md
A description of data flow and relationships between modules, a living document that is updated as the product is developed.


# TEAM.md
A list of agents featuring a name, description, tools and a concise set of instructions for how each agent will develop, test and document the product. The description, tools, and instructions should only be updated by consent of the product owner as the product evolves.

## Agents
- Frontend Agent
- Backend Agent
- Database Agent
- Agentic LLM RAG Agent

## Team Rules
A set of CRITICAL rules for the product development applies to all team members without exception only from consent of the product owner.

## Version Control & Workflow
- the code repository is maintained on GitHub
- all development uses feature branches off `DEV` branch
- pull requests require passing tests before merge
- `main` branch contains only production-ready code
- PRs to `main` will only be accepted for a passing GitHub Actions workflow

## Development Process
- all development will be done to completely satisfy the `README.md`
- agentic team members are specified in the `TEAM.md` and will only perform work on their corresponding module but can communicate with each other to correlate work and tests
- at first the entire team will review `README.md`, discuss with each other and the product owner, form a consensus, and produce the initial contents of `ROADMAP.md`
- the `ROADMAP.md` is a living document with module-specific sections that can be worked on in parallel with defined integration points

## Testing Requirements
- inline code documentation written during development
- new code or changes to existing code must begin with corresponding unit tests covering 100% of all code paths and edge cases
- integration tests required for cross-module interactions with 100% method coverage
- the `DATAFLOW.md` should be updated as the product is developed with the latest data flow and relationships between modules
- test documentation in `tests/[module]/[sub_module]/README.md`
- global testing documentation maintained in `tests/README.md` within the section for the module, with links to the individual tests
- root level `test.sh` script updated to include all tests produced by the team member
- root level `deploy.sh` script updated to deploy all modules with argument flags, user prompts with defaults, and defaults from last execution
- GitHub Actions workflow for automated testing must be kept up to date with execution of all tests
- root `README.md` should be updated in section for module after task is completed; code is written, tested, and documented
- instructions for deployment for development and production will be updated within the `README.md`
- the `ROADMAP.md` should be updated after the team member has completed the work, all tests pass, and documentation is fully written
- merging to `DEV` branch after all of the above is successful and the commit message should correspond with concise description of the work completed
- `CHANGELOG.md` maintained for all releases


# ROADMAP.md
A hierarchical breakdown of the steps for product development, with parallel module tracks and integration milestones:

- Initiatives
    - Epics
        - User Stories
            - Tasks

Each module maintains its own section with:
- Dependencies on other modules clearly marked
- Integration points defined
- Estimated complexity (1-10 scale)
- Status tracking (Not Started, In Progress, Testing, Complete)


# CHANGELOG.md
A changelog for the product, maintained for all releases.

## [0.1.0] - 2025-08-29
- Initial release

## [0.2.0] - 2025-08-30
- Added feature X
- Fixed bug Y
- Improved documentation