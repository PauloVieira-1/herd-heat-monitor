---
title: "Heat Stress Demo"
category: project
tags: [project]
---

# Heat Stress Demo

Live at **https://paulovieira-1.github.io/herd-heat-monitor/** (GitHub Pages, public repo `PauloVieira-1/herd-heat-monitor`). This folder is its own git repository: commit and push from here, and Pages redeploys within a minute. It is gitignored by the vault.

A one-page client demo of a system that predicts heat stress in dairy cows. It shows a herd of five cows, flags the one showing heat stress (cow 001), and explains why: each measurement, the limit it is checked against, whether it counts as a warning sign, and what the farmer should do.

## What is real and what is made up

- Cow 001's readings, limits and 80% confidence come from the team's spreadsheet mock-up (`Mock-up V1.xlsx`, 26 Sep 2026 09:10 reading).
- Cows 002–005, their names and the advice wording are invented for the demo. The spreadsheet only had placeholders such as "ADVICE for RESPIRATION RATE".
- Confidence is a simple count: each warning sign adds 20%, as in the spreadsheet (4 signs → 80%). The real system will use a trained model.
- Levels: under 50% normal, 50–69% watch, 70% and up heat stress.

## Measurements are taken outdoors

The cows are in the field, not a barn: the temperature is "Outdoor temperature" from a thermometer on location, and the advice talks about shade and water rather than fans.

## Editing

One hand-written `index.html`, no build step. The data lives in three arrays at the top of the script: `INPUTS` (measurements and limits), `ADVICE`, and `COWS` (readings per cow). Scores and levels are computed from them, so change a reading and the chart, banner-level colours and table follow. The banner text and summary tiles are written by hand and must be updated if cow 001 stops being the alert.
