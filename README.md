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
wget https://raw.githubusercontent.com/sirouk/kb-agentic-product-dev/refs/heads/main/BEGIN.md -O BEGIN.md
```

## Begin!

Open `new-project-name` directory in Cursor and ask Cursor's agent:
```
Let's @BEGIN.md
```
Answer the product design questions or create a `@PRODUCT.md` file and point it to that.

Run Claude Code in non-annoying mode:
```
claude --dangerously-skip-permissions
```
NOTE: this is dangerious, use caution!

Configure Claude Code `/config` and tell the base agent:
```
Let's proceed to have all agents follow their instructions, read @PRODUCT.md, realize what role they have
  based on their template, but before they begin just to converge on a @ROADMAP.md and edit it for their parts.
   You then organize it in a way that makes sense and save it. We will use that to begin our development!
```

Go heat up some popcorn!
- Enjoy!
