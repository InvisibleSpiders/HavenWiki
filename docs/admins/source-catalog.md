# Source Catalog

`sources.yml` is the shared catalog for modules that need item, block, mob, XP, and income groupings.

## Why It Exists

Instead of repeating long material lists in every module, modules can refer to source categories. Storage uses these categories to keep module config cleaner, and professions can use the same style of source data for XP and income values.

## Categories

Categories can include:

- Explicit materials, blocks, or mobs.
- Built-in tags.
- Base XP values or XP ranges.
- Base income values or income ranges.
- Per-material or per-mob overrides.

This lets a category define a broad baseline while still making rare items or dangerous mobs worth more.

## Custom Categories

Admins can add custom categories to `sources.yml`. A custom category is not restricted to the premade list, as long as the module consuming it is configured to reference that category ID.

## Multipliers

Modules can still apply their own multipliers on top of source values. For example, professions can reduce normal-world XP, increase frontier XP, or apply main/hobby rates after the source value is resolved.

## Storage Usage

Storage categories can reference one or more source categories through `source-categories`. That keeps storage category definitions compact while still allowing broad item coverage.

