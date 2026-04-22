Read CLAUDE.md first. Then ingest the source file at: $ARGUMENTS

Default mode is INTERACTIVE. Do not skip the discussion step.

Workflow:
1. Read the raw source file completely
2. Present key takeaways to the user: what's new, what's surprising, what contradicts existing wiki knowledge. Ask the user what to emphasize before proceeding. Do NOT skip this step unless the user explicitly says "batch mode".
3. Create wiki/sources/YYYY-MM-DD-slug.md using the template in templates/source-template.md — fill in ALL frontmatter fields
4. For each person, organization, publisher, tool, or book mentioned: check if an entity page exists in wiki/entities/. If yes, update it with new info from this source and increment sources_count. If no, create one using templates/entity-template.md
5. For each concept, theory, framework, or technique mentioned: check if a concept page exists in wiki/concepts/. If yes, update it. If no, create one using templates/concept-template.md
6. If this source contradicts anything in existing wiki pages, add a > [!warning] callout on both pages
7. Update wiki/index.md — add rows for all new pages
8. Append an entry to wiki/log.md in the format: ## [YYYY-MM-DD] ingest | Source Title
9. If this source significantly changes our understanding of any theme, update wiki/overview.md

Always use [[wiki-links]] when mentioning entities or concepts. Link generously. When linking to a page that doesn't exist yet, still use [[wiki-links]] — it becomes a "wanted page" visible in Obsidian's graph view.
