# Playbook: improve a screen that already exists

"Better" means closer to the best equivalent screens in hierarchy, clarity and finish, verified in a capture from the design tool, not by eye.

**Always work on a copy.** Never edit the original screen. Duplicate it into a test section below the base screens (for example "Skill test: <screen>") with the "Before" copy and the "After" version side by side. The original changes only when the user approves the "After".

**Every choice has a justification.** Each "After" gets a note (sticky note or text frame) beside it listing each change with its source: user decision, project rule, user curation, Mobbin reference (with `mobbin_url`) or "agent suggestion". A change without a justification does not go in.

## 1. Diagnose before searching

Capture the current screen and name its 3 biggest problems precisely ("three lines of the same weight, no hierarchy", "back button centered instead of at the top", "slider hand-drawn instead of using the component"). The research aims at those problems.

## 2. Reference board

Free searches first, looking at every image (see "AI credits" in SKILL.md):
- `search_screens(mode="standard")` with the NAME of the screen or content ("profile with weekly insights", "notes editor with bullet list"); if needed, a second `standard` with another term or a priority app's name.
- `search_screens(mode="deep")` with what it should LOOK like ("calm light profile with a weekly row and a streak card") ONLY if the standard searches didn't yield 5 good references, and at most once per screen.

Include the user's priority apps. Pick the **5 to 8 best** and say why each earns its place; store them in `references/mobbin/<area>/`.

## 3. Extract the pattern

Write down the target: layout skeleton, hierarchy order, controls, spacing rhythm, role of colors (mapped to your tokens) and where motion would live (annotate in the note; static tools can't show it). Every line must be checkable in a capture.

## 4. Rebuild and iterate (the loop)

1. Build against the target using existing components and variables or tokens, and your project's type, icon, touch-target and platform rules.
2. Capture the screen and compare side by side with the 2 best references.
3. Check: clipped text, overlap, margins, contrast (text and non-text minimums from your rules or WCAG), hierarchy, states (empty, loading, error), dark mode via tokens.
4. Fix and repeat. Do not stop at "better than before": stop when an honest comparison with the best reference is **at least as good**. If it isn't, name the gap and go around again.

## 5. If the screen belongs to a flow

Check one step before and one after in the prototype: entry, exit, the state carried from one to the other, and what back does. If the screen is a sheet, a modal, or sits after a one-way door, confirm its presentation matches what it IS.
