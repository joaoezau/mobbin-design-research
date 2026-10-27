# Methods: flows, components and studying like a design director

## Flows: study journeys, not screenshots

Use when the question is "how do the best structure X?".

1. `search_flows` with the journey in one sentence ("onboarding with personalization and notification permission", "add a friend by username"). Name the app to see its flow ("<app> onboarding").
2. Compare 3 to 5 apps on the same flow, side by side. Note the shared skeleton: number of steps, what each step asks and gives, where friction is deliberate and where it disappears, and what each step IS (pushed screen, modal, sheet, overlay). Consistent presentation is part of the spec.
3. Journeys worth studying in almost any product: onboarding, paywall, welcome, notification and permission prompts, plus the product's own core flows.

## Components: how the best build a piece

When the question is about a component ("what should the tab bar / level picker / priority chip look like?"):

1. `search_screens` describing the piece and where it appears ("chat input recording voice message with live waveform", "bottom sheet with slider to choose intensity level").
2. Extract NUMBERS, not vibes: sizes, positions, item counts, labels, active state, what has an icon and what has text.
3. Then build in the design tool by reusing the components your design system already has. Never hand-draw what exists as a component; adapt the existing one to the new case.

## Study discipline

- **Question first.** Every pass answers a named question.
- **See everything, in order.** The journey is the unit of design; a sampled flow lies.
- **Across apps before within an app.** One app shows its taste; five show the grammar of the category. Divergence among the good ones is a real choice; convergence is a convention to break only on purpose.
- **Stop at saturation.** The question is answered when new screens stop changing the spec.
- **Project rules beat the reference.** Typography, icons, color roles, tokens, copy language and casing, and platform conventions come from your rules file, never from the app you are studying.
