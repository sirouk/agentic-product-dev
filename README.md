# Agentic Product Development Seed Document

The goal of this project is to provide a quick and easy way to start a new project with a team of agents. We decided to use Claude as our agentic framework.

Use the [CLAUDE.md](/CLAUDE.md) to start your journey in a new code repo.

The steps below will help you get started quickly.


## Quick Start

Set up new repo:
```bash
cd $HOME
mkdir new-project-name
```

Enter and fetch [`CLAUDE.md`](/CLAUDE.md) document:
```bash
cd ./new-project-name
wget https://raw.githubusercontent.com/sirouk/agentic-product-dev/refs/heads/main/CLAUDE.md -O CLAUDE.md
```

## Begin!

Open `new-project-name` directory in Cursor and ask Cursor's agent:
```
Hey @CLAUDE.md, let's begin!
```
Answer the product design questions or create a `@PRODUCT.md` file and point it to that.

Run Claude Code in non-annoying mode:
```
IS_SANDBOX=1 claude --dangerously-skip-permissions
```
NOTE: this is dangerious, use caution!

Configure Claude Code:
```/config```

Then have the sub-agents collab on `DATAFLOW.md`:
```
Activate all agents in parallel to acknowledge their roles and template rules,
  thoroughly review @PRODUCT.md, and collaboratively update @DATAFLOW.md by identifying
  each other's needs and ensuring each agent's section covers all intra-agent and inter-agent data
  flows and all service interactions.
```

Once they converge on a `DATAFLOW.md`, have sub-agents draft their module sections in `ROADMAP.md`, then the base agent sequences/reviews (no code edits by base agent):
```
Sub-agents: read your @.claude/agents/*.md template and carefully study @DATAFLOW.md to author your module's `ROADMAP.md` section.
Base agent: study all module sections and @DATAFLOW.md to sequence and segment the global `ROADMAP.md` respecting dependencies and phases. Base agent does not author module work items.
```

Review the `ROADMAP.md` for `DATAFLOW.md` compatibility:
```
Let's do a once-over by carefully reviewing @DATAFLOW.md and @ROADMAP.md to make sure
  all sections and items are in their section and sequenced in a way that makes sense,
  as this will determine the ability for our @TEAM.md to succeed in developing the @PRODUCT.md
```

Once you review the documents, and it is to your liking, proceed to development:
```
Ok, let's proceed to have all agents carefully work in parallel,
  staying within their scope, working in sequence, and stopping where blocked.
  Sub-agents perform all code edits and tests for their modules.
  The base agent performs no code edits and only sequences/reviews the `ROADMAP.md`,
  communicates with the product owner and sub-agents, and enforces phase gates and dependencies.
  Agents should never complete work assigned to another agent.
```

Go heat up some popcorn!
- Enjoy!
