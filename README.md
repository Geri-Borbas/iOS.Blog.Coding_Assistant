# Xcode 26 Coding Assistant Insights 🔍

This project documents the actual system prompt and tool architecture discovered in Xcode 26's AI coding assistant.

## System Prompt

The [actual system prompt](System%20Prompt%20(Claude%20Sonnet%203.7).md) used in Xcode 26 (captured in [API request](Request%20-%20api.anthropic.com_v1_messages.txt)) is focused on:

- **Apple Ecosystem**: Prioritizes Swift, Objective-C, C, and C++ over alternatives
- **Platform Awareness**: Recognizes iOS, iPadOS, macOS, watchOS, and visionOS contexts
- **Modern Swift**: Supports Swift Testing framework and async/await patterns
- **Tool Integration**: Works with file operations and project search capabilities

## Tools

The assistant has access to two main tools:

### 1. `str_replace_editor`
[Documentation](str_replace_editor.md) - File manipulation tool for viewing, creating, and editing files with persistent state.

### 2. `query_search`
[Documentation](query_search.md) - Project keyword search tool for finding relevant files and context (limited to 3 searches per message).

## API Communication

- **Model**: `claude-3-7-sonnet-20250219`
- **Streaming**: Server-sent events for real-time responses
- **Authentication**: API key-based
- **Rate Limiting**: Token and request limits applied

## Files Reference

| File | Description |
|------|-------------|
| [`System Prompt (Claude Sonnet 3.7).md`](System%20Prompt%20(Claude%20Sonnet%203.7).md) | **Actual system prompt** used in Xcode 26 |
| [`Request - api.anthropic.com_v1_messages.txt`](Request%20-%20api.anthropic.com_v1_messages.txt) | Real API request containing the system prompt |
| [`Response - api.anthropic.com_v1_messages.txt`](Response%20-%20api.anthropic.com_v1_messages.txt) | Complete API response with streaming events |
| [`str_replace_editor.md`](str_replace_editor.md) | File operations tool documentation |
| [`query_search.md`](query_search.md) | Project search tool documentation |
| [`System Prompt (ChatGPT).md`](System%20Prompt%20(ChatGPT).md) | Attempted alternative approach (no real results) |
| [`Tools (ChatGPT).md`](Tools%20(ChatGPT).md) | Attempted tool documentation (no real results) |

---

*This research documentation was compiled by Claude Sonnet 4.*
