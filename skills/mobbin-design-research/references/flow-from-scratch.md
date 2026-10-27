# Playbook: design a flow or area from scratch

The goal is a finished flow in your design tool in which every screen holds up side by side with the best reference studied, not a draft.

## Phase 1: user base and winners

1. Read the user's curation (SKILL.md, ground rule 1): saved collections, curated folders, design files. If a base exists for the area, it is the skeleton.
2. Run 1 to 3 `search_flows` for the journey and 2 to 4 `search_screens` for the key screens. Prioritize the apps the user saved or named (`priority_apps` in the config).
3. Record them in `references/mobbin/<area>/REFERENCES.md` with `mobbin_url` and what to take from each (see [REFERENCES.example.md](../examples/REFERENCES.example.md)).

## Phase 2: read the language of the area

Answer, with images side by side:
- What is the first moment of this area? What is one tap away?
- How many steps does the flow have, and what does each step earn (data, permission, commitment)?
- What do the empty, loading, error and success states look like?
- What does everyone do (mandatory), what do only the best do (differentiator), and what does everyone do badly (your chance)?

Write the answers in `references/mobbin/PATTERNS.md` (see [PATTERNS.example.md](../examples/PATTERNS.example.md)).

## Phase 3: spec and navigation map

List the screens in journey order. For each, state what it IS (tab, pushed screen, modal, sheet, overlay) and what back does, including one-way doors (sign-in, finishing onboarding, purchase) where back must not reopen the old state. Show the plan to the user before drawing and wait for corrections.

## Phase 4: build screen by screen

For each screen, in order:
1. Reopen its references (curation first; `search_screens` for gaps).
2. Build with the components from your design system's components page and its variables or tokens. Where a component is missing, use a labeled placeholder and list what was missing.
3. Run the capture-and-compare loop (see [improve-a-screen.md](improve-a-screen.md), step 4) until no defect is found.

## Phase 5: the ruler

Walk the whole flow in the prototype three times:
1. **Happy path.**
2. **Skeptical path:** skip everything that can be skipped.
3. **Error path:** invalid data, empty states, back at every point.

If any screen ends up worse than the best equivalent reference, it goes back into the loop.
