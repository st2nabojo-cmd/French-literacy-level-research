Read CLAUDE.md first. Then process all NEW files in raw/github/ that have not yet been ingested.

Workflow:
1. List all files in raw/github/
2. Read wiki/log.md to check which files have already been ingested (look for their filenames in log entries)
3. For each file NOT yet in the log:
   a. Determine the file type (PDF, markdown, text, etc.)
   b. Read and process it
   c. Run the full /ingest workflow: create source page, update entities, update concepts, flag contradictions, update index, update log
4. After processing all new files, output a summary: how many files were processed, what pages were created/updated
5. If any file could not be processed (e.g., binary format, corrupted), log it with a note explaining why

This command is designed to be run after the Obsidian Git plugin pulls new commits from collaborators.
