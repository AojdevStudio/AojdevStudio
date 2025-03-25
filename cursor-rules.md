I'll revise the rules to prioritize the Think MCP tool over Sequential Thinking and update the database rules for Supabase. Here's the updated version of rule #1 and the database rules, with all communication rules in markdown format.

### 1. MCP Tool Usage (mcp-tool-usage.mdc)

```markdown
---
description: Mandatory MCP Tool Usage Requirements
globs: 
alwaysApply: true
---

## Think MCP (PRIMARY THINKING TOOL)
- Use for ALL analysis tasks, debugging, troubleshooting, complex problem-solving, and project planning
- Structure thoughts in a logical progression:
  - Begin with problem definition and context assessment
  - Analyze alternatives and trade-offs
  - Conclude with concrete action plans
- Record all reasoning processes to maintain decision history
- Use for multi-step problem decomposition
- Recall previous thoughts when needed for context

## Sequential Thinking MCP (SECONDARY TOOL)
- Only use when explicitly requested by user
- Do not use if Think MCP has already been applied to the same problem
- Ensure there's no collision between Think and Sequential Thinking tools

## Web Search Tools
- Use Brave Search for general programming questions, error messages, documentation
- Use Tavily Search for specialized technical content, library-specific information
- Focus queries on specific technical terms and include version information
- Report found information with sources
- Combine with Think MCP to refine solutions based on research
```

### 4. Database and Data Handling (database-rules.mdc)

```markdown
---
description: Supabase Database and Data Handling Requirements
globs: 
alwaysApply: true
---

## Supabase Database Operations
- Use Supabase PostgreSQL MCP server for all database operations
- Create proper database schema with appropriate relationships
- Utilize RLS (Row Level Security) for all tables that contain user data
- Implement proper error handling for all Supabase operations
- Use structured PostgreSQL queries rather than raw JSON storage
- Leverage Supabase's built-in authentication when appropriate
- Utilize PostgREST API for data access patterns

## Supabase Data Protection
- Never expose API keys in client-side code
- Configure proper RLS policies for all tables
- Use Supabase storage with appropriate bucket policies
- Implement proper data validation before storage operations
- Never delete or alter critical data without explicit confirmation
- Back up data before major migrations or schema changes
- Test database operations thoroughly in the development environment
```

### 5. Communication Protocol (communication-protocol.mdc)

```markdown
---
description: Communication Standards and Change Reporting
globs: 
alwaysApply: true
---

# COMMUNICATION PROTOCOL

## Status Updates
- After EACH change, provide:
  ```
  [COMPLETE] Description of change
  - Coverage: XX% statements, XX% branches
  - Next: Description of next step
  - Updated: stories.md [x] Sub-task name
  ```

## Change Classification
- [MINOR] 1-5 lines
- [MODERATE] 5-20 lines
- [MAJOR] 20+ lines (requires approval)
- [COMPLEX] Affects >3 files (requires approval)

## Tool Usage Reporting
- After using Think MCP:
  ```
  [THINK COMPLETE] - X thoughts recorded
  - Key insights: Brief summary
  - Action plan: Identified steps
  ```

- After web searches:
  ```
  [WEB SEARCH COMPLETE] - Used <Tool>
  - Found: Key findings summary
  - Applied: How information was used
  - Source: Main reference URLs
  ```

## Approval Requirements
- MUST get approval for [MAJOR] changes
- MUST get approval for [COMPLEX] changes
- MUST get approval for performance-critical changes
- MUST get approval for database schema changes

## Documentation Updates
- Update stories.md in real-time after each component completion
- Document all status changes with appropriate markers:
  - Complete: [x]
  - In Progress: [-]
  - Pending: [ ]
- Record all technical decisions in instructions.md
- Log significant events and milestones in logs.md
```

### Project-Level MCP Setup (.cursor/mcp.json)

Here's an updated MCP configuration with Think as the primary tool and Supabase integration:

```json
{
  "mcpServer": {
    "think": {
      "type": "Think"
    },
    "sequential-thinking": {
      "type": "SequentialThinking"
    },
    "brave-search": {
      "type": "BraveSearch"
    },
    "tavily-search": {
      "type": "TavilySearch"
    },
    "supabase": {
      "type": "PostgreSQL",
      "connectionString": "YOUR_SUPABASE_CONNECTION_STRING_HERE"
    }
  }
}
```
