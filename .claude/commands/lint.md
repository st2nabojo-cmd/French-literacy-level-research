Read CLAUDE.md first. Then perform a full health check of the wiki.

Check for:
1. **Contradictions** — scan all source pages for key_claims that conflict with each other. Report each pair.
2. **Orphan pages** — wiki pages that have NO inbound [[wiki-links]] from any other page
3. **Wanted pages** — [[wiki-links]] that point to pages that don't exist yet. Prioritize any wanted page linked from 2+ existing pages — these are where the wiki most wants to expand. List them and suggest which should be created first.
4. **Stale content** — entity or concept pages whose last_updated date is older than the most recent source that mentions them
5. **Missing cross-references** — entity or concept names that appear in page body text but are not wrapped in [[wiki-links]]
6. **Broken frontmatter** — pages missing required YAML fields as defined in CLAUDE.md
7. **Research gaps** — themes from wiki/overview.md that have fewer than 2 sources. Suggest what to look for.
8. **Tag consistency** — tags used in frontmatter that are not in the approved list in CLAUDE.md

Then go further — suggest research directions:
9. **New questions** — propose questions to investigate based on patterns or tensions in existing knowledge
10. **Source suggestions** — recommend specific types of sources to seek (e.g., "We have opinions on AI writing quality but no empirical studies comparing AI vs human text for children — look for peer-reviewed papers on this")
11. **Under-represented themes** — identify themes from wiki/overview.md that are weakly covered relative to others

Output a structured markdown report. For each issue, state:
- What the issue is
- Which files are affected
- Suggested fix

Offer to fix structural issues automatically after the user reviews the report.

Append to wiki/log.md: ## [YYYY-MM-DD] lint | Health check performed — N issues found, M research suggestions
