Read CLAUDE.md first. Then answer this question using the wiki: $ARGUMENTS

Workflow:
1. Read wiki/index.md to identify relevant pages
2. Read those pages in full
3. Synthesize an answer grounded in wiki content — cite sources using [[wiki-links]]
4. Choose the right output format for the question:
   - Markdown page for synthesis or analysis
   - Comparison table for "X vs Y" questions
   - Timeline for chronological questions
   - Slide deck (Marp format) if the user needs to present findings
   - Chart description if data visualization would help
   - Obsidian Canvas (.canvas JSON) for mapping relationships visually
5. If the wiki doesn't have enough information, say so clearly and suggest what sources to look for
6. After answering, ask: "Would you like me to save this answer as a new wiki page?" Explorations should compound in the knowledge base just like ingested sources do.
7. Append to wiki/log.md: ## [YYYY-MM-DD] query | Short description of the question
