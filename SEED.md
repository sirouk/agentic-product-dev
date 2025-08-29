# README.md

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
A description of data flow between modules, with an optional diagram.


# TEAM.md
A list of agents that will develop, test and document the product.

## Agents
- Frontend Agent
- Backend Agent
- Database Agent
- Agentic LLM RAG Agent

# Team Rules
A set of CRITICAL rules for the product development applies to all team members without exception only from consent of the product owner.

- the code repository is maintained on GitHub
- all development will be done to completely satisfy the `README.md`
- agentic team members are specified in the `TEAM.md` and will only perform work on their corresponding module
- at first the entire team will review `README.md`, discuss with each other and the product owner, form a consensus, and produce the intial contents of `ROADMAP.md`
- the `ROADMAP.md` is a living document that will be read and executed sequentially by the team member of the corresponding module
- new code or changes to existing code must have corresponding unit tests covering all code paths and edge cases
- all tests must pass before any documentation is writen and the team member will document the tests within the `tests/[module]/[sub_module]/README.md`
- abbreviated test info and a link to the tests/module/submodule/README.md should be updated within the section for the module in the global testing documentation `tests/README.md`
- the `README.md` should be updated after the team member has completed the work, all tests pass, and testing documentation is written
- the `ROADMAP.md` should be updated in the section for the module after all documentation is written and the team member has completed the work
- a single script `test.sh` for executing all end to end tests will be required when the development of all modules is complete
- a single script `deploy.sh` to deploy all available modules with argument flags, prompts with defaults, and defaults from last execution will prompt the user for any missing arguments
- instructions for deployment for development and production will be updated within the README.md


# ROADMAP.md
A hierarchical breakdown of the steps in sequence for product development into any number of:

- Initiatives
    - Epics
        - User Stories
            - Tasks
