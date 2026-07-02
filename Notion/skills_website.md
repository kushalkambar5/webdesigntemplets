## Frontend Design

- npx skills add anthropics/claude-code - skill frontend-design
- npx skills add https://github.com/vercel-labs/agent-skills --skill web-design-guidelines
- Figma to code: npx skills add https://github.com/anthropics/skills --skill figma
- Theme factory: npx skills add https://github.com/anthropics/skills --skill theme-factory
- Brand Guidelines: npx skills add https://github.com/anthropics/skills --skill brand-guidelines
- Canvas Design: npx skills add https://github.com/anthropics/skills --skill canvas-design
- Skill Creator: npx skills add https://github.com/anthropics/skills --skill skill-creator
- npx skills add https://lnkd.in/gJUtRmBK --skill tinyfish
- npx typeui.sh pull <slug>
    
    
    | **Skill Name [1, 2, 3, 4]** | **Command** |
    | --- | --- |
    | **Bento** | `npx typeui.sh pull bento` |
    | **Paper** | `npx typeui.sh pull paper` |
    | **Cafe** | `npx typeui.sh pull cafe` |
    | **Modern** | `npx typeui.sh pull modern` |
    | **Bold** | `npx typeui.sh pull bold` |
- https://www.design-extractor.com/ - Paste a URL and get a structured DESIGN.md with colors, typography, spacing, and tokens.
- https://github.com/VoltAgent/awesome-design-md - Copy a DESIGN.md into your project, tell your AI agent "build me a page that looks like this" and get pixel-perfect UI that actually matches.
- https://www.designprompts.dev/ - Drop these prompts into any AI assistant and ship beautiful, consistent interfaces in minutes.
- https://drive.google.com/file/d/1z4t4fOwQ62_RDk29uwZ6WJrnnu97nE-D/view?usp=sharing - Animated website Design.md file
- https://github.com/pbakaus/impeccable - npx skills add pbakaus/impeccable
- https://www.ui-layouts.com/ -
- https://reactbits.dev/
- https://magicui.design/
- https://tympanus.net/
- https://uiverse.io/ - for elements
- https://www.awwwards.com/
- https://tympanus.net/codrops/hub/
- https://ui.aceternity.com/components
- https://www.svgator.com/animation-templates - SVG Templets
- https://styles.refero.design/ - Themes+its design.md
- https://skiper-ui.com/components
- https://app.spline.design/community - 3d model templets
- https://getdesign.md/
- **Explain Code: mkdir -p ~/.claude/skills/explain-code**
- motionsites.ai
- 

## Mobile Frontend Design

npx skills add https://github.com/vercel-labs/agent-skills --skill vercel-react-native-skills

**react-native-bottom-tabs -** https://github.com/callstack/react-native-bottom-tabs

- InstantDB Skill: npx skills add instantdb/skills
- **Building Native UI:** npx skills add https://github.com/expo/skills --skill building-native-ui
- **Explain Code: mkdir -p ~/.claude/skills/explain-code**
- **React Native Skills:** npx skills add https://github.com/vercel-labs/agent-skills --skill vercel-react-native-skills
- **App Icon:** npx skills add https://github.com/code-with-beto/skills --skill app-icon

# **Skill Creator**

- npx skills add https://github.com/anthropics/skills --skill skill-creator

## **supabase-postgres-best-practices**

npx skills add supabase/agent-skills --skill supabase
npx skills add supabase/agent-skills --skill supabase-postgres-best-practices

npx skills add https://github.com/supabase/agent-skills --skill supabase-postgres-best-practices

## **better-auth-best-practices**

npx skills add https://github.com/better-auth/skills --skill better-auth-best-practices

## Tinyfish

- **Navigating bot-protected sites** without getting blocked.
- **Extracting structured JSON** from dynamic web pages instead of raw HTML.
- **Automating multi-step browser flows** (like filling forms or clicking buttons).

npm install -g @tiny-fish/cli

npx skills add tinyfish-io/tinyfish

## Superpowers

- /plugin install superpowers@claude-plugins-official
- **Brainstorming & Design:** The agent starts by asking clarifying questions and exploring alternatives before drafting a formal design document.
- **Structured Planning:** Once the design is approved, it breaks the work into 2–5 minute "bite-sized" tasks with exact verification steps.
- **Strict TDD (Test-Driven Development):** It enforces a "Red-Green-Refactor" cycle—writing the test first and even deleting any code written before a failing test exists.
- **Systematic Debugging:** It replaces "guessing" with a four-phase root cause analysis process.
- **Workflow Automation:** It utilizes **git worktrees** to keep development in isolated branches, ensuring your main workspace stays clean.

Download: https://github.com/obra/superpowers/tree/main/skills

Drop them into your project's `.agent/skills/` directory

# GSD - Get shit done skill

- npx get-shit-done-cc —claude —global

!image.png

# Graphify

https://github.com/safishamsi/graphify

## Cavemen

- **Token Savings:** It cuts between **65% and 75%** of output tokens on average.
- **Speed:** Because the agent generates fewer words, the responses arrive significantly faster ("speed go brrr").
- **Specialized Sub-Skills:**
    - **`caveman`:** The standard compressed communication mode.
    - **`caveman-review`:** One-line code reviews that provide the location, problem, and fix immediately.
    - **`caveman-commit`:** Generates terse "Conventional Commit" messages under 50 characters.
    - **`compress`:** A tool that overwrites your "memory files" (like `CLAUDE.md` or `TODOS.md`) into a compressed format to save *input* tokens in every future session.

npx skills add https://github.com/juliusbrussee/caveman

## Claude-mem

- **Continuous Learning:** It captures tool usage and observations in real-time and compresses them into searchable "memories" using AI.
- **Context Injection:** In future sessions, it injects the most relevant "memories" back into the AI’s context, so you don’t have to re-explain the project structure or previous bugs.
- **Token Efficiency:** It uses a "3-Layer Workflow" (Search → Timeline → Fetch) to find the right memory without bloating your token usage.
- **Web UI:** It includes a dashboard at `http://localhost:37777` where you can view your AI's "thought stream" and memories live.

### **Step 1: Install the Memory Worker**

First, you need to install the core service on your machine that will actually store the memories:

Bash

`npx claude-mem install`

*This handles the dependencies, SQLite database setup, and background worker.*

### **Step 2: Add to Antigravity (MCP)**

Antigravity doesn't use a simple `SKILL.md` for this because it requires a live server to search the database. You must add it as an MCP server:

1. Open Antigravity and click the **three dots (...)** at the top right of the **Agent Manager** panel.
2. Select **"MCP Servers"** and then **"Manage MCP Servers"**.
3. Click **"View raw config"** to open your `mcp_config.json` file.
4. Add the following entry to the `mcpServers` object:JSON
    
    ```jsx
    "claude-mem": {
      "command": "npx",
      "args": ["-y", "@thedotmack/claude-mem", "mcp"]
    }
    ```
    
5. Save the file. Antigravity will automatically detect the new **`mem-search`**, **`timeline`**, and **`get-observations`** tools.

### **Step 3: Using the Skill**

Once connected, you don't need to do anything manually. The agent in Antigravity will "see" that it has a memory tool. When you ask a question like, *"What was that bug we fixed last week in the Fundify project?"*, the agent will automatically call the `mem-search` skill to find the answer.

## **Awesome Agentic Patterns**

This repository includes a special `llms.txt` file designed specifically for AI agents to read.

1. In your Antigravity chat, simply paste this URL and say:
    
    > *"Read the patterns from https://agentic-patterns.com/llms.txt and use them to improve your workflow for my project."*
    > 
2. Antigravity will index the entire library of 166 patterns and start applying things like "Context-Minimization" and "Step-by-Step Verification" to your code.

## **sql-optimization-patterns**

npx skills add https://github.com/wshobson/agents --skill sql-optimization-patterns

**it is excellent for production development.**
Most performance bottlenecks in production apps happen at the database layer (slow queries, missing indexes, or the "N+1" problem). This skill provides the AI with a "Senior DBA" mindset, ensuring it doesn't just write code that *works*, but code that *scales*.

**Key Production Benefits:**

- **Systematic EXPLAIN Analysis:** Instead of "guessing" what’s slow, it teaches the agent to use `EXPLAIN ANALYZE` to read query plans and find the exact bottleneck (e.g., a Sequential Scan vs. Index Scan).
- **Anti-Pattern Detection:** It specifically targets the **N+1 query problem** (fetching data in a loop), which is the #1 killer of production performance in MERN/Node.js apps.
- **Advanced Indexing:** It covers more than just basic indexes; it includes **Composite, Partial, and Covering indexes**, which are essential for high-traffic apps.
- **Efficient Pagination:** It moves agents away from slow `OFFSET`/`LIMIT` pagination (which gets slower as your table grows) toward performant cursor-based pagination.

---

### **Where it can make problems**

While powerful, blindly following these optimization patterns can lead to a few "production traps":

### **1. The "Over-Indexing" Trap**

- **The Problem:** The skill heavily emphasizes creating indexes to speed up reads.
- **The Risk:** Every index you add makes `INSERT`, `UPDATE`, and `DELETE` operations **slower** because the database has to update the index too. If your app is write-heavy (like a logging system), too many indexes can crash your performance.

### **2. Version & Database Lock-in**

- **The Problem:** This skill is heavily optimized for **PostgreSQL** (using features like GIN/GiST indexes and specific `EXPLAIN` metrics).
- **The Risk:** If you are using **MySQL**, **MariaDB**, or **SQLite**, some of the suggested syntax or index types might not exist or might behave differently, leading to "syntax errors" or ineffective optimizations.

### **3. Stale Data with Materialized Views**

- **The Problem:** The skill suggests **Materialized Views** for complex aggregations.
- **The Risk:** Unlike regular Views, Materialized Views do not update automatically. If the agent implements them without a "Refresh" strategy, your production users will see **stale, old data**.

### **4. Complexity & Technical Debt**

- **The Problem:** It may suggest refactoring a simple `JOIN` into a complex subquery or temporary table for "efficiency."
- **The Risk:** Sometimes the "optimized" version is so complex that your human team will struggle to maintain it. In production, "readable and slightly slower" is often better than "super-fast but unreadable."

### **Recommendation**

Install it, but use it with a **"Verification Pattern."** When the agent suggests an optimization, ask:

> *"What is the impact of this new index on our write speed, and will this work on my specific DB version?"*
> 

This ensures you get the performance gains without the side effects.

# **api-design**

npx skills add https://github.com/supercent-io/skills-template --skill api-design

Must while creating websites

The Ultimate SaaS Launch Checklist — 68 Things Before You Ship

Claude Code or Open Code points

Creating Tools Websites