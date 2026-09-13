---
name: publish-work-items-to-linear
description: Publish standalone Markdown work items to a user-selected Linear project and team when the connected Linear MCP server supports the required operations.
---

# Publish Work Items to Linear

Publish local work items only after the user selects a resolved Linear project and team. Do not alter local artifacts.

## Select the destination

1. Before any Linear write, discover the available Linear MCP tools and use their documented read-only lookup capabilities to list the teams and projects available to the connected user. Do not infer a destination from the repository, current Linear context, or previous publishing activity.
2. Present the available destinations to the user, including each team's name and identifier and each project's name, identifier, and associated team when available. Ask the user to select one project and one team from those results.
3. Resolve the user's selections against the discovered results. If a selection is missing, unavailable, ambiguous, or the project does not belong to the selected team, ask the user to choose again from the available results. Do not publish until both are resolved unambiguously.

## Discover and preflight

1. Recursively discover local `work-item.md` files. Each file is a publishable item. Process items in stable, lexicographic path order.
2. Before creating or reusing an issue, confirm that the connected Linear capabilities can:
   - search issues scoped to the resolved project and team; and
   - create an issue in that project and team with the resolved team's Backlog state.
3. If any capability is unsupported, unavailable, or cannot be confirmed, report the limitation and stop before creating or changing any Linear issue.

## Publish

For each work item:

1. Read `work-item.md`. Use its first Markdown H1 as the issue title. Use all content after that H1 unchanged as the issue description. Do not add implementation details, local paths, or other commentary.
2. Search for an existing issue within the resolved project and team. Reuse one only when the title and supplied work-item content make the match unambiguous.
3. Otherwise, create an issue in the resolved project and team's Backlog state.

Do not create subissues or modify existing issue content.

## Report

Report each processed Linear issue identifier and title, and whether it was created or reused. Also report any failure that stopped publishing.
