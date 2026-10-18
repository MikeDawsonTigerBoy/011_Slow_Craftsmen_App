# 011 Slow Craftsman

A logbook for slow crafts. Each loaf of sourdough and each carved spoon gets its own record of photos, measurements and outcomes, so you can see which variables made the difference.

> **Draft for review.** Lines tagged *(proposed)* are Claude's suggestions, not yet agreed. Section 10 lists the questions to settle before the first proper build.

## Status

**Focus: parked.** Not one of the featured prototypes for now. The featured three are 001, 002 and 004.

Working prototype, built as a single-file web app (`index.html`). It was originally published as a Claude artifact.

## 1. Problem statement

Sourdough and spoon carving both improve through many small adjustments: hydration, starter strength and timing for bread; wood, grain, tools and technique for spoons. Most makers keep no record, or keep scattered photos and notes. Without a record, a good loaf can't be reproduced and a bad one can't be explained.

## 2. Target audience

- **Primary:** Mike, as a home baker and spoon carver.
- **Secondary** *(proposed)*: hobby makers who already photograph their work and want a structured log, rather than a social feed.

## 3. Value proposition

Every loaf and every spoon becomes a data point. It has photo evidence at the stages that matter and the variables that were used, so you can learn from your own practice.

## 4. Core functionality

**Bread**
- Choose a bread type, each with its own formula and hydration range.
- Track the starter: New, then Day 1, 2 and 3 feeds, then ready to mix, with an activity level.
- Scale by number of loaves and dough weight, and adjust the ratios (hydration, levain, salt).
- Step-by-step bake timeline with timers for mixing, folding and baking.
- Photo evidence at each crucial stage.
- Reminders and alarms on the phone for each step.

**Spoon carving**
- One record per spoon, holding the wood, the stage (Blank to Oiled) and progress photos.
- Tools and their maintenance.
- A link to the spoon's OneDrive photo folder.
- Overall dimensions, which later feed a Revit model of the piece.

## 5. Key user journeys

1. **Bake:** pick a bread and batch size, start the bake, follow each step's timer, take a photo at the checkpoints, then log the outcome.
2. **Starter:** feed it, log the rise with a photo, and see when the next feed is due.
3. **Carve:** start a spoon, add photos as it moves through each stage, enter dimensions, then link the model.
4. **Look back:** compare past bakes or spoons to see what changed.

## 6. Non-goals

- No social feed, followers or likes.
- No recipe marketplace or shop *(proposed)*.
- Not a general crafts platform in version 1. It covers bread and spoons only *(proposed)*.

## 7. Feasibility

- The prototype already covers most of the core functionality.
- **Harder parts:**
  - Real phone alarms and reminders need a native app or a notification service.
  - OneDrive needs Microsoft Graph sign-in.
  - Revit needs either a Revit add-in or a manual export.

## 8. Assumptions and risks

- **Assumption:** taking photos at checkpoints doesn't feel like a chore mid-bake, with floury hands.
- **Assumption:** the suggested schedule times are close enough to be useful. Real fermentation depends on temperature.
- **Risk:** linking to Revit adds a lot of build effort for a niche benefit.

## 9. Success metrics

*(proposed)*
- Mike logs at least 80% of his bakes for two months.
- After 10 bakes, at least one change to the recipe can be explained by looking at the logged data.
- At least one spoon is logged from blank to oiled with complete photos.

## 10. Open questions and challenges

1. **Why are bread and spoons in one app?**
   - The connecting idea is "slow craft". If that's the identity, the app might be one logbook engine with craft templates, so it's ready for a third craft.
   - If it isn't, two separate apps would be simpler.
2. **Why Revit for a spoon?**
   - A spoon is an organic, freeform object. Revit is built for parametric buildings and handles this kind of form poorly. Rhino, Blender or a photogrammetry scan would model it better.
   - Is the goal a usable model, or a portfolio link that shows Revit work alongside craft?
3. **What does "insights gained" actually mean?**
   - Without a defined comparison view (for example, hydration against crumb photos), the data gets collected and never used.
4. **How does temperature fit in?**
   - Kitchen temperature drives fermentation timing more than anything else. Should version 1 log it?
5. **Phone app or web app?**
   - Alarms and the camera both point towards Expo, the portfolio's default format.

## 11. Tech approach

- **Now:** the prototype is one HTML file. Its data sync and photo uploads use the Claude artifact runtime (`window.claude`). Opened anywhere else, it saves data in the browser on that device only.
- **Next** *(proposed)*: Expo (React Native), matching the portfolio standard, with a small backend for data and photos.

## 12. Roadmap

- **v0 (done):** single-file prototype covering formulas, starter, timed bake steps with photo checkpoints, the spoon log and tools.
- **v1:** phone app with real notifications and photo storage.
- **Later:** OneDrive folder sync, Revit model link, and views that compare variables against outcomes.

## Running it

Open `index.html` in a browser.
