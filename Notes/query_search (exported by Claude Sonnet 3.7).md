# query_search Tool

## Description
A tool for querying the project for contextual information by keyword searching for additional files.

Key features:
- Can be used up to 3 times per message the user sends
- The user sees every search performed, so it's important to avoid making noisy or redundant requests
- Helps find relevant files and context within the project

## Schema
```json
{
  "name": "query_search",
  "description": "Query the project for contextual information by keyword searching for additional files. You can do this up to 3 per message the user sends you. However, the user sees every search you perform, so avoid making noisy or redundant requests when possible — and make sure you use your context window wisely.",
  "parameters": {
    "description": "queries",
    "properties": {
      "queries": {
        "items": {
          "type": "string"
        },
        "type": "array"
      }
    },
    "required": ["queries"],
    "type": "object"
  }
}
```

## Examples

### Search for files related to a specific feature
```
<function_calls>
<invoke name="query_search">
<parameter name="queries">["UIViewController", "navigation controller", "view lifecycle"]</parameter>
</invoke>
</function_calls>
```

### Search for Swift files related to networking
```
<function_calls>
<invoke name="query_search">
<parameter name="queries">["URLSession", "network request", "API client"]</parameter>
</invoke>
</function_calls>
```

### Search for model or data structures
```
<function_calls>
<invoke name="query_search">
<parameter name="queries">["struct Model", "class ViewModel", "protocol DataSource"]</parameter>
</invoke>
</function_calls>
```

The `query_search` tool is especially useful when you need to:
1. Find related files in a large codebase
2. Locate implementation details for specific features
3. Discover how certain patterns are used throughout the project
4. Find dependencies or related components

When using this tool, try to:
- Be specific in your search terms
- Combine related concepts in a single query
- Avoid redundant searches that might return the same files
- Use file extensions (like `.swift`) when appropriate to narrow results
