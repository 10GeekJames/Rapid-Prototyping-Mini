Add the following note to your local IDE's llm instruction file:

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
- Avoid mix nested quotes issues
- Avoid path issues: 
    + BAD - C:\Users\Username\Project
    + GOOD - "%~dp0ProjectFolder"
- Use only standard ASCII characters (A-Z, a-z, 0-9, basic punctuation)
- Always install dependencies automatically (cheap and ensures consistency)
- Use port 8989 for all services, handle conflicts gracefully
- never nest the triple tick marks / code marks use a different symbol
- avoid complex chaining
    + Bat Examples: ```
    
    BAD - Complex chaining with nested quotes: 
    pushd Folder && echo "Starting" && npm start && popd

    GOOD - Clear, step-by-step approach: 
    if errorlevel 1 exit /b 1
        echo Starting application...
        npm start    
    if errorlevel 1 exit /b 1


## Code Standards
- Keep files under 400 lines
- Use clear, descriptive file names
- Single responsibility per file
- (always) Vanilla JavaScript ES6+ only (no frameworks for MVP)
- (always) Tailwind CSS + DaisyUI for styling
- (as needed) SQLite database (sqlite.db)
- (as needed) RESTful API under /api/ endpoints

## Quality Gates
- Test each feature before moving to the next
- Update requirements-document.md as features are completed
- Ensure run/stop scripts work on target platform
- Clean shutdown prevents orphaned processes
- All acceptance criteria must be met before marking complete
