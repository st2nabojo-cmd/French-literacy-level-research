Read CLAUDE.md first. Then save the last query answer as a new wiki page.

Workflow:
1. Take the content from the most recent /query response
2. Determine the best location: wiki/concepts/ if it's a concept synthesis, wiki/comparisons/ if it's a comparison, wiki/sources/ if it references a specific source
3. Create proper frontmatter according to CLAUDE.md conventions
4. Add [[wiki-links]] to all mentioned entities and concepts
5. Update wiki/index.md with the new page
6. Append to wiki/log.md: ## [YYYY-MM-DD] save | Saved query answer as wiki/path/page-name.md
