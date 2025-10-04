# LLM Instructions for Rapid Prototyping

## Overview

This document provides instructions for integrating rapid prototyping capabilities into your Cursor Rules or Copilot Instructions. It references the companion files in the same directory and provides additional helpful instructions for AI assistants.

## Integration Instructions

### Rapid Prototyping Framework

#### Core Files
- `rapid-prototyping-mini.md` - Complete guide for 1-hour rapid prototyping sessions
- `requirements-management.md` - Instructions for managing requirements-document.md files
- `cursor-copilot-instructions.md` - This integration guide

#### Development Principles
- Vanilla JavaScript ES6+ only (no frameworks for MVP)
- HTML5 Canvas 2D API for rendering
- Single port 8989 for all services, static site and api
- SQLite database (sqlite.db)
- RESTful API under /api/ endpoints
- Tailwind CSS + DaisyUI for styling

#### File Organization
- Keep files under 400 lines
- Use clear, descriptive file names
- Organize by feature, not by file type
- Maintain single responsibility per file
- Don't add folders and files that arne't needed or used yet

#### AI Collaboration Rules
- Always reference requirements-document.md
- Update requirements as features are added
- Test each feature before moving to the next
- Ask for help with complex implementations
- Document decisions and rationale


## Additional AI Instructions

### When Starting a New Project
1. **Check for requirements-document.md** in the project root
2. **If missing, create one** using the template from requirements-management.md and ask the user to give you initial requirements before starting to generate code
3. **Review existing requirements** before making changes
4. **Follow the rapid-prototyping-mini.md** workflow for development

### When Implementing Features
1. **Reference the requirements-document.md** for scope and acceptance criteria
2. **Follow the file organization patterns** from rapid-prototyping-mini.md
3. **Use the code standards** and patterns provided
4. **Test against acceptance criteria** before marking complete
5. **Update requirements-document.md** with progress
6. **Routing and Navigation**: Assume the application will be run in the project folder root. Use relative paths for all file references.
7. **Layout, Styling, and Navigation**: Use Tailwind CSS and DaisyUI for all styling. Ensure the UI is responsive and works well on different screen sizes.  Update any navigation menu as needed.  Ensure there is a common/shared layout for all pages.

### When Managing Requirements
1. **Use the format** specified in requirements-management.md
2. **Keep requirements specific and testable**
3. **Update status** as features are completed
4. **Add new requirements** as scope evolves
5. **Maintain clarity** and consistency

## Enhanced Development Workflow

### Pre-Development Checklist
- [ ] Requirements-document.md exists and is current
- [ ] Project structure follows rapid-prototyping-mini.md guidelines
- [ ] All dependencies are minimal and necessary
- [ ] Development environment is ready
- [ ] AI assistant understands the project scope

### During Development
- [ ] Reference requirements-document.md frequently
- [ ] Follow the file organization patterns
- [ ] Use the provided code standards
- [ ] Test each feature thoroughly
- [ ] Update requirements as needed
- [ ] Ask for help when stuck

### Post-Development
- [ ] All acceptance criteria are met
- [ ] Requirements-document.md is updated
- [ ] Code is clean and well-organized
- [ ] All features work end-to-end
- [ ] Documentation is complete

## Code Quality Standards

### JavaScript Standards
```javascript
// Use modern ES6+ features
const api = {
    async get(url) {
        const response = await fetch(`/api${url}`);
        return response.json();
    }
};

// Keep functions small and focused
function validateForm(formData) {
    // Single responsibility
    return formData.email && formData.email.includes('@');
}

// Use clear variable names
const userInput = document.getElementById('userInput');
const submitButton = document.getElementById('submitButton');
```

### HTML Standards
```html
<!-- Use semantic HTML -->
<main>
    <section id="userInput">
        <form id="inputForm">
            <label for="userText">Enter your text:</label>
            <input type="text" id="userText" required>
            <button type="submit">Submit</button>
        </form>
    </section>
</main>

<!-- Include Tailwind and DaisyUI -->
<link href="https://cdn.jsdelivr.net/npm/daisyui@4.4.19/dist/full.min.css" rel="stylesheet" type="text/css" />
<script src="https://cdn.tailwindcss.com"></script>
```

### CSS Standards
```css
/* Use Tailwind classes primarily */
/* Add custom styles only when necessary */
.custom-animation {
    transition: all 0.3s ease;
}

/* Keep styles minimal and focused */
.error-message {
    color: #ef4444;
    font-size: 0.875rem;
}
```

## API Design Patterns

### Endpoint Structure
```
GET    /api/items          # List all items
GET    /api/items/:id      # Get specific item
POST   /api/items          # Create new item
PUT    /api/items/:id      # Update item
DELETE /api/items/:id      # Delete item
```

### Response Format
```javascript
// Success response
{
    "success": true,
    "data": { /* item data */ },
    "message": "Operation successful"
}

// Error response
{
    "success": false,
    "error": "Error message",
    "code": "ERROR_CODE"
}
```

### Error Handling
```javascript
// Consistent error handling
try {
    const result = await api.post('/api/items', data);
    // Handle success
} catch (error) {
    console.error('API Error:', error);
    // Show user-friendly message
}
```

## Database Patterns

### SQLite Setup
```javascript
const Database = require('better-sqlite3');
const db = new Database('sqlite.db');

// Create tables with proper schema
db.prepare(`
    CREATE TABLE IF NOT EXISTS items (
        id INTEGER PRIMARY KEY AUTOINCREMENT,
        title TEXT NOT NULL,
        content TEXT,
        created_at DATETIME DEFAULT CURRENT_TIMESTAMP,
        updated_at DATETIME DEFAULT CURRENT_TIMESTAMP
    )
`).run();
```

### Query Patterns
```javascript
// Prepared statements for security
const insertItem = db.prepare(`
    INSERT INTO items (title, content) 
    VALUES (?, ?)
`);

const getItems = db.prepare(`
    SELECT * FROM items 
    ORDER BY created_at DESC
`);
```

## Testing Guidelines

### Manual Testing Checklist
- [ ] All form inputs work correctly
- [ ] Data persists across page refreshes
- [ ] Navigation works between pages
- [ ] API endpoints respond correctly
- [ ] Error handling works properly
- [ ] UI is responsive on different screen sizes

### Automated Testing (Optional)
```javascript
// Basic API testing
async function testAPI() {
    try {
        const response = await fetch('/api/items');
        const data = await response.json();
        console.log('API Test:', data);
    } catch (error) {
        console.error('API Test Failed:', error);
    }
}
```

## Troubleshooting Guide

### Common Issues
1. **CORS Errors**: Ensure server allows frontend origin
2. **Database Locked**: Check for multiple connections
3. **Port Conflicts**: Verify port 8989 is available
4. **File Paths**: Use relative paths, avoid absolute paths
5. **Missing Dependencies**: Check package.json and node_modules

### Debugging Tips
- Use browser developer tools
- Check console for errors
- Verify API endpoints with tools like Postman
- Test database queries directly
- Use console.log for debugging

## Extension Patterns

### Adding New Features
1. **Update requirements-document.md** with new requirement
2. **Create necessary files** following the organization pattern
3. **Implement feature** using established patterns
4. **Test thoroughly** against acceptance criteria
5. **Update documentation** as needed

### Scaling Considerations
- Keep files small and focused
- Use modular architecture
- Implement proper error handling
- Add logging for debugging
- Consider performance implications

## Success Metrics

### Technical Success
- All requirements are implemented
- Code is clean and well-organized
- No console errors or warnings
- All acceptance criteria are met
- Documentation is complete

### User Experience Success
- Interface is intuitive and responsive
- Data persists correctly
- Navigation is smooth
- Error messages are helpful
- Performance is acceptable

### Learning Success
- Participants understand the concepts
- Code is educational and clear
- Patterns are reusable
- Documentation is helpful
- Experience is positive

This integration guide ensures that AI assistants can effectively support rapid prototyping sessions while maintaining high quality standards and clear communication.
