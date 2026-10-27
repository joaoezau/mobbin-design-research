---
name: mobbin-design-research
description: Design research with Mobbin that ends in a better screen, not a moodboard. Use when designing, improving or reviewing any screen, flow or component (onboarding, paywall, settings, chat, profile, tab bar...), when the user says "search Mobbin", "how do other apps do X", "look at how the best apps handle this", or shares a reference link or screenshot. Covers the Mobbin tool map, how to study flows and components, where to store research, and two playbooks ("flow from scratch" and "improve a screen") that always finish with a capture-and-compare loop in the design tool.
license: MIT
---

# Mobbin design research

Mobbin is a library of real app screens and flows. This skill turns research into decisions: **study what already works, then build something better in your design tool**, inside your project's own rules.

Requires the official Mobbin MCP server (hosted at `https://api.mobbin.com/mcp`, OAuth sign-in, read-only tools `search_screens`, `search_flows`, `search_sections`) and a paid Mobbin plan (Pro, Team or Enterprise); docs: https://mobbin.com/mcp and https://github.com/mobbin/mobbin-mcp-server. Without it, use the fallback below.

## Step 0: load the project config

Read `project-config.md` at the project root or in your agent's config folder (e.g. `.claude/`, `.cursor/`, `.gemini/`) (template: [references/project-config.template.md](references/project-config.template.md)). It names the rules file, platform, design tool, design-system locations, curated reference folders, priority apps, naming quirks and rate limits. If it is missing, offer to create it from the template; otherwise use these defaults: rules file `AGENTS.md` (or your agent's equivalent, e.g. `CLAUDE.md`, `GEMINI.md`), platform `ios`, design tool Figma, no curated folders.

Read the project rules file before designing. Research never authorizes breaking those rules: copy **patterns, not pixels**, colors or fonts from other apps.

## Without the Mobbin MCP

If the Mobbin tools are not available in this tool or chat, say so at the start. Ask the user for Mobbin links, screenshots or their exported collection, and run the same method on those (questions, numbers, patterns, compare loop). Never pretend to have searched Mobbin, and never invent `mobbin_url`s or screens you have not seen.

## Who decides (priority order)

1. The user's explicit decision, including hand edits made in the design tool (never overwrite them).
2. The project rules file.
3. The user's curation: saved Mobbin collections, bases and references they provided.
4. Mobbin references.
5. Agent judgment, only to fill gaps. Anything the agent adds on its own (new color, icon, element, structural change) stays out of the "After" version and goes in the justification note as "agent suggestion" for the user to decide.

One "After" version per screen: no B/C options. Would-be options go in the note, not as extra screens.

## Ground rules

1. **Curation first.** Before searching, check what the user already chose: saved collections, the curated folders and design files listed in the config. When a user base exists for the screen it leads; Mobbin completes it.
2. **Go deep, with a question.** Every search answers a question from the task ("how do apps show the streak?", "where does note privacy live?"). A search without a question is sightseeing.
3. **Look at the images.** Never describe a screen from metadata alone. Cite each screen used with its `mobbin_url`.
4. **Image links expire.** Download what you use (from `image_url`, never the preview) into `references/mobbin/<area>/img/` and record the `mobbin_url`, which is durable.
5. **App-name collisions.** If a name returns the wrong app, search distinctive spellings or add a qualifier (see `naming_quirks` in the config).
6. **Respect rate limits.** Mobbin MCP allows 60 requests per 60 seconds per user (HTTP 429 with `Retry-After`: wait, then retry). Mobbin searches don't spend your design tool's limits, so search before opening the tool. In the tool, batch work into large scripts and capture at the end of each block; the limits live in the config.
7. **Reuse existing components.** Never hand-draw what the design system already has.
8. **Extract numbers, not vibes.** Sizes, positions, item counts, labels, active states.

## Tool map (Mobbin MCP)

| Tool | Returns | Use when |
|---|---|---|
| `search_screens` | Up to 30 screens with image, app and `mobbin_url`. `mode="deep"` interprets intent and filters relevance; `mode="standard"` is fast. Name the app to filter ("<app> profile screen") | References for one screen or component |
| `search_flows` | Up to 10 flows per page, screens in order; paginate with `page` | How apps chain a journey (onboarding, paywall, add a friend) |
| `search_sections` | Website sections | Web or landing pages only |
| Collection tools (only if your client exposes them) | The user's saved collections | Reading curation |

Fixed parameters (`platform`, `image_format`, output destination and tool) come from the config. Use the **same English `task_intent`** in every search of one task. One search = one screen or one journey. No negations, no vague words ("modern", "clean"), never two things at once.

## Playbooks

| Situation | Playbook |
|---|---|
| Design a flow or area from scratch | [references/flow-from-scratch.md](references/flow-from-scratch.md) |
| Improve a screen that already exists | [references/improve-a-screen.md](references/improve-a-screen.md) |
| Study a flow or a component | [references/methods.md](references/methods.md) |

Both build playbooks end the same way: **the capture-and-compare loop in the design tool, repeated until no defect is found** (see `improve-a-screen.md`, step 4). Research without that loop is decoration.

## Where to keep the research

```
references/mobbin/
  <area>/                 # e.g. profile, onboarding, streaks
    REFERENCES.md         # screens and flows used: mobbin_url, app, what was taken from each
    img/                  # downloaded images, in journey order
  PATTERNS.md             # cross-app synthesis: what everyone does, what only the best do, where to beat them
```

Templates: [examples/REFERENCES.example.md](examples/REFERENCES.example.md) and [examples/PATTERNS.example.md](examples/PATTERNS.example.md). On delivery, cite the screens used and one line on what came from each.
