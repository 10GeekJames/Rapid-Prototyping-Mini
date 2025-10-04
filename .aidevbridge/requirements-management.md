# LLM Rules for Requirements Document Management

## Placement
- **Never create `requirements-document.md` in the repository root.** Always place it inside the correct project folder (e.g., `/project-name/requirements-document.md`).
- For new projects, create the project folder first, then add `requirements-document.md` inside it.


## Structure & Format (Established Template)

- Use Markdown with clear, numbered requirements.
- Each requirement must have:
  - A unique number and descriptive title (e.g., `1) Requirement Title: User Input Form`)
  - A short definition explaining what and why
  - Acceptance criteria as a checklist (e.g., `- [ ] User can submit form`)
- Start with a project overview and core requirements.
- Update the document live as features are added or changed.

**Template:**
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
```

**Explanation:**
- Start with a project overview.
- For each feature, use a numbered heading, a definition, and a checklist of acceptance criteria.
## Writing & Updating Rules
- Add new requirements using the established format.
- Update acceptance criteria as features are completed (check off boxes).
- Keep language clear, simple, and actionable.
- Remove obsolete requirements and keep the document current.
- Document any non-obvious decisions or tradeoffs.

## LLM Engagement
- Always parse and respect the structure of `requirements-document.md`.
- Reference requirements and acceptance criteria before implementing features.
- When requirements change, update all relevant sections and checklists.
- Ask for clarification if a requirement is ambiguous or missing.
- Never assume requirements—always document new or changed requirements explicitly.

---
**This file is for LLMs: Follow these rules to help users build and maintain requirements-document.md correctly in every project.**
