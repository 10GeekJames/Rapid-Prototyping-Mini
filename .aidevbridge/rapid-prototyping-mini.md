

# Rapid Prototyping Mini Guide (User Preferences, Patterns, and LLM Rules)

This file documents the **unique rules, patterns, and preferences** that LLMs (Copilot/GPT) must follow for rapid prototyping in this repo. It is not a generic tech tutorial—focus on what makes this workflow unique, what to always do, and what to avoid.

## Core Principles & Preferences

- **Project structure and clarity are top priorities.**
- **All code must live in `/src/` inside a project folder.**
- **Frontend:** Vanilla JS, HTML, CSS, Tailwind CSS + DaisyUI (CDN only)
- **Backend:** Node.js (Express, single port 8989, use `server.js` in `/src/`)
- **Database:** SQLite (sqlite3, only if persistence is needed, all DB logic in `data/database.js`)
- **No unnecessary libraries or frameworks.**
- **Never use inline `<script>` or `<style>` tags.**
- **Split HTML, CSS, JS by feature/page/component.**
- **Keep files small, clear, and single-responsibility.**
- **Scripts:** Always generate `run.sh`, `stop.sh`, and Windows equivalents. Scripts must install dependencies, use port 8989, and clean up processes.
- **requirements-document.md** must always be in the project folder, never in repo root.
- **When making changes to models/data, update all layers (backend, frontend, DB, API).**
- **Remove unused code, files, and folders immediately.**
- **Refactor and improve existing code, don't duplicate.**
- **Build one clear pathway—no competing approaches.**
- **Document any non-obvious decisions or tradeoffs in requirements-document.md.**


## Serving Frontend & API with Node (Express)

When using Node (Express), always serve both your API endpoints and static frontend files (HTML, JS, CSS) from the same Express server, all on port 8989. This is the most common and scalable approach. Do not split frontend and backend into separate servers/ports unless there is a specific advanced requirement.

## Project Structure (Color-by-Number Template)

```
<sub-project>/
├── run.sh              # Cross-platform startup script
├── run.bat             # Windows startup script
├── stop.sh             # Cross-platform shutdown script
├── stop.bat            # Windows shutdown script
├── package.json        # Dependencies and scripts
├── requirements-document.md
├── src/
│   ├── index.html      # Main entry point
│   ├── frontend.js       # Frontend logic
│   ├── server.js       # Backend/API logic
|   ├── blogs/
|   │   ├── blog.html
|   │   ├── blog.js
|   │   └── blog.css
|   ├── surveys/
|   │   ├── survey.html
|   │   ├── survey.js
|   │   └── survey.css
|   ├── results/
|   │   ├── result.html
|   │   ├── result.js
|   │   └── result.css
│   ├── shared/         # Shared layouts, utilities, and components
│   │   ├── layout.html # Make sure this file exists and make sure all other pages share it, it handles any navigation, and uses the router.js to handle navigation
│   │   ├── layout.js
│   │   ├── layout.css
│   │   ├── router.js
│   │   └── storage.js
│   │   └── Navigation/
│   │       └── NavMenu.html
│   │       └── NavMenu.js
│   │       └── NavMenu.css
│   ├── {page}/         # Each feature/page in its own folder (html | js | css)
│   ├── {page}/{component}/   # Components for each page  (html | js | css)
│   ├── api/
│   │   ├── {database-name}.db # Actual database files
│   │   └── database.js     # Database logic (if needed)
```

### Path Handling for Node.js Projects
> **Tip:** All Node.js code in this project is always run from inside the `/src/` folder. When writing code that uses relative paths (e.g., `fs.readFileSync`, `require`, etc.), **do not prefix paths with `/src/`**. Assume the working directory is already `/src/`.

**Example:**

- Good: `require('./utils/helper.js')`
- Bad: `require('/src/utils/helper.js')`

This ensures portability and prevents path errors when running scripts or modules.

**How to use this:**
- Start with just `index.html` (the home page) and a folder for your first feature.
- The home page should always provide a full menu linking to all other pages/features.
- Every other page should include a simple "Back" button that returns the user to the home page (index.html).
- Add new folders for each feature/page as you grow.
- Only add `server.js` and `data/database.js` if you need persistence or backend logic.

## Change Propagation & Data Storage

- If you need to store information (e.g., form submissions), always create a backend using `server.js` and SQLite for persistence.
- When making changes to models, domains, or data structure, always update all layers: backend, frontend, database schema, and API endpoints.
- Rename files, folders, and update all references as needed to keep the project consistent and maintainable before moving on to new features.

## Script Rules (for LLMs)

- Scripts must work on Linux, Mac, and Windows.
- Always install dependencies automatically.
- Use port 8989 for all services.
- Store process IDs for clean shutdown.
- Stop scripts must force-kill anything on port 8989.
- No extended ASCII, no nested parentheses, plain ASCII only.
- Output must be clear and simple.

## File Organization & Cleanup

- Never use inline `<script>` or `<style>` tags in HTML files—always separate HTML, CSS, and JS.
- For each feature or page, create a folder and place separate `.html`, `.css`, and `.js` files inside.
- Do not combine multiple pages or features into a single HTML file.
- Remove unused code, files, and folders immediately.
- Refactor and improve existing code, don't duplicate.
- json files and json data cannot have code comments

## New Projects

- Always create `/project-name/` and `/project-name/src/` for new projects.
- Never put requirements-document.md in repo root.
- Avoid unnecessary libraries—use only trusted, minimal dependencies.

---
**This file is for user-specific rapid prototyping rules and patterns.**
