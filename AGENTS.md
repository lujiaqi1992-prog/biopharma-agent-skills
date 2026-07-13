# Biopharma Agent Skills Router

This repository contains three reusable agent skills. Read only the skill relevant to the user's request.

## Routing

- When `innosight_mcp` is enabled and the user prioritizes depth, coverage, BD/CI decision quality, or explicitly requests InnoSight, read and follow `disease-area-research-innosight.md`. Do not silently downgrade if InnoSight is unavailable.
- For portable disease landscape research without a required InnoSight connector, read and follow `disease-area-research.md`.
- For pressure-testing a specific drug asset, indication expansion, me-too/best-in-class/first-in-class positioning, four-quadrant diligence, or a 90-day de-risking plan, read and follow `drug-asset-strategy-review.md`.

## Universal operating rules

- Treat tool names and connector schemas as environment-specific. Discover available capabilities before calling them; never invent a tool or parameter.
- Prefer current primary evidence and state the retrieval cutoff date.
- Separate verified facts, user-provided claims, reasonable inferences, and unknowns.
- Do not fabricate clinical results, regulatory status, patent status, deal terms, epidemiology, or competitor information.
- If a commercial data connector is unavailable, continue with authoritative public sources and disclose the coverage limitation.
- Exception: when using `disease-area-research-innosight`, follow its hard gate and stop or recommend the portable version if InnoSight is unavailable.
- Do not present the output as medical, legal, regulatory, investment, or formal FTO advice.
