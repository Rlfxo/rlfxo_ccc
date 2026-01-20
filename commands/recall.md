# Recall Project Knowledge

Load and summarize the knowledge base for the current project to provide context for the conversation.

## Instructions

1. **Identify the current project** from working directory
2. **Load knowledge base** from `/Users/gilbert/Claude/{project-name}/`
3. **Read these files in order**:
   - `rlf-core.md` - Core project knowledge
   - `rlf-code-map.md` - Code structure
   - `rlf-discoveries.md` - Recent discoveries (last 10 entries)
   - `sessions/` - List recent sessions (last 3)

4. **Provide a concise summary** (under 500 words) covering:
   - Project type and purpose
   - Key architecture points
   - Important code locations you've learned
   - Recent discoveries
   - Unresolved questions (if any)

5. **Set context** for continuing work

## Output Format

```
# Context Loaded: {project-name}

## Project Overview
{brief description}

## Known Architecture
{key points}

## Important Code Locations
{file:line references}

## Recent Discoveries
{last few discoveries}

## Ready to Continue
Context loaded. What would you like to explore?
```

## Notes
- If knowledge base doesn't exist, inform the user and suggest running `/archive` first
- Keep summary concise but informative
- Prioritize recent/relevant information
