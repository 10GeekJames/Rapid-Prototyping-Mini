---
applyTo: "**"
---
# Core Instructions
- Always read and follow `copilot-instructions.md` and any files that are reference there
- Thoroughly read and apply all `*.md` guidance from the `.aidevbridge` folder.
- Always reference `requirements-document.md` for project scope and acceptance criteria.
- Follow the `rapid-prototyping-mini.md` workflow for 1-hour development sessions.
- Use `cursorrules-integration.md` for code standards and patterns.

# Rapid Prototyping Framework Rules

## Core Instructions
- Thoroughly read and apply all guidance from the `.aidevbridge` folder.
- Always reference `requirements-document.md` for project scope and acceptance criteria.
- Follow the `rapid-prototyping-mini.md` workflow for 1-hour development sessions.
- Use `cursorrules-integration.md` for code standards and patterns.

## Development Principles
- Start with simple static files; add complexity only when needed.
- Clean up unused code, files, functions, and variables immediately.
- Improve existing code rather than creating new files and methods when possible.
- Build one clear pathway through the system—avoid multiple competing approaches.
- Remove legacy or dead code instead of keeping it "just in case." If unsure, document the reason for keeping code.

## Script Creation Rules
- Generate `run.sh`/`run.bat` and `stop.sh`/`stop.bat` for every project. On Linux/macOS, set executable permission when needed: `chmod +x ./run.sh ./stop.sh`.
- Never use emojis, extended ASCII, or special characters in scripts; use plain ASCII only.
- Avoid nested parentheses inside parentheses—use alternative structures or clearer control flow.
- Avoid mixing nested quotes; prefer consistent quoting patterns to prevent shell parsing issues.
- Avoid path issues: prefer portable patterns.
    - BAD: `C:\Users\Username\Project`
    - BETTER (batch): `"%~dp0ProjectFolder"` — use location tokens appropriate to the shell.
- Use only standard ASCII characters (A-Z, a-z, 0-9, basic punctuation).
- Always install dependencies automatically in scripts to ensure reproducible environments.
- Use port 8989 for local services by default; handle conflicts gracefully (e.g., detect free port, allow override via env var).
- Never nest triple-backtick fences inside scripts or documentation; use alternate markup or quoting when required.
- Avoid complex command chaining in scripts. Prefer clear step-by-step logic and explicit error checks.
    - BAD (complex chaining): `pushd Folder && echo "Starting" && npm start && popd`
    - GOOD (clear flow):
        1. `pushd Folder` or change directory explicitly and check the return code.
        2. `echo "Starting application..."`.
        3. `npm install` (if needed) then `npm start` and check for errors after each step.
        4. `popd` or return to previous directory, with explicit error handling.

## Code Standards
- Keep files under 400 lines where practical; split responsibilities across files when needed.
- Use clear, descriptive file names.
- Single responsibility per file or module.
- Vanilla JavaScript (ES6+) only for MVP code—avoid frameworks for initial prototypes.
- Use Tailwind CSS + DaisyUI for styling when building UIs for consistency with the framework.
- Use SQLite (`sqlite.db`) when lightweight, file-based persistence is needed.
- Provide RESTful APIs under `/api/` endpoints for server components; keep them small and well-documented.

## Quality Gates
- Test each feature before moving to the next; use small, fast tests suitable for rapid iteration.
- Update `requirements-document.md` as features are completed to keep scope and acceptance criteria current.
- Ensure `run`/`stop` scripts work on the target platform and perform clean shutdowns to avoid orphaned processes.
- All acceptance criteria specified in `requirements-document.md` must be met before marking a feature or project complete.

## Development Workflow
- Always work to implement the user's requests as completely and thoroughly as possible within the session scope.
- Do not stop to ask the user for interaction unless it is important or clarification is required.
- If unsure about requirements, ask a concise clarifying question; otherwise infer reasonable defaults and document assumptions.
- Use the built-in todo structure (or project task tracker) to plan and execute work in small, verifiable steps.
- Complete open todos before stopping and create follow-up todos when new work is discovered.

## Script and Project Practicals (examples and conventions)
- Default service port: `8989`. Allow override through an environment variable, e.g., `PORT`.
- Example guard in shell scripts: exit immediately on failed commands and print helpful errors.
    - `set -euo pipefail` (use in POSIX-compatible shells to help detect errors early).
- When creating batch files for Windows, use clear stepwise commands and explicit errorlevel checks.

## Notes on Documentation and Maintainability
- Keep documentation close to code: small READMEs, inline comments, and a top-level `requirements-document.md`.
- When keeping non-obvious decisions or code, add a short comment explaining why it remains.

## Always
- Read through the `.aidevbridge` folder thoroughly and follow the policies and patterns inside.
