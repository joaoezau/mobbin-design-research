# project-config.md (template)

Copy this file to your project root (or your agent's config folder, e.g. `.claude/project-config.md`) and fill it in. The skill reads it first. Delete lines you don't need; unfilled values fall back to the defaults in SKILL.md.

## Rules
- rules_file: AGENTS.md          # or CLAUDE.md, CONTRIBUTING.md, design-rules.md
- rules_note: Visual, token and touch-target rules in that file always win over a reference.

## Platform and Mobbin parameters
- platform: ios                  # ios | android | web
- image_format: jpg
- output_destination: design_tool
- output_tool: Figma             # name of your design tool
- task_intent: ""                # optional default intent, in English; reuse it for every search of a task

## Design tool
- design_tool: Figma             # Sketch, Penpot, Framer, etc. also work: the loop only needs "capture and compare"
- file_url: ""                   # the source-of-truth design file
- test_section_prefix: "Skill test:"   # where copies go (see improve-a-screen.md)

## Design system
- components_page: ""            # page or library with reusable components
- color_tokens: ""               # collection or prefix names for color
- spacing_tokens: ""             # spacing, radius, size tokens
- type_styles: ""                # text style names
- icon_library: ""
- never: ""                      # e.g. "raw hex values, parallel token collections"

## Curated references (read these before searching)
- saved_mobbin_collections: ""   # URL or collection names
- reference_folders:
  - references/mobbin-saved/
  - references/user-bases/
- reference_design_files: []     # read-only files the user built on

## Priority apps
- priority_apps: []              # apps to include in searches first

## Naming quirks
- naming_quirks:
  - "<app name>: search '<distinctive spelling>' together, because '<plain name>' returns a different app"

## Mobbin AI credits (deep search only: 5 credits per successful search)
- deep_searches_per_screen: 1
- deep_searches_per_task: 3      # above this, ask the user first
- deep_search_allowed: true      # false = never use mode "deep" (zero credits)

## Tool rate limits
- mobbin_mcp_requests_per_minute: 60   # 60 per 60 s per user; on 429 wait for Retry-After, then retry
- design_tool_calls_per_minute: 8
- on_limit_reached: wait 90 seconds, retry once
- batching: large scripts; capture at the end of each block

## Where research is stored
- research_dir: references/mobbin/
