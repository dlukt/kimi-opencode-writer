# Kimi OpenCode Writer

This repository contains a specialized configuration for [OpenCode](https://opencode.ai) designed to turn the Kimi 2.5 model (or other long-context LLMs) into a **"Novel Architect"**—a collaborative agent for planning, outlining, and drafting books.

**Repository:** [https://github.com/dlukt/kimi-opencode-writer](https://github.com/dlukt/kimi-opencode-writer)

## 📂 Repository Structure

```text
.
├── agents
│   └── writer.md       # The "Novel Architect" agent persona and logic
└── commands
    ├── bible.md        # /bible : Generates story status report
    ├── critique.md     # /critique : Editor mode for feedback
    └── expand.md       # /expand : Enhances prose with sensory details
```

## 🛠️ Installation

### Option 1: Per-Project (Recommended)
Use this method to keep the agent configuration specific to your book project.

1.  Navigate to the root of your writing project.
2.  Clone this repository (or copy the `agents` and `commands` folders) into a `.opencode` directory.

```bash
# Example structure after install:
my-novel/
├── .opencode/
│   ├── agents/
│   │   └── writer.md
│   └── commands/
│       ├── bible.md
│       ├── critique.md
│       └── expand.md
└── chapter1.txt
```

### Option 2: Global Install
Use this method to make the writer agent available in every OpenCode session.

Copy the `agents` and `commands` folders to your global configuration path:
* **Mac/Linux:** `~/.config/opencode/`
* **Windows:** `%APPDATA%/opencode/`

---

## 🚀 Usage Guide

### 1. Activate the Agent
Open OpenCode and run the following command to switch to the writer persona:
```bash
/agent writer
```

### 2. The Kickoff (First Message)
To properly initialize the writer persona and start Phase 1, **copy and paste the following prompt** into the chat:

> Hi! I'm ready to start. I have the `writer` agent active.
>
> I want to write a novel. Let's begin **Phase 1: Brainstorming & Setup**.
>
> Here is what I know so far:
> * **Genre:** [Insert Genre, e.g., Sci-Fi Mystery]
> * **Vibe/Tone:** [e.g., Dark, Humorous, Fast-paced]
> * **Core Idea:** [Insert idea or leave blank]
>
> Please help me solidify the concept and create a 'Story Bible' before we start outlining.

### 3. Workflow Commands
Use these commands during drafting to maintain quality and consistency.

| Command | Description |
| :--- | :--- |
| **`/bible`** | **Memory Save.** Run this after every chapter. It forces the agent to summarize the plot, inventory, and character status so it doesn't forget details later. |
| **`/expand`** | **Prose Enhancer.** Run this on a specific paragraph (e.g., `/expand the fight scene`). It rewrites the text to be 50% longer with deep sensory details. |
| **`/critique`** | **Quality Control.** Run this to get a ruthless critique of pacing, plot holes, and dialogue quality. |

