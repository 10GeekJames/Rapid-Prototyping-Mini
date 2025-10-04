
## PATH CONTRACT (MUST FOLLOW)
- All generated files MUST live under `/{project-name}/` (or its subfolders).
- If no path is specified, ASSUME `/{project-name}/`.
- Do NOT create or modify files at repository root. Ever.
- When responding, FIRST print a file plan (paths + filenames), THEN the content.



# AI DevBridge Index (Medium-Level Router)

**For LLMs and humans:** This file is your quick reference and router for all rapid prototyping and requirements management rules. Always read this file and the two detailed guides below into memory before starting work.

## Quick Links
| What you need              | Where to look                        |
|---------------------------|--------------------------------------|
| Project structure         | rapid-prototyping-mini.md            |
| Requirements format/rules | requirements-management.md           |
| Code/database/scripts     | rapid-prototyping-mini.md            |
| Rules summary             | aidevbridge-index.md                 |

**Always read these files into memory:**
- `.aidevbridge/rapid-prototyping-mini.md`
- `.aidevbridge/requirements-management.md`



## Key Principles (see detailed guides for full rules)
- Break HTML, CSS, and JS into separate files, organized by feature/page/component.
- Never use inline `<script>` or `<style>` tags.
- Use the color-by-number folder structure as your project grows. (See rapid-prototyping-mini.md)
- Place all code in `/src/` inside the project folder (never at repository root).
- Use SQLite for persistence if needed; keep all DB logic in `data/database.js`.
- requirements-document.md must always be in the project folder, never in repository root.
- Keep requirements-document.md up to date and reference it for all scope and acceptance criteria.


## How to Use This Repository
- Start with `copilot-instructions.md` for a high-level overview and links to these guides.
- Use this file as your quick reference for the most important rules and where to find details.
- For all detailed rules, patterns, and examples, see:
    - `.aidevbridge/rapid-prototyping-mini.md` (project structure, workflow, code/database/testing patterns)
    - `.aidevbridge/requirements-management.md` (requirements, backlog, acceptance criteria)

## Why This Structure?
- Consistency and clarity across all projects
- Easy onboarding for new contributors
- Rapid, high-quality prototyping
- Maintainable, scalable codebases

**If in doubt, start at the top and work your way down for more detail.**

# LLM Instructions for Rapid Prototyping

**For LLMs:** Always follow these rules and route to the detailed guides for specifics. If you are unsure, ask for clarification or infer the most maintainable default and document your assumption.




## AI Instructions (Bulleted Summary)

- When starting a new project:
    - Check for requirements-document.md in the project folder (never repository root)
    - If missing, create one using the template from requirements-management.md
    - Ask the user for initial requirements before generating code
    - Review existing requirements before making changes
    - Follow the rapid-prototyping-mini.md workflow for development

- When implementing features:
    - Reference requirements-document.md for scope and acceptance criteria
    - Follow file organization patterns from rapid-prototyping-mini.md
    - Use the code standards and patterns provided (see detailed guide)
    - Update requirements-document.md with progress
    - Use Tailwind CSS and DaisyUI for styling; ensure responsive UI and shared layout
        + <link href="https://cdn.jsdelivr.net/npm/daisyui@4.4.19/dist/full.min.css" rel="stylesheet" type="text/css" />
        + <script src="https://cdn.tailwindcss.com"></script>

- When managing requirements:
    - Use the format specified in requirements-management.md
    - Keep requirements specific and testable
    - Update status as features are completed
    - Add new requirements as scope evolves
    - Maintain clarity and consistency

## Never do this (Critical Don’ts)
- Never create or modify files at repository root (except top-level docs).
- Never put requirements-document.md in repository root.
- Never use inline `<script>` or `<style>` tags in HTML.
- Never add libraries or frameworks unless specifically requested or absolutely necessary.
- Never combine multiple features/pages into a single HTML file.

# For all code, API, database, and testing patterns, see `.aidevbridge/rapid-prototyping-mini.md`.

# For requirements management, see `.aidevbridge/requirements-management.md`.


# For all code, API, database, and testing patterns, see `.aidevbridge/rapid-prototyping-mini.md`.

# For requirements management, see `.aidevbridge/requirements-management.md`.