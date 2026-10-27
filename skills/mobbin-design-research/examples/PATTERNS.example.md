# Patterns

File: `references/mobbin/PATTERNS.md`

Cross-app synthesis, one section per area. Each line should be checkable in a capture.

## Profile

### Everyone does (mandatory)
- Avatar at the top, name directly below it.
- Settings reachable from the profile, usually a top-right icon.
- One primary action (edit, share or follow) within the first screenful.

### Only the best do (differentiators)
- One number per stat, with a small label, in a single row of 2 to 3 items.
- Content tabs as a segmented control with the selected state shown by fill.
- Edit profile as a sheet that preserves the profile underneath.

### Everyone does badly (our chance)
- Empty states: a blank area with no hint of what will appear or how to start.
- Privacy of each item is hidden several levels deep.
- Dark mode often reuses light borders and loses hierarchy.

## Onboarding

### Everyone does (mandatory)
- Progress indicator visible on every step.
- Permission prompts come after the value is shown, not before.

### Only the best do (differentiators)
- Each step earns something the user can see right away (a preview, a first item created).

### Everyone does badly (our chance)
- No way back from the penultimate step without losing input.

## Decisions taken (convention vs deliberate break)
- Convention kept: avatar plus name stack at the top.
- Break on purpose: stats row replaced by a single streak card, because the product has one core number.
