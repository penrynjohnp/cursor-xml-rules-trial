# Cursor Rules System

This repository contains a structured system for managing and implementing Cursor AI rules that enhance code quality, maintain consistency, and automate development workflows.

## Getting Started

The easiest and recommended way to create new rules is to ask the AI to generate them. The AI understands the required structure and will automatically format the rule correctly, including all necessary sections and proper XML formatting.

### Example Prompts

Here are some examples of prompts that could generate rules similar to those in this repository:

1. "Create a rule that enforces TypeScript type safety standards. It should ensure proper type definitions, prevent any usage, and maintain strict type checking across the codebase."

   - This could generate something like our `ts-type-safety.mdc` rule

2. "Create a rule for Test-Driven Development workflow that guides developers through the red-green-refactor cycle. It should enforce writing tests first, then implementation."

   - This could generate something like our `tdd-workflow.mdc` rule

3. "Create a rule for documentation standards that follows Google's Technical Writing Style Guide. It should enforce clear, consistent documentation in JSDoc comments and markdown files."
   - This could generate something like our `documentation-standards.mdc` rule

### Why XML?

The rules use XML format for several key reasons:

1. **Structured Validation**: XML provides strict schema validation, ensuring rules maintain consistent structure
2. **Clear Hierarchy**: XML's nested structure clearly represents relationships between rule components
3. **Machine Readability**: XML is easily parsed and processed by both AI and traditional tools
4. **Metadata Support**: XML naturally supports rich metadata and attributes
5. **Standard Processing**: Extensive tooling exists for XML validation and transformation

## Overview

The Cursor Rules System is a powerful framework that allows you to define, manage, and enforce coding standards, documentation requirements, and development workflows through AI-assisted rules. Each rule is defined in a `.mdc` file format that combines frontmatter configuration with XML-based rule definitions.

## Rule File Structure

### Location

All rule files must be placed in the `.cursor/rules/` directory with a `.mdc` extension:

```
.cursor/
└── rules/
    ├── your-rule-name.mdc
    └── another-rule.mdc
```

### File Format

Each rule file consists of two main sections:

1. **Frontmatter Configuration**

```yaml
---
description: ALWAYS use when [TRIGGER_SCENARIO] to ensure [OUTCOME]. [BRIEF_EXPLANATION]
globs: "**/*.{extension}"
---
```

2. **XML Rule Definition**

```xml
<?xml version="1.0" encoding="UTF-8"?>
<rule>
  <metadata>...</metadata>
  <filters>...</filters>
  <actions>...</actions>
  <examples>...</examples>
</rule>
```

## Key Requirements

### Description Format

- Must start with action words (e.g., "ALWAYS", "NEVER", "USE")
- Clearly specify trigger scenarios
- Be concise but complete (1-2 sentences)
- Include relevant trigger keywords
- Match exactly between frontmatter and metadata

### File Naming

- Use kebab-case format
- Must be descriptive of the rule's purpose
- Must have `.mdc` extension

### XML Structure

- Proper formatting with consistent indentation
- Required sections: metadata, filters, actions, examples
- CDATA tags for special characters when necessary
- Example section showing correct and incorrect usage

## Creating New Rules

When creating a new rule:

1. Place the file in `.cursor/rules/` directory
2. Use the proper naming convention: `your-rule-name.mdc`
3. Include required frontmatter fields
4. Structure the XML content with all required sections
5. Provide clear examples of correct and incorrect usage

## Best Practices

1. **Optimization for AI**

   - Use clear, actionable descriptions
   - Include relevant trigger keywords
   - Specify precise file patterns in globs

2. **Clarity and Maintainability**

   - Keep descriptions concise but complete
   - Use consistent formatting
   - Document examples thoroughly

3. **Rule Enforcement**
   - Define clear trigger scenarios
   - Specify precise file patterns
   - Include comprehensive validation rules

## Example Rule Template

```yaml
---
description: ALWAYS use when writing new components to ensure consistent styling. This rule enforces design standards and best practices.
globs: "**/*.{tsx,jsx}"
---
<?xml version="1.0" encoding="UTF-8"?>
<rule>
<metadata>
<description>ALWAYS use when writing new components to ensure consistent styling. This rule enforces design standards and best practices.</description>
<priority>high</priority>
<version>1.0</version>
</metadata>
<!-- Add filters, actions, and examples sections -->
</rule>
```

## Common Mistakes to Avoid

1. Placing rule files outside `.cursor/rules/` directory
2. Missing or mismatched descriptions between frontmatter and metadata
3. Vague or non-actionable descriptions
4. Incomplete XML sections
5. Missing examples of correct/incorrect usage

## Leveraging Rules

Rules can be used to:

- Enforce coding standards
- Maintain documentation quality
- Ensure consistent workflows
- Automate development processes
- Guide AI-assisted development

Each rule should be designed to be both human-readable and optimized for AI interpretation, enabling seamless integration with development workflows while maintaining clear standards for the development team.
