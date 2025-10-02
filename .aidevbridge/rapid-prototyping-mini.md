# Rapid Prototyping Mini Guide

## 1-Hour Rapid Prototyping Session Framework

This guide enables successful rapid prototyping sessions using vanilla JavaScript, HTML5 Canvas, and modern web APIs. Perfect for pre-sales demonstrations and learning sessions.

## Core Stack (No Dependencies)
- build in /{Project}/src/ so users can have multiple ideas in one repo, /{Project}/src/(client | server | server/api | server/data)
- **Frontend**: Vanilla JavaScript ES6+, HTML5, CSS3
- **Styling**: Tailwind CSS + DaisyUI (CDN)
- **Backend**: Node.js with Express (single port 8989)
- **Database**: SQLite (sqlite.db) via the 'sqlite3' npm package (use 'sqlite3' for Node.js v22+ compatibility)
- **API**: RESTful endpoints under `/api/`


## Session Flow (60 minutes)

### Phase 1: Foundation (15 minutes)
1. **Project Setup & Scripts**
   - Create `run.sh` and `run.bat` for cross-platform execution
   - Create `stop.sh` and `stop.bat` for clean shutdown
   - Generate and maintain `package.json` or `project.csproj` or whatever this projects equivellent is with necessary dependencies
   
2. **Blank Canvas Setup**
   - Create `index.html` with Tailwind + DaisyUI CDN
   - Add input form with large display area
   - Implement localStorage persistence
   - Test refresh behavior

### Phase 2: Navigation (10 minutes)
3. **Add Navigation Menu**
   - Create simple nav with "Home" and "Blog" pages
   - Implement client-side routing
   - Keep home page functionality intact

### Phase 3: Content Creation (15 minutes)
4. **Blog Page Development**
   - Create blog entry form
   - Add blog post display
   - Use AI assistance to generate sample content
   - Implement basic CRUD operations

### Phase 4: Backend Integration (20 minutes)
5. **Server Setup**
   - Create Express server on port 8989
   - Set up SQLite database
   - Implement `/api/` endpoints
   - Connect frontend to backend
   - Test full-stack functionality

## Development Principles

### File Organization

#### Progressive Architecture
Start with simple static files and only add complexity when needed. Many projects will never need more than HTML, CSS, and JavaScript files. Only add server-side code, APIs, and databases when the project actually requires them. Build one clear pathway through the system rather than creating multiple approaches.

#### Code Cleanup Rules
- **Remove unused code**: Always delete files, folders, functions, methods, and variables that are no longer used
- **Improve existing files**: Enhance current code rather than creating new files and methods
- **Single pathway**: Build one clear path through the system - don't create alternative approaches
- **No legacy code**: Don't keep old code "just in case" - clean it up immediately
- **Refactor, don't duplicate**: Improve existing code instead of creating new versions
```
{project}/
├── run.sh              # Cross-platform startup script
├── run.bat             # Windows startup script
├── stop.sh             # Cross-platform shutdown script
├── stop.bat            # Windows shutdown script
├── package.json        # Dependencies and scripts
├── requirements-document.md
├── src/
│   ├── index.html
│   ├── css/
│   │   └── styles.css
│   └── js/
│       ├── main.js
│       ├── router.js
│       ├── api.js
│       └── storage.js
└── server/
    ├── index.js
    └── database.js
```

### Code Standards
- **Single Responsibility**: One purpose per file
- **Small Files**: Keep files under 400 lines
- **Clear Naming**: File names tell the story
- **Modular Design**: Easy to extend and modify

### AI Collaboration Rules
1. **Ask for Help**: Use AI for code generation, debugging, and optimization
2. **Iterate Quickly**: Make small changes, test frequently
3. **Document Decisions**: Update requirements-document.md as you go
4. **Stay Focused**: Complete one feature before starting the next

## Cross-Platform Script Generation

### AI Assistant Instructions for Script Creation

When creating any project, the AI assistant must generate `run.sh`/`run.bat` and `stop.sh`/`stop.bat` files that:

#### Run Scripts Must:
- **Detect the project type** by examining existing files (package.json, requirements.txt, go.mod, Cargo.toml, etc.)
- **Detect the operating system** and available tools
- **Install dependencies automatically** using the appropriate package manager
- **Start the appropriate server/service** for the detected project type
- **Use port 8989** for all services
- **Store process ID** for clean shutdown
- **Provide clear feedback** about what's happening

#### Stop Scripts Must:
- **Find and terminate** the running process (using stored PID or port detection)
- **Clean up any temporary files** or processes
- **Provide confirmation** that services have stopped
- **Handle cases** where no process is running

#### Smart Detection Rules:
- **Project Type**: Examine project files to determine language/framework
- **Environment**: Detect OS (Windows, Mac, Linux) and available tools
- **Dependencies**: Use appropriate package manager (npm, pip, go, cargo, etc.)
- **Server**: Start the correct server for the project type
- **Port Management**: Always use port 8989, handle conflicts gracefully

#### Cross-Platform Considerations:
- **Windows**: Use `.bat` files with `start /b` for background processes
- **Unix/Linux/Mac**: Use `.sh` files with `&` for background processes
- **Process Management**: Store PIDs in `.pid` file for clean shutdown
- **Error Handling**: Check for port conflicts and running processes
- **Dependency Installation**: Always run install commands (they're cheap and ensure consistency)

#### Script Creation Rules:
- **No Extended ASCII**: Never use emojis, special characters, or extended ASCII
- **No Nested Parentheses**: Avoid `()` inside other `()` - use different symbols like `[]` or `{}`
- **Plain Text Only**: Use only standard ASCII characters (A-Z, a-z, 0-9, basic punctuation)
- **Cross-Platform Compatibility**: Scripts must work on Windows, Mac, and Linux
- **Clear Output**: Use simple, clear messages without decorative characters

### Script Integration with Development

#### Pre-Development Checklist
- [ ] `run.sh` and `run.bat` created and tested
- [ ] `stop.sh` and `stop.bat` created and tested
- [ ] Scripts handle dependency installation
- [ ] Scripts work on target platform
- [ ] Clean shutdown functionality verified

#### During Development
- [ ] Use `./run.sh` or `run.bat` to start development
- [ ] Use `./stop.sh` or `stop.bat` to stop services
- [ ] Scripts automatically install new dependencies
- [ ] Port conflicts are handled gracefully
- [ ] Process cleanup works correctly

#### Post-Development
- [ ] All scripts work on target platform
- [ ] Dependencies install correctly
- [ ] Services start and stop cleanly
- [ ] No orphaned processes
- [ ] Documentation includes script usage

## Success Patterns

### Form Handling
```javascript
// Consistent form pattern
const form = document.getElementById('myForm');
form.addEventListener('submit', async (e) => {
    e.preventDefault();
    const data = new FormData(form);
    const result = await api.post('/api/endpoint', data);
    // Handle response
});
```

### API Integration
```javascript
// Standard API client
const api = {
    async get(url) {
        const response = await fetch(`/api${url}`);
        return response.json();
    },
    async post(url, data) {
        const response = await fetch(`/api${url}`, {
            method: 'POST',
            headers: { 'Content-Type': 'application/json' },
            body: JSON.stringify(data)
        });
        return response.json();
    }
};
```

### Database Patterns
```javascript
// SQLite with sqlite3 (Node.js v22+ compatible)
const sqlite3 = require('sqlite3').verbose();
const db = new sqlite3.Database('sqlite.db');
db.run(`
    CREATE TABLE IF NOT EXISTS posts (
        id INTEGER PRIMARY KEY,
        title TEXT,
        content TEXT,
        created_at DATETIME DEFAULT CURRENT_TIMESTAMP
    )
`);
```

## New projects
- Create /{project-name}/ and  /{project-name}/src folders and work in there when creating a brand new project, ask the user if you are not 100% sure that is what they want to do.
- Continually avoid adding any unnecessary libraries, only ever suggest or use very trusted libraries

## Quality Gates

### Before Moving to Next Phase
- [ ] Current feature works end-to-end
- [ ] No console errors
- [ ] Data persists across refreshes
- [ ] UI is responsive and clean
- [ ] Code is organized and readable
- [ ] Run scripts work on target platform
- [ ] Stop scripts clean up processes properly

### Final Session Checklist
- [ ] All requirements from requirements-document.md completed
- [ ] Full-stack functionality working
- [ ] Database properly seeded
- [ ] API endpoints documented
- [ ] Code is clean and well-organized
- [ ] Run/stop scripts work on all target platforms
- [ ] Dependencies install automatically
- [ ] Clean shutdown prevents orphaned processes

## Troubleshooting

### Common Issues
1. **CORS Errors**: Ensure server allows frontend origin
2. **Database Locked**: Check for multiple connections
3. **Port Conflicts**: Verify port 8989 is available
4. **File Paths**: Use relative paths, avoid absolute paths

### AI Prompting Tips
- Be specific about what you want to build
- Ask for code examples, not just explanations
- Request error handling and edge cases
- Ask for optimization suggestions
- Request run/stop scripts for your specific environment
- Ask for cross-platform compatibility when needed

## Extension Ideas

### After Core Functionality
- Add user authentication
- Implement real-time updates
- Add file upload capabilities
- Create admin dashboard
- Add search functionality
- Implement data export

### Production Considerations
- Add input validation
- Implement error boundaries
- Add loading states
- Create proper error messages
- Add accessibility features
- Implement security headers

## Learning Outcomes

By the end of this session, participants will understand:
- Modern JavaScript development patterns
- Full-stack application architecture
- Database design and integration
- API design principles
- AI-assisted development workflows
- Rapid prototyping methodologies

This framework ensures successful, educational, and impressive rapid prototyping sessions that demonstrate the power of modern development practices.
