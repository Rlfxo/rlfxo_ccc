# Archive Session Knowledge

You are helping to archive and update the knowledge base for the current project.

## Instructions

1. **Identify the current project** by checking the working directory
2. **Determine the knowledge base path**: `/Users/gilbert/Claude/{project-name}/`
3. **Update or create the following files**:
   - `rlf-core.md` - Core knowledge about the project (architecture, key concepts)
   - `rlf-code-map.md` - File structure and important code locations
   - `rlf-discoveries.md` - Important discoveries from this session
   - `sessions/{date}-session.md` - This session's Q&A and findings

## Knowledge Base Format

### rlf-core.md
```markdown
# Project: {name}
Path: {path}
Type: {embedded/backend/frontend/etc}

## Architecture
- Brief system overview
- Key components
- Tech stack

## Key Concepts
- Domain-specific concepts
- Protocols
- Design patterns used

## Critical Files
- file:line - description
```

### rlf-code-map.md
```markdown
# Code Structure Map

## Initialization Flow
main() → function1() → function2()

## Key Modules
### Module Name
- file.c:function() - purpose

## Message Flows
Source → Destination (via mechanism)
```

### rlf-discoveries.md
```markdown
# Discoveries

## {Date} - {Topic}
### Question
- Original question

### Finding
- What was discovered

### Code Evidence
- file:line - snippet or description

### Impact
- Why this matters
```

## Your Task

1. Read the conversation history from this session
2. Extract key learnings, code locations, and insights
3. Update the knowledge base files (merge with existing if present)
4. Create a session summary in `sessions/{today}-session.md`
5. Respond with a summary of what was archived

## Important
- Be concise but complete
- Focus on facts, code locations, and discoveries
- Use absolute file paths
- Include line numbers for code references
- Optimize for quick AI comprehension (not human readability)

# Tip
False knowledge that is duplicated or unnecessary is checked by the user and deleted to optimize it.

