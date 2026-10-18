# Slow Craftsman

A logbook for sourdough baking and spoon carving: capture progress, photo evidence and outcomes per loaf and per spoon, so the variables can be understood over time.

**Status:** early prototype, built as a single-file web app (`index.html`).

## Bread
- **Formula** – six bread types (country, high-hydration, whole wheat, 70% rye, focaccia, sandwich tin). Adjustable hydration, levain and salt; scale by loaf count and dough weight. Grams from baker's percentages, with a levain build.
- **Starter** – New → Day 1 → Day 2 → Day 3 → Ready to mix. Log feeds with ratio, rise and photo; next-feed countdown.
- **Bake** – timed step timeline with photo checkpoints at the crucial stages; finished bakes go to a log.

## Spoon carving
- **Spoons** – wood, stage tracker (Blank → Oiled), stage-tagged progress photos, overall dimensions (mm), Revit model link, OneDrive folder link.
- **Tools** – maintenance tasks with intervals and due status.

## Notes
- The prototype was built as a Claude artifact. Its data sync and photo uploads use the Claude artifact runtime (`window.claude`); opened anywhere else, `index.html` falls back to saving data in the browser on that device.
- Phone alarms/reminders and OneDrive photo sync are not built yet.
