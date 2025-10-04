# Rapid Prototyping Framework

This repository defines a **pyramid of guidance** for rapid prototyping projects.  
Always start here, then follow the linked files for increasing detail.

## Pyramid Structure
1. **README.md** — high-level overview (this file).
2. **.aidevbridge/aidevbridge-index.md** — quick-reference index and essential rules.
3. **.aidevbridge/rapid-prototyping-mini.md** — full technical guide: file structures, scripts, coding patterns.
4. **.aidevbridge/requirements-management.md** — requirements and backlog rules.

If in doubt, start at the top and go deeper as needed.

---

## Core Rules

- **Path Contract**  
  - All generated files must live inside `/{project-name}/` or its subfolders.  
  - Never create or modify files at repository root.  
  - Always create a `requirements-document.md` in each project folder (e.g., `/{project-name}/requirements-document.md`), never at repository root.
  - The file `.aidevbridge/requirements-management.md` is the instructions for crafting requirements-document.md files and always lives in `.aidevbridge/`.

- **Workflow**  
  - Reference the `requirements-document.md` in your current project folder for scope and acceptance criteria.  
  - Follow the step-by-step flow in `rapid-prototyping-mini.md` for development.  
  - Keep requirements updated as features are delivered.

- **Development Principles**  
  - Start with the simplest possible files (HTML, CSS, JS). Add backend, API, and database only when needed.  
  - Separate HTML, CSS, and JS into dedicated files per feature/page. No inline `<script>` or `<style>`.  
  - Use Tailwind CSS(https://cdn.tailwindcss.com) + DaisyUI (https://cdn.jsdelivr.net/npm/daisyui@4.4.19/dist/full.min.css) for styling.
  - SQLite is the default persistence layer.  
  - Default service port is `8989` (override with `PORT` env var).  
  - Any and all services, server, api, client all run on the same 8989 port organized in a single project

- **Code & Quality Standards**  
  - One responsibility per file, keep files small (<400 lines).  
  - Clean up unused code immediately; refactor rather than duplicate.  
  - Test each feature before moving on.  
  - Generate and maintain `run.sh` / `stop.sh` and `run.bat` / `stop.bat` for every project.  

---

## Where to Go Next

- **Quick rules & routing:** [.aidevbridge/aidevbridge-index.md](.aidevbridge/aidevbridge-index.md)  
- **Technical handbook:** [.aidevbridge/rapid-prototyping-mini.md](.aidevbridge/rapid-prototyping-mini.md)  
- **Requirements & backlog instructions:** [.aidevbridge/requirements-management.md](.aidevbridge/requirements-management.md)  

---

## Always
- Keep documentation close to code.  
- Maintain clarity in structure, naming, and requirements.  
- Build one clear path through the system — avoid competing approaches.  
- Ask for clarification only when essential; otherwise infer defaults and document assumptions.  
- **Remember:** `requirements-document.md` files live in each project folder, while `.aidevbridge/requirements-management.md` is the global instructions file for crafting them.
