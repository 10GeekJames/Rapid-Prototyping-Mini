# Rapid Prototyping Framework Rules

## Core Instructions
- Thoroughly read and apply all guidance from the .aidevbridge folder
- Always reference requirements-document.md for project scope and acceptance criteria
- Follow the rapid-prototyping-mini.md workflow for 1-hour development sessions
- Use cursorrules-integration.md for code standards and patterns

## Development Principles
- Start with simple static files, add complexity only when needed
- Always clean up unused code, files, functions, and variables immediately
- Improve existing code rather than creating new files and methods
- Build one clear pathway through the system - avoid multiple approaches
- Remove legacy code instead of keeping it "just in case"

## Script Creation Rules
- Generate run.sh/run.bat and stop.sh/stop.bat for every project
- Never use emojis, extended ASCII, or special characters in scripts
- Avoid nested parentheses () inside other () - use different symbols
- Use only standard ASCII characters (A-Z, a-z, 0-9, basic punctuation)
- Always install dependencies automatically (cheap and ensures consistency)
- Use port 8989 for all services, handle conflicts gracefully

## Code Standards
- Keep files under 400 lines
- Use clear, descriptive file names
- Single responsibility per file
- Vanilla JavaScript ES6+ only (no frameworks for MVP)
- Tailwind CSS + DaisyUI for styling
- SQLite database (sqlite.db)
- RESTful API under /api/ endpoints

## Quality Gates
- Test each feature before moving to the next
- Update requirements-document.md as features are completed
- Ensure run/stop scripts work on target platform
- Clean shutdown prevents orphaned processes
- All acceptance criteria must be met before marking complete


## Development Workflow
- Always work to implement the users requests as completely and thuroughly as you can.  
- Do not stop to ask the user for interaction unless it is important.
- Continue further, even if you think you have completed the task, until you are sure you have done everything you can to satisfy the users request.
- If you are unsure about something, ask the user for clarification.
- If you are unsure about what the user wants, ask for clarification.
- Work with your built-in todo structure to make a great plan to implement the users request.
- Always work to make the users request as complete and thurough as you can.
- Work to complete all open todos before stopping
- Always create more todos if you think of more things to do