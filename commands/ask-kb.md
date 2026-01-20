# Query Knowledge Base

Search the knowledge base for specific information.

## Usage
`/ask-kb {query}`

Example: `/ask-kb SLAC timing`

## Instructions

1. **Load knowledge base** from `/Users/gilbert/Claude/{project-name}/`
2. **Search across all files** for the query term
3. **Return relevant excerpts** with context
4. **Include file references** where information was found

## Output Format

```
# Knowledge Base Results: "{query}"

## Found in rlf-core.md
{relevant excerpt}

## Found in rlf-discoveries.md
### {Date} - {Topic}
{relevant discovery}

## Found in sessions/
### {session-file}
{relevant Q&A}

## Code References
- file:line - {description}
```

## Notes
- Use grep-like search across knowledge base
- Show context around matches
- If nothing found, suggest related topics or running `/archive`
