# Requirements Management for Rapid Prototyping

## Overview

The `requirements-document.md` file serves as the single source of truth for project scope, features, and constraints during rapid prototyping sessions. This document guides both human developers and AI assistants through the development process.

## File Structure

### Location
- **Root Level**: `requirements-document.md` in project root
- **Format**: Markdown with numbered requirements
- **Updates**: Live document, updated as features are added

### Template Format
```markdown
# Project Requirements

## Project Overview
Brief description of what we're building and why.

## Core Requirements

### 1) Requirement Title: [Feature Name]
**Requirement Definition:** [What the feature does and why it's needed]
**Acceptance Criteria:**
- [ ] Specific, testable criteria
- [ ] Another measurable outcome
- [ ] User experience expectation

### 2) Requirement Title: [Next Feature]
**Requirement Definition:** [Clear description]
**Acceptance Criteria:**
- [ ] Criteria 1
- [ ] Criteria 2

## Technical Constraints
- Technology stack limitations
- Performance requirements
- Integration constraints

## Success Metrics
- What defines a successful prototype
- Key functionality that must work
- User experience goals
```

## Requirement Writing Guidelines

### Requirement Titles
- **Format**: `{Number}) Requirement Title: {Feature Name}`
- **Style**: Action-oriented, clear, concise
- **Examples**: 
  - `1) Requirement Title: User Input Form`
  - `2) Requirement Title: Data Persistence`
  - `3) Requirement Title: Navigation Menu`

### Requirement Definitions
- **Purpose**: Explain what the feature does and why it's needed
- **Scope**: Define boundaries and limitations
- **Context**: How it fits into the overall system
- **User Value**: What problem it solves

### Acceptance Criteria
- **Format**: Bullet points with checkboxes
- **Specificity**: Measurable, testable outcomes
- **Completeness**: Cover all aspects of the requirement
- **User Focus**: Written from user perspective

## AI Assistant Instructions

### When Reading Requirements
1. **Parse Structure**: Identify requirement numbers, titles, and definitions
2. **Extract Criteria**: Note all acceptance criteria and checkboxes
3. **Understand Context**: Read project overview and technical constraints
4. **Plan Implementation**: Break down into implementable tasks

### When Updating Requirements
1. **Add New Requirements**: Follow the established format
2. **Update Status**: Check off completed acceptance criteria
3. **Add Details**: Include technical notes or implementation details
4. **Maintain Clarity**: Keep language simple and actionable

### When Implementing Features
1. **Reference Requirements**: Always check against acceptance criteria
2. **Test Against Criteria**: Verify each checkbox can be completed
3. **Update Progress**: Mark criteria as completed when done
4. **Document Issues**: Note any constraints or challenges

## Requirement Categories

### Core Functionality
- Essential features that must work
- Primary user interactions
- Data flow and persistence
- Basic navigation and routing

### User Experience
- Interface design and layout
- Responsive behavior
- Error handling and feedback
- Loading states and transitions

### Technical Implementation
- API design and endpoints
- Database schema and queries
- Security considerations
- Performance requirements

### Integration Points
- External service connections
- Data import/export
- Authentication and authorization
- Real-time features

## Quality Standards

### Requirement Completeness
- [ ] Clear title and definition
- [ ] Specific acceptance criteria
- [ ] Measurable outcomes
- [ ] User-focused language
- [ ] Technical feasibility

### Implementation Readiness
- [ ] Requirements are actionable
- [ ] Acceptance criteria are testable
- [ ] Dependencies are identified
- [ ] Constraints are documented
- [ ] Success metrics are defined

### Documentation Quality
- [ ] Consistent formatting
- [ ] Clear language
- [ ] Logical organization
- [ ] Complete information
- [ ] Easy to understand

## Common Patterns

### Form Requirements
```markdown
### X) Requirement Title: User Registration Form
**Requirement Definition:** Allow users to create accounts with basic information
**Acceptance Criteria:**
- [ ] Form accepts name, email, and password
- [ ] Validates email format
- [ ] Shows success/error messages
- [ ] Prevents duplicate emails
- [ ] Stores data in database
```

### API Requirements
```markdown
### X) Requirement Title: Data Retrieval API
**Requirement Definition:** Provide RESTful endpoints for data access
**Acceptance Criteria:**
- [ ] GET /api/items returns list of items
- [ ] GET /api/items/:id returns specific item
- [ ] Proper HTTP status codes
- [ ] JSON response format
- [ ] Error handling for missing data
```

### UI Requirements
```markdown
### X) Requirement Title: Responsive Navigation
**Requirement Definition:** Navigation that works on all screen sizes
**Acceptance Criteria:**
- [ ] Collapses to hamburger menu on mobile
- [ ] Shows full menu on desktop
- [ ] Smooth transitions between states
- [ ] Accessible keyboard navigation
- [ ] Consistent styling across pages
```

## Maintenance Guidelines

### Regular Updates
- Update requirements as scope changes
- Mark completed criteria with checkboxes
- Add new requirements as features are discovered
- Remove obsolete requirements
- Keep document current and accurate

### Version Control
- Commit changes frequently
- Use descriptive commit messages
- Tag major milestone updates
- Maintain change history
- Document breaking changes

### Collaboration
- Share updates with team members
- Get approval for major changes
- Document decisions and rationale
- Maintain consistency across sessions
- Ensure everyone understands requirements

## Integration with Development

### Pre-Development
- Review all requirements
- Identify dependencies
- Plan implementation order
- Estimate effort and time
- Prepare development environment

### During Development
- Reference requirements frequently
- Update progress regularly
- Document implementation decisions
- Test against acceptance criteria
- Maintain requirement traceability

### Post-Development
- Verify all criteria are met
- Document any deviations
- Update requirements for future iterations
- Gather feedback for improvements
- Plan next phase requirements

This requirements management system ensures clear communication, consistent development, and successful rapid prototyping outcomes.
