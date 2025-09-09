# Agentic Product Development Seed Document

Use the [BEGIN.md](/BEGIN.md) to start your journey in a new code repo.

The steps below will help you get started quickly.


## Quick Start

Set up new repo:
```bash
cd $HOME
mkdir new-project-name
```

Enter and fetch [`BEGIN.md`](/BEGIN.md) document:
```bash
cd ./new-project-name
wget https://raw.githubusercontent.com/sirouk/agentic-product-dev/refs/heads/main/BEGIN.md -O BEGIN.md
```

## Begin!

Open `new-project-name` directory in Cursor and ask Cursor's agent:
```
Let's @BEGIN.md
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

Once they converge on a `DATAFLOW.md` then have the base-agent write the `ROADMAP.md`:
```
Now read all sub-agent's @.claude/agents/*.md template and then carefully study @DATAFLOW.md
  so you can create a carefully sequenced and segemented @ROADMAP.md taking into consideration the full @PRODUCT.md
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
  Each agent must carefully follow their role and template rules to complete
  the tasks in @ROADMAP.md, staying in their scope and stopping where blocked.
  The agents should not ever complete work assigned to another agent.
```

Go heat up some popcorn!
- Enjoy!
