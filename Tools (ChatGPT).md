# Coding Assistant Tools Reference

This document lists all the tools the coding assistant is allowed to use, as described in the system prompt. For each tool, you'll find its name, purpose, schema (parameters and types), and a usage example.

---

## 1. classify_message

**Purpose:**
Classifies the user's message as either an explanation request or a code change request. This tells the assistant if it should explain or modify code.

**Schema:**
```json
{
  "classification": "string", // Either 'explain'/Users/tahoe/Desktop/System Prompt.md or 'make changes'
  "reasoning": "string" // Reasoning for the chosen classification
}

